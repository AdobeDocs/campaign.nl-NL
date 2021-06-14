---
product: Adobe Campaign
title: SDK's voor campagnes integreren met uw app
description: Meer informatie over het integreren van Campagne-Android- en iOS-SDK's in uw app
version: v8
feature: Push
role: Developer
level: Experienced
hide: true
hidefromtoc: true
source-git-commit: 9f05209e47f35c91720f68d56593812115726817
workflow-type: tm+mt
source-wordcount: '1567'
ht-degree: 1%

---

# SDK&#39;s voor campagnes integreren met uw app {#integrate-campaign-sdk}

Gebruik de campagne-SDK&#39;s voor iOS en Android om de integratie van uw mobiele toepassing in het Adobe Campaign-platform te vergemakkelijken.

Ondersteunde versies voor Android en iOS, en compatibele versies voor Campagne SDK&#39;s voor Campagne v8 worden vermeld in [Compatibiliteitsmatrix](../start/compatibility-matrix.md#MobileSDK).

>[!NOTE]
>
>Als beheerder van de Campagne, kunt u Campagne SDKs van [de Distributie van de Software van de Experience Cloud downloaden ](https://experience.adobe.com/#/downloads/content/software-distributicampaign.html). Neem voor meer informatie contact op met de [klantenservice van Adobe](https://helpx.adobe.com/nl/enterprise/admin-guide.html/enterprise/using/support-for-experience-cloud.ug.html).


## Integratie-instellingen {#declaring-integration-settings} declareren

Als u de campagne-SDK wilt integreren in de mobiele toepassing, moet de functionele beheerder de ontwikkelaar de volgende informatie geven:

* **Een integratiesleutel**: om het Adobe Campaign-platform in staat te stellen de mobiele toepassing te identificeren.

   >[!NOTE]
   >
   >Deze integratietoets wordt ingevoerd in de Adobe Campaign-console, op het tabblad **[!UICONTROL Information]** van de service die is toegewezen aan de mobiele toepassing. Raadpleeg [Campaign Classic v7-documentatie](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/configure-the-mobile-app/configuring-the-mobile-application.html?lang=en#creating-ios-app).

* **Een URL** voor bijhouden: die overeenkomt met het adres van de Adobe Campaign-trackingserver.
* **Een marketing-URL**: om de inzameling van abonnementen toe te laten.

* **In Android**:

   ```sql
   Neolane.getInstance().setIntegrationKey("your Adobe mobile app integration key");
   Neolane.getInstance().setMarketingHost("https://yourMarketingHost:yourMarketingPort/");
   Neolane.getInstance().setTrackingHost("https://yourTrackingHost:yourTrackingPort/"); 
   ```

* **In iOS**:

   ```sql
   Neolane_SDK *nl = [Neolane_SDK getInstance];
   [nl setMarketingHost:strMktHost];
   [nl setTrackingHost:strTckHost];
   [nl setIntegrationKey:strIntegrationKey];
   ```

## Android-SDK integreren

Android SDK is een jar-bibliotheek geschreven in JAVA. Zo kunnen Android-ontwikkelaars integreren met Adobe Campaign: registreert een nieuw apparaat, koppelt het apparaat met een gebruiker, volgt gedrag, en meer.

In deze sectie leert u hoe u de Android-SDK kunt gebruiken in een Android-toepassing die [FCM (Firebase Cloud Messaging)](https://firebase.google.com/docs/cloud-messaging/) van Google implementeert.

### FCM configureren

Als u de pushmelding wilt gebruiken op Android, moet u een FCM-account hebben, uw Android-toepassing configureren om uw melding te ontvangen en uw toepassing aan de FCM-account te koppelen. Meer informatie vindt u in [Google-documentatie](https://firebase.google.com/docs/cloud-messaging/).

Raadpleeg [Google-documentatie](https://firebase.google.com/docs/android/setup) om Firebase aan uw Android-project toe te voegen.

Leer hoe u FCM in uw toepassing implementeert in [Google-documentatie](https://firebase.google.com/docs/android/setup).

>[!NOTE]
>
> * Vergeet niet google-services.json aan uw project te downloaden en toe te voegen.
   >
   > 
* De `apiKey` moet overeenkomen met de `projectKey`-set in de Adobe Campaign Mobile-toepassing die is gekoppeld aan deze Android-toepassing.


### Android-SDK configureren

1. **De SDK initialiseren**

   Voordat u de Android-SDK kunt gebruiken, moet u deze initialiseren. De SDK-initialisatie kan worden uitgevoerd in de functie `onCreate` van een activiteit.

   ```sql
   /** Called when the activity is first created. */
   @Override
   public void onCreate(Bundle savedInstanceState)
   {
       super.onCreate(savedInstanceState);
   
       // initialize Campaign SDK
       SharedPreferences settings = getSharedPreferences(YourApplicationActivity.APPLICATION_PREF_NAME, Context.MODE_PRIVATE);
   
       Neolane.getInstance().setIntegrationKey(settings.getString(YourApplicationActivity.APPUUID_NAME, YourApplicationActivity.DFT_APPUUID));
       Neolane.getInstance().setMarketingHost(settings.getString(YourApplicationActivity.SOAPRT_NAME, YourApplicationActivity.DFT_SOAPRT));
       Neolane.getInstance().setTrackingHost(settings.getString(YourApplicationActivity.TRACKRT_NAME, YourApplicationActivity.DFT_TRACKRT));
       ...
   }
   ```

   De `IntegrationKey` moet overeenkomen met de &#39;IntegrationKey&#39;-set in de Adobe Campaign Mobile-toepassing die is gekoppeld aan deze Android-toepassing.

1. **Het mobiele apparaat registreren op de Adobe Campaign-server**

   Met de registratiefunctie kunt u:

   * Stuur de bericht-id of push-id (deviceToken voor iOS en registrationID voor Android) naar Adobe Campaign.
   * de afstemmingssleutel of de gebruikersnaam herstellen (bijvoorbeeld e-mail- of accountnummer)

   U moet uw apparaat registreren bij Adobe Campaign, bij de initialisatie van de app of bij actie van de gebruiker. Het kan gemakkelijk worden gedaan gebruikend de `registerDevice` methode.

   ```sql
   public void onClick(View v)
   {
   SharedPreferences settings = this.context.getSharedPreferences(YourApplicationActivity.APPLICATION_PREF_NAME, Context.MODE_PRIVATE);
   EditText mailEdit = (EditText) this.context.findViewById(R.id.editText1);
   
   final String FCMRegistrationId = FirebaseInstanceId.getInstance().getToken();
   if (FCMRegistrationId != null)
       NeoTripActivity.registerOnNeolane(this.context, FCMRegistrationId, mailEdit.getText().toString());
   
   }
   ```

   YourApplicationActivity.java

   ```sql
   public static void registerOnNeolane(final Context ctx, String registrationId, String userKey)
   {
       NeolaneAsyncRunner neolaneAs = new NeolaneAsyncRunner(Neolane.getInstance());
       // Additional Subscription Parameters
       Map<String,Object> additionnalParam = new HashMap<String, Object>();
       additionnalParam.clear();
       SharedPreferences settings = ctx.getSharedPreferences(YourApplicationActivity.APPLICATION_PREF_NAME, Context.MODE_PRIVATE);
       if (settings.getBoolean(YourApplicationActivity.SUBPARAMEN1_NAME, false))
       {
           additionnalParam.put(settings.getString(YourApplicationActivity.SUBPARAMNAME1_NAME, "") , settings.getString(YourApplicationActivity.SUBPARAMVALUE1_NAME, ""));   
       }
       if (settings.getBoolean(YourApplicationActivity.SUBPARAMEN2_NAME, false))
       {
           additionnalParam.put(settings.getString(YourApplicationActivity.SUBPARAMNAME2_NAME, "") , settings.getString(YourApplicationActivity.SUBPARAMVALUE2_NAME, ""));   
       }
       if ( additionnalParam.isEmpty() )
       {
           additionnalParam = null;
       }
       // Campaign Registration
       neolaneAs.registerDevice(registrationId, userKey, additionnalParam, ctx, new RequestListener() {
       public void onComplete(String e, Object obj)
       {
           Intent upd = new Intent();
           upd.setAction(BROADCAST_NEWREGISTER_ACTION);
           ctx.sendBroadcast(upd);
       }
   
       public void onNeolaneException(NeolaneException e, Object obj)
       {
           sendErrorMsg(e.getErrorString());
       }
   
       public void onIOException(IOException e, Object obj)
       {
           sendErrorMsg(e.getMessage());
       }
   
       public void sendErrorMsg(String err)
       {
           SharedPreferences.Editor edit = ctx.getSharedPreferences(YourApplicationActivity.APPLICATION_PREF_NAME, Context.MODE_PRIVATE).edit();
           edit.putBoolean(YourApplicationActivity.REGISTRATION_ERROR_NEOLANE_KEYNAME, true);
           edit.commit();
           Intent toast = new Intent();
           toast.setAction(BROADCAST_TOAST_DISPLAY_TEXT);
           toast.putExtra("text", "An error happened, please register again (" + err + ")");
           ctx.sendBroadcast(toast);
       }
       });
   }
   ```

1. **Campagne waarschuwen wanneer het token van het mobiele apparaat van de gebruiker verandert**

   We raden u aan de functie `registerDevice` te gebruiken wanneer u de functie `onTokenRefresh` aanroept om Adobe Campaign op de hoogte te stellen van de wijziging in het token voor mobiele apparaten van de gebruiker.

   Bijvoorbeeld:

   YourApplicationFirebaseInstanceIDService.java

   ```sql
   package com.android.YourApplication;
   
   import android.content.Context;
   import android.content.SharedPreferences;
   import android.util.Log;
   
   import com.google.firebase.iid.FirebaseInstanceId;
   import com.google.firebase.iid.FirebaseInstanceIdService;
   
   import static android.content.SharedPreferences.*;
   
   public class YourApplicationFirebaseInstanceIDService extends FirebaseInstanceIdService 
   {
       @Override
       public void onTokenRefresh() 
       {
       SharedPreferences settings = getSharedPreferences(YourApplicationActivity.APPLICATION_PREF_NAME, Context.MODE_PRIVATE);
       if (!settings.getBoolean(YourApplicationActivity.USE_GCM, false))
           {
           String refreshedToken = FirebaseInstanceId.getInstance().getToken();
           String userKey = settings.getString(YourApplicationActivity.USERKEY_NAME, "");
           Editor edit = settings.edit();
           edit.putString(YourApplicationActivity.FCM_REGISTRATIONID_NAME, refreshedToken);
           edit.commit();
           YourApplicationActivity.registerOnNeolane(this, refreshedToken, userKey);
           }
       }
   }
   ```

1. **Firebase Messaging Service configureren**

   Breid `FirebaseMessagingService` in `onMessageReceived` callback uit om berichten te ontvangen. Wij adviseren u om de `notifyReceive` functie te roepen wanneer `onMessageReceived` callback wordt geroepen om het volgen van de berichtontvangst op het mobiele apparaat toe te laten. In Adobe Campaign heet dit **print** bericht: Deze functie moet worden aangeroepen vlak voordat het besturingssysteem wordt gevraagd het bericht weer te geven.

   YourApplicationMessagingService.java

   ```sql
   package com.android.YourApplication;
   
   import android.content.Context;
   import android.content.SharedPreferences;
   import android.os.Bundle;
   import android.util.Log;
   
   import com.google.firebase.messaging.FirebaseMessagingService;
   import com.google.firebase.messaging.RemoteMessage;
   
   import java.util.Iterator;
   import java.util.Map;
   import java.util.Map.Entry;
   
   public class YourApplicationFirebaseMessagingService extends FirebaseMessagingService 
       {
       private static final String TAG = "MyFirebaseMsgService";
   
       @Override
       public void onMessageReceived(RemoteMessage message) 
           {
           Log.d(TAG, "Receive message from: " + message.getFrom());
           Map<String,String> payloadData = message.getData();
           final Bundle extras = new Bundle();
           final Iterator<Entry<String, String>> iter = payloadData.entrySet().iterator();
           while(iter.hasNext())
           {
           final Entry<String, String>  entry =iter.next();
           extras.putString(entry.getKey(), entry.getValue());
           }
   
           SharedPreferences settings = this.getSharedPreferences(YourApplicationActivity.APPLICATION_PREF_NAME, Context.MODE_PRIVATE);
           String mesg = payloadData.get("_msg");
           String title = payloadData.get("title");
           String url = payloadData.get("url");
           String messageId = payloadData.get("_mId");
           String deliveryId = payloadData.get("_dId");
           YourApplicationActivity.handleNotification(this, mesg, title, url, messageId, deliveryId, extras);
           }
       }   
   ```

   Voor Campagne Android SDK v1.1.1

   ```sql
   public static void handleNotification(Context context, String message, String title, String url, String messageId, String deliveryId, Bundle extras)
   {
       if( message == null ) message = "No Content";
       if( title == null )   title = "No title";
       if( url == null )     url = "http://www.tripadvisor.fr";
       int iconId = R.drawable.notif_neotrip;
   
       // notify Adobe Campaign that a notification just arrived
       SharedPreferences settings = context.getSharedPreferences(NeoTripActivity.APPLICATION_PREF_NAME, Context.MODE_PRIVATE);
       Neolane.getInstance().setIntegrationKey(settings.getString(NeoTripActivity.APPUUID_NAME, NeoTripActivity.DFT_APPUUID));
       Neolane.getInstance().setMarketingHost(settings.getString(NeoTripActivity.SOAPRT_NAME, NeoTripActivity.DFT_SOAPRT));
       Neolane.getInstance().setTrackingHost(settings.getString(NeoTripActivity.TRACKRT_NAME, NeoTripActivity.DFT_TRACKRT));
   
       NeolaneAsyncRunner nas = new NeolaneAsyncRunner(Neolane.getInstance());
       nas.notifyReceive(messageId, deliveryId, new NeolaneAsyncRunner.RequestListener() {
       public void onNeolaneException(NeolaneException arg0, Object arg1) {}
       public void onIOException(IOException arg0, Object arg1) {}
       public void onComplete(String arg0, Object arg1){}
       });
       if (yourApplication.isActivityVisible())
       {
       Log.i("INFO", "The application has the focus" );
       ...
       }
       else
       {
       // notification creation
       NotificationManager notificationManager = (NotificationManager) context.getSystemService(Context.NOTIFICATION_SERVICE);
       Notification notification;
   
       // Activity to start
       Intent notifIntent = new Intent(context.getApplicationContext(), NotificationActivity.class);
       notifIntent.putExtra("notificationText", message);
       notifIntent.putExtra(NotificationActivity.NOTIFICATION_URL_KEYNAME, url);
       notifIntent.putExtra("_dId", deliveryId);
       notifIntent.putExtra("_mId", messageId);
       notifIntent.addFlags(Intent.FLAG_ACTIVITY_NEW_TASK);
       PendingIntent contentIntent = PendingIntent.getActivity(context, 1, notifIntent, PendingIntent.FLAG_UPDATE_CURRENT);
   
       notification = new Notification.Builder(context)
               .setContentTitle(title)
               .setContentText(message)
               .setSmallIcon(iconId)
               .setContentIntent(contentIntent)
               .build();
   
       // launch the notification
       notification.flags |= Notification.FLAG_AUTO_CANCEL;
       notificationManager.notify(1234, notification);
       }
   }
   ```

1. **Het spoor opent gegevensberichten**

   Voor gegevensberichten, kunt u volgen wanneer een gebruiker op een bericht klikt om het te openen, gebruikend de functie `notifyOpening`. De meldingsactiviteit zal worden gecreeerd wanneer de gebruiker op het bericht klikt (die tijdens `onMessageReceived`functievraag wordt gecreeerd)

   Voor Campagne Android SDK v1.1.1

   ```sql
   public class NotificationActivity extends Activity {
       public void onCreate(Bundle savedBundle) {
           [...]
           Bundle extra = getIntent().getExtras();
           if (extra != null) {
               // reinit the Campaign sdk
               SharedPreferences settings = getSharedPreferences(NeoTripActivity.APPLICATION_PREF_NAME, Context.MODE_PRIVATE);
               Neolane.getInstance().setIntegrationKey(settings.getString(NeoTripActivity.APPUUID_NAME, NeoTripActivity.DFT_APPUUID));
               Neolane.getInstance().setMarketingHost(settings.getString(NeoTripActivity.SOAPRT_NAME, NeoTripActivity.DFT_SOAPRT));               
               Neolane.getInstance().setTrackingHost(settings.getString(NeoTripActivity.TRACKRT_NAME, NeoTripActivity.DFT_TRACKRT));
   
               // Get the messageId and the deliveryId to perform tracking
               String deliveryId = extra.getString("_dId");
               String messageId = extra.getString("_mId");
   
               if (deliveryId != null && messageId != null) 
               {
                   try {
                   Neolane.getInstance().notifyOpening(messageId, Integer.valueOf(deliveryId));
                   } catch (NeolaneException e) {
                   // ...
                   } catch (IOException e) {
                   // ...
                   }
               }
           }
       }
   }
   ```

1. **Het spoor opent en klikt op berichtberichten**

   Voor berichtberichten, moet open/klik het volgen met de `notifyOpening` functie binnen de toepassingslanceringsactiviteit worden gedaan, zoals hieronder:

   ```sql
   /** Called when the activity is first created. */
   @Override
   public void onCreate(Bundle savedInstanceState)
   {
       super.onCreate(savedInstanceState);
   
       SharedPreferences settings = getSharedPreferences(NeoTripActivity.APPLICATION_PREF_NAME, Context.MODE_PRIVATE);
   
       // initialize Campaign SDK
       Neolane.getInstance().setIntegrationKey(settings.getString(NeoTripActivity.APPUUID_NAME, NeoTripActivity.DFT_APPUUID));
       Neolane.getInstance().setMarketingHost(settings.getString(NeoTripActivity.SOAPRT_NAME, NeoTripActivity.DFT_SOAPRT));
       Neolane.getInstance().setTrackingHost(settings.getString(NeoTripActivity.TRACKRT_NAME, NeoTripActivity.DFT_TRACKRT));
   ...
   ...
   ...
   
       // Manage opening/receive tracking of message notification
       Intent intent = getIntent();
       Bundle data = intent.getExtras();
       String messageId = null, deliveryId = null;
       if( data != null ) {
       if (data.containsKey("_mId")) messageId = data.get("_mId").toString();
       if (data.containsKey("_dId")) deliveryId = data.get("_dId").toString();
       if ( messageId != null && deliveryId != null) {
           Log.i(TAG, "Notify opening from backgroun click_action");
           NeolaneAsyncRunner nas = new NeolaneAsyncRunner(Neolane.getInstance());
           nas.notifyOpening(messageId, deliveryId, new NeolaneAsyncRunner.RequestListener() {
           public void onNeolaneException(NeolaneException arg0, Object arg1) {
               toastMessage( "error", getString(R.string.open_track_sdk_error) + arg0.getErrorCode());
           }
           public void onIOException(IOException arg0, Object arg1) {
               toastMessage( "error", getString(R.string.open_track_io_error) +  arg0.getLocalizedMessage());
           }
           public void onComplete(String arg0, Object arg1) {
               toastMessage( "error", getString(R.string.open_track_ok));
           }
           });
           nas.notifyReceive(Integer.valueOf(messageId), deliveryId, new NeolaneAsyncRunner.RequestListener() {
           public void onNeolaneException(NeolaneException arg0, Object arg1) {
               toastMessage( "error", getString(R.string.rec_track_sdk_error) + arg0.getErrorCode());
           }
           public void onIOException(IOException arg0, Object arg1) {
               toastMessage( "error", getString(R.string.rec_track_io_error) +  arg0.getLocalizedMessage());
           }
           public void onComplete(String arg0, Object arg1) {
               toastMessage( "error", getString(R.string.rec_track_ok));
           }
           });
       }
       }
   }
   ```

   >[!NOTE]
   >
   > Vergelijkbaar beheer moet worden uitgevoerd als de gebruiker de optie `click_action` binnen de doelactiviteit gebruikt.


1. **Tracking ontvangen voor gegevensberichten**

   Voor gegevensberichten, wordt het volgen ontvangen op het `onMessageReceived` vraagniveau. De functie &#39;notifyReceive&#39; moet worden aangeroepen.

   YourApplicationMessagingService.java

   ```sql
   package com.android.YourApplication;
   
   import android.content.Context;
   import android.content.SharedPreferences;
   import android.os.Bundle;
   import android.util.Log;
   
   import com.google.firebase.messaging.FirebaseMessagingService;
   import com.google.firebase.messaging.RemoteMessage;
   
   import java.util.Iterator;
   import java.util.Map;
   import java.util.Map.Entry;
   
   
   public class YourApplicationFirebaseMessagingService extends FirebaseMessagingService {
   private static final String TAG = "MyFirebaseMsgService";
   
   @Override
   public void onMessageReceived(RemoteMessage message) 
       {
           Log.d(TAG, "Receive message from: " + message.getFrom());
           Map<String,String> payloadData = message.getData();
           final Bundle extras = new Bundle();
           final Iterator<Entry<String, String>> iter = payloadData.entrySet().iterator();
           while(iter.hasNext())
           {
           final Entry<String, String>  entry =iter.next();
           extras.putString(entry.getKey(), entry.getValue());
           }
   
           SharedPreferences settings = this.getSharedPreferences(YourApplicationActivity.APPLICATION_PREF_NAME, Context.MODE_PRIVATE);
           String mesg = payloadData.get("_msg");
           String title = payloadData.get("title");
           String url = payloadData.get("url");
           String messageId = payloadData.get("_mId");
           String deliveryId = payloadData.get("_dId");
           YourApplicationActivity.handleNotification(this, mesg, title, url, messageId, deliveryId, extras);
       }
   }
   ```

   ```sql
   public static void handleNotification(Context context, String message, String title, String url, String messageId, String deliveryId, Bundle extras){
       .....
       .....
           // notify Campaign that a notification just arrived
           SharedPreferences settings = context.getSharedPreferences(NeoTripActivity.APPLICATION_PREF_NAME, Context.MODE_PRIVATE);
           Neolane.getInstance().setIntegrationKey(settings.getString(NeoTripActivity.APPUUID_NAME, NeoTripActivity.DFT_APPUUID));
           Neolane.getInstance().setMarketingHost(settings.getString(NeoTripActivity.SOAPRT_NAME, NeoTripActivity.DFT_SOAPRT));
           Neolane.getInstance().setTrackingHost(settings.getString(NeoTripActivity.TRACKRT_NAME, NeoTripActivity.DFT_TRACKRT));
   
           NeolaneAsyncRunner nas = new NeolaneAsyncRunner(Neolane.getInstance());
           nas.notifyReceive(Integer.valueOf(messageId), deliveryId, new NeolaneAsyncRunner.RequestListener() {
               public void onNeolaneException(NeolaneException arg0, Object arg1) {}
               public void onIOException(IOException arg0, Object arg1) {}
               public void onComplete(String arg0, Object arg1){}
       });
   }
   ```

1. **Tracking ontvangen voor berichtberichten**

   Voor berichtberichten, moet de volgende ontvangst op twee niveau worden gevormd:

   * `onMessageReceived` (niet op de achtergrond): de uitvoering heeft plaatsgevonden in het vorige deel
   * `onCreate` van de opstarthandeling (of de doelactiviteit indien de  `click_action`functie wordt gebruikt). (Toepassing niet op de achtergrond).

   U dient dit op hetzelfde moment te doen als klikken en openen.

   ```sql
   /** Called when the activity is first created. */
       @Override
       public void onCreate(Bundle savedInstanceState)
       {
           super.onCreate(savedInstanceState);
   
           SharedPreferences settings = getSharedPreferences(NeoTripActivity.APPLICATION_PREF_NAME, Context.MODE_PRIVATE);
   
           // initialize Campaign SDK
           Neolane.getInstance().setIntegrationKey(settings.getString(NeoTripActivity.APPUUID_NAME, NeoTripActivity.DFT_APPUUID));
           Neolane.getInstance().setMarketingHost(settings.getString(NeoTripActivity.SOAPRT_NAME, NeoTripActivity.DFT_SOAPRT));
           Neolane.getInstance().setTrackingHost(settings.getString(NeoTripActivity.TRACKRT_NAME, NeoTripActivity.DFT_TRACKRT));
   ...
   ...
   ...
   
       // Manage opening/receive tracking of message notification
       Intent intent = getIntent();
       Bundle data = intent.getExtras();
       String messageId = null, deliveryId = null;
       if( data != null ) {
       if (data.containsKey("_mId")) messageId = data.get("_mId").toString();
       if (data.containsKey("_dId")) deliveryId = data.get("_dId").toString();
       if ( messageId != null && deliveryId != null) {
           Log.i(TAG, "Notify opening from backgroun click_action");
           NeolaneAsyncRunner nas = new NeolaneAsyncRunner(Neolane.getInstance());
           nas.notifyOpening(messageId, deliveryId, new NeolaneAsyncRunner.RequestListener() {
           public void onNeolaneException(NeolaneException arg0, Object arg1) {
               toastMessage( "error", getString(R.string.open_track_sdk_error) + arg0.getErrorCode());
           }
           public void onIOException(IOException arg0, Object arg1) {
               toastMessage( "error", getString(R.string.open_track_io_error) +  arg0.getLocalizedMessage());
           }
           public void onComplete(String arg0, Object arg1) {
               toastMessage( "error", getString(R.string.open_track_ok));
           }
           });
           nas.notifyReceive(Integer.valueOf(messageId), deliveryId, new NeolaneAsyncRunner.RequestListener() {
           public void onNeolaneException(NeolaneException arg0, Object arg1) {
               toastMessage( "error", getString(R.string.rec_track_sdk_error) + arg0.getErrorCode());
           }
           public void onIOException(IOException arg0, Object arg1) {
               toastMessage( "error", getString(R.string.rec_track_io_error) +  arg0.getLocalizedMessage());
           }
           public void onComplete(String arg0, Object arg1) {
               toastMessage( "error", getString(R.string.rec_track_ok));
           }
           });
       }
       }
   }
   ```


## iOS SDK integreren

1. **Het mobiele apparaat registreren op de Adobe Campaign-server**

   Met de registratiefunctie kunt u:

   * Stuur de bericht-id of push-id (deviceToken voor iOS en registrationID voor Android) naar Adobe Campaign.
   * de afstemmingssleutel of de gebruikersnaam herstellen (bijvoorbeeld e-mail- of accountnummer)

   ```sql
   // Callback called on successful registration to the APNs
    - (void)application:(UIApplication*)application didRegisterForRemoteNotificationsWithDeviceToken:(NSData*)deviceToken
   {
     // Pass the token to Adobe Campaign
     Neolane_SDK *nl = [Neolane_SDK getInstance];
     [nl registerDevice:tokenString:self.userKey:dic];
   }
   ```

1. **Functie voor bijhouden inschakelen**

   Met de functie voor bijhouden kunt u bijhouden wanneer meldingen zijn geactiveerd (wordt geopend).

   ```sql
   (void)application:(UIApplication *)application didReceiveRemoteNotification:(NSDictionary *)launchOptions
   fetchCompletionHandler:(void (^)(UIBackgroundFetchResult))completionHandler
   {
   if( launchOptions ) { // Retrieve notification parameters here ... // Track application opening Neolane_SDK
   *nl = [Neolane_SDK getInstance]; [nl track:launchOptions:NL_TRACK_CLICK]; } 
   ...  
   completionHandler(UIBackgroundFetchResultNoData);
   }
   ```

1. **Beheer van stille meldingen**

   Met iOS kunt u geen meldingen verzenden, een melding of gegevens die rechtstreeks naar een mobiele toepassing worden verzonden zonder deze weer te geven. Met Adobe Campaign kun je ze volgen.

   Volg het onderstaande voorbeeld om je melding op te volgen:

   ```sql
   // AppDelegate.m
   ...
   ...
   #import "AppDelegate.h"
   #import "Neolane_SDK.h"
   ...
   ...
   // Callback called when the application is already launched (whether the application is running foreground or background)
   - (void)application:(UIApplication *)application didReceiveRemoteNotification:(NSDictionary *)launchOptions fetchCompletionHandler:(void (^)(UIBackgroundFetchResult))completionHandler
   {
   NSLog(@"IN didReceiveRemoteNotification:fetchCompletionHandler");
   if (launchOptions) NSLog(@"IN launchOptions: %@", [launchOptions description]);
   NSLog(@"Application state: %ld", (long)application.applicationState);
   
   // Silent Notification (specific case, can use NL_TRACK_RECEIVE as the user does not have click/open the notification)
   if ([launchOptions[@"aps"][@"content-available"] intValue] == 1 )
       {
   NSLog(@"Silent Push Notification");
   ...  
   ...
   //Call receive tracking
           Neolane_SDK *nl = [Neolane_SDK getInstance];
   [nl track:launchOptions:NL_TRACK_RECEIVE];
   
   completionHandler(UIBackgroundFetchResultNoData); //Do not show notification
   return;
   }  
   ...
   ...
           completionHandler(UIBackgroundFetchResultNoData);
   }
   ```

1. **Registratiestatus configureren**

   Het gedelegeerde protocol staat u toe om het resultaat van **registerDevice** vraag te krijgen en kan worden gebruikt om te weten of een fout tijdens registratie voorkwam.

   Het prototype **registerDeviceStatus** is:

   ```sql
   - (void) registerDeviceStatus: (ACCRegisterDeviceStatus) status:(NSString *) errorReason;
   ```

   * **Met** Status kunt u weten of een registratie is geslaagd of dat een fout is opgetreden.

   * **** ErrorReasonBiedt u meer informatie over de fouten die voorkwamen. Raadpleeg de onderstaande tabel voor meer informatie over beschikbare fouten en beschrijvingen.

| Status | Beschrijving | ErrorReason |
| ---------------------------------------------------------- | ------------------------------------------------------ | ----------------------------------------- |
| ACCRegisterDeviceStatusSuccess | Registratie voltooid | LEEG |
| ACCRegisterDeviceStatusFailedMarketingServerHostnameEmpty | De hostnaam van de ACC-marketingserver is leeg of niet ingesteld. | LEEG |
| ACCRegisterDeviceStatusFailedIntegrationKeyEmpty | De integratietoets is leeg of niet ingesteld. | LEEG |
| ACCRegisterDeviceStatusFailedConnectionIssue | Verbindingsprobleem met ACC | Meer informatie (in huidige taal van besturingssysteem) |
| ACCRegisterDeviceStatusFailedUnknownUID | De opgegeven UUID (integratiesleutel) is onbekend. | LEEG |
| ACCRegisterDeviceStatusFailedUnexpectedError | Onverwachte fout die aan server ACC is teruggekeerd. | The error message returned to ACC. |

{style=&quot;table-layout:auto&quot;}

    **Neolane_SDKDelegate** protocol en **registerDeviceStatus** gedelegeerde definitie is als volgt:
    
    &quot;sql
    // Neolane_SDK.h
    // Campagne SDK
    ..
    ..
    // Apparaatstatus registreren 
    Enumtypedef NS_ENUM(NSUInteger, ACCRegisterDeviceStatus) {
    ACCRegisterDeviceStatusSuccess, // Resistration 
    SucceedACCRegisterDeviceStatusFailedMarketingServerHostnameEmpty, // De hostnaam van de campagne-marketingserver is leeg of niet 
    setACCRegisterDeviceStatusFailedIntegrationKeyEmpty, // De integratietoets is leeg of niet 
    setACCRegisterDeviceFailedConnectionIssue, // Probleem met verbinding met campagne, meer informatie in 
    errorReasonACCRegisterDeviceStatusFailedUnknownUID, // De ingevoerde UUID (integratie)) is 
    unknownACCRegisterDeviceStatusFailedUnexpectedError // Unexpected error returned by Campagne server, more information in errorReason
    };
    // definieer het protocol voor het registerDeviceStatus-gedelegeerde
      &lt;nsobject>
     
    @protocol Neolane_SDKDelegate@optionalDeviceStatus(void) registerDeviceStatus: (ACCRegisterDeviceStatus) status:(NSString *) errorReason;
    @end
    @interface Neolane_SDK: NSObject {
    }
    ..
    ...
    // registerDeviceStatus gedelegeerde
    @eigenschap (niet-atomisch, zwak) id- &lt;neolane_sdkdelegate> gedelegeerde;
    ..
    ...
    @end
    &quot;
    
    Om **registerDeviceStatus** afgevaardigde uit te voeren, volg deze stappen:
    
    1. Voer **setDelegate** tijdens de initialisering van SDK uit.
    
    &quot;sql
    // AppDelegate.m
    ...
    ...
    - (BOOL)application:(UIApplication *)application didFinishLaunchingWithOptions:(NSDictionary *)launchOptions
    {
    ..
    ...
    // Get the stored 
    
    settingsNSUserDefaults *defaults = [NSUserDefaults standardUserDefaults];
    NSString *strMktHost = [defaults objectForKey:@&quot;mktHost&quot;];
    NSString *strTckHost = [defaults objectForKey:@ tckHost&quot;];
    NSString *strIntegrationKey = [defaults objectForKey:@&quot;integrationKey&quot;];
    userKey = [defaults objectForKey:@&quot;userKey&quot;];
    
    // Configure Campagne SDK on first 
    launchNeolane_SDK *nl = [Neolane_SDK getInstance];
     [nl setMarketingHost:strMktHost];
    [nl setTrackingHost:strTckHost];
     
    [nl setIntegrationKey:strIntegrationKey];[nl setDelegate:self]; // HIER
    ...
    ...
    }
    &quot;
    
    1. Voeg het protocol toe in de **@interface** van uw klasse.
    
    &quot;sql
    // AppDelegate.h
    
    #import  &lt;uikit>
    #import  &lt;corelocation>
    #import &quot;Neolane_SDK.h&quot;
    
    @class LandingPageViewController;
    
    @interface AppDelegate: UIResponder  &lt;uiapplicationdelegate> {
    CLLocationManager *locationManager;
    NSString *userKey;
    NSString *mktServerUrl;
    NSString *trackServerUrl;
    NSString *homeURL;
    NSString *strLandingPageUrl;
    NST imer *timer;
    }
     
    
    &quot;1. Voer de afgevaardigde in **AppDelegate** uit.
    
    &quot;sql
    // AppDelegate.m
    
    #import &quot;AppDelegate.h&quot;
    #import &quot;Neolane_SDK.h&quot;
    #import &quot;LandingPageViewController.h&quot;
    #import &quot;RootViewController.h&quot;
    ..
    ...
    - (void) registerDeviceStatus: (ACCRegisterDeviceStatus) status :(NSString *) errorReason
    {
    NSLog(@&quot;registerStatus: %lu&quot;,status);
    
    if (errorReason != nil )
    NSLog(@&quot;errorReason: %@&quot;,errorReason);
    
    if( status == ACCRegisterDeviceStatusSuccess )
    {
    // Registratie geslaagd
    ..
    ..
    }
    else { // An error occurred
    NSString *message;
    switch ( status ){
    case ACCRegisterDeviceFailedUnknownUID:
    message = @&quot;Unknown IntegrationKey (UUID)&quot;;
    break;
    case ACCRegisterDeviceStatusFailedMarketingServerHostnameEmpty:
    message = @&quot;Marketing URL not set or Empty&quot;;
    break;
    case ACCRegisterDeviceStatusFailedIntegrationKeyEmpty:
    message = @&quot;Integration Key not set or empty&quot;;
    break;
    case ACCRegisterDeviceStatusFailedConnectionIssue:
    message = [NSString stringWithFormat:@&quot;%@ %@&quot;,@&quot;Connection issue:&quot;,errorReason];
    break;
    case ACCRegisterDeviceStatusFailedUnexpectedError:
    default:
    message = [NSString stringWithFormat:@&quot;%@ %@&quot;,@&quot;Unexpected Error&quot;,errorReason];
    break;
    }
    ...
    ...
    }
    }
    @end
    &quot;

## Variabelen {#variables}

Met de variabelen kunt u het gedrag van mobiele toepassingen definiëren nadat u een melding hebt ontvangen. Deze variabelen moeten worden gedefinieerd in de mobiele toepassingscode en in de Adobe Campaign-console, op het tabblad **[!UICONTROL Variables]** in de speciale service voor mobiele toepassingen.

[!DNL :arrow_upper_right:] Meer informatie in  **Campaign Classic v7-** documentatie over mobiele app:  [Configuratiestappen voor ](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/configure-the-mobile-app/configuring-the-mobile-application.html) iOS- en  [configuratiestappen voor Andoid](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/configure-the-mobile-app/configuring-the-mobile-application-android.html).

Hieronder ziet u een voorbeeld van een code waarmee een mobiele toepassing toegevoegde variabelen in een melding kan verzamelen. In ons voorbeeld gebruiken we de variabele &quot;VAR&quot;.

* **In Android**:

   ```sql
   public void onReceive(Context context, Intent intent) {
        ...
       String event = intent.getStringExtra("VAR");
        ...
   }
   ```

* **In iOS**:

   ```sql
   - (BOOL)application:(UIApplication *)application didFinishLaunchingWithOptions:(NSDictionary *)launchOptions
   {
       ....
       if( launchOptions )
       {
           // When application is not already launched, the notification data if any are stored in the key 'UIApplicationLaunchOptionsRemoteNotificationKey'
           NSDictionary *localLaunchOptions = [launchOptions objectForKey:@"UIApplicationLaunchOptionsRemoteNotificationKey"];
           if( localLaunchOptions )
           {
            ...
            [localLaunchOptions objectForKey:@"VAR"];
           ...
           }
      }
   }
   
   // Callback called when the application is already launched (whether the application is running foreground or background)
   - (void)application:(UIApplication *)application didReceiveRemoteNotification:(NSDictionary *)launchOptions
   {
       if( launchOptions )
       {
        ...
           [launchOptions objectForKey:@"VAR"];
       }
   }
   ```

>[!CAUTION]
>
>Adobe raadt u aan korte variabelenamen te kiezen, omdat de berichtgrootte voor iOS en Android beperkt is tot 4 kB.

## Uitbreiding meldingsservice {#notification-service-extension}

**Voor iOS**

De media moeten worden gedownload op het niveau van de berichtdienst uitbreiding.

```sql
#import "NotificationService.h"

@interface NotificationService ()

@property (nonatomic, strong) void (^contentHandler)(UNNotificationContent *contentToDeliver);
@property (nonatomic, strong) UNMutableNotificationContent *bestAttemptContent;

@end

@implementation NotificationService

- (void)didReceiveNotificationRequest:(UNNotificationRequest *)request withContentHandler:(void (^)(UNNotificationContent * _Nonnull))contentHandler {
    NSDictionary *userInfo = nil;
    NSString *url = nil;

    self.contentHandler = contentHandler;
    self.bestAttemptContent = [request.content mutableCopy];

    userInfo = request.content.userInfo;
    if ( userInfo != nil )
    {
        url = userInfo[@"mediaUrl"];  // Get the url of the media to download (Adobe Campaign additional variable)
    }
    ...
    // Perform the download to local storage
```

## Extensie meldingsinhoud {#notification-content-extension}

**Voor iOS**

Op dit niveau moet u:

* Wijs de extensie van de inhoud toe aan de categorie die door Adobe Campaign is verzonden:

   Als u wilt dat uw mobiele toepassing een afbeelding weergeeft, kunt u de categoriewaarde instellen op &quot;image&quot; in Adobe Campaign en in uw mobiele toepassing, maakt u een meldingsextensie met de parameter **UNNotificationExtensionCategory** ingesteld op &quot;image&quot;. Wanneer het pushbericht op het apparaat wordt ontvangen, wordt de extensie aangeroepen op basis van de gedefinieerde categoriewaarde.

* De lay-out voor uw melding definiëren

   U moet een lay-out definiëren met de relevante widgets. Voor een afbeelding krijgt de widget de naam **UIImageView**.

* Uw media weergeven

   U moet code toevoegen om de mediagegevens aan de widget te kunnen doorgeven. Hier volgt een voorbeeld van code voor een afbeelding:

   ```sql
   #import "NotificationViewController.h"
   #import <UserNotifications/UserNotifications.h>
   #import <UserNotificationsUI/UserNotificationsUI.h>
   
   @interface NotificationViewController () <UNNotificationContentExtension>
   
   @property (strong, nonatomic) IBOutlet UIImageView *imageView;
   @property (strong, nonatomic) IBOutlet UILabel *notifContent;
   @property (strong, nonatomic) IBOutlet UILabel *label;
   
   @end
   
   @implementation NotificationViewController
   
   - (void)viewDidLoad {
       [super viewDidLoad];
       // Do any required interface initialization here.
   }
   
   - (void)didReceiveNotification:(UNNotification *)notification {
       self.label.text = notification.request.content.title;
       self.notifContent.text = notification.request.content.body;
       UNNotificationAttachment *attachment = [notification.request.content.attachments objectAtIndex:0];
       if ([attachment.URL startAccessingSecurityScopedResource])
       {
         NSData * imageData = [[NSData alloc] initWithContentsOfURL:attachment.URL];
         self.imageView.image =[UIImage imageWithData: imageData];
         [attachment.URL stopAccessingSecurityScopedResource];
       }
   }
   @end
   ```
