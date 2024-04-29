---
title: Invoegtoepassing voor uitgebreide beveiliging
description: Ga aan de slag met de uitgebreide beveiligingsinvoegtoepassing Campagne
feature: Configuration
role: Developer
level: Experienced
hide: true
hidefromtoc: true
source-git-commit: cec935c2c73e3df4d2e03d54305004df9bd2655e
workflow-type: tm+mt
source-wordcount: '643'
ht-degree: 1%

---


# Invoegtoepassing voor uitgebreide beveiliging {#enhanced-security}

Om uw netwerkverbinding veiliger te maken en betere veiligheid voor uw middelen te verstrekken, [!DNL Adobe Campaign] biedt nieuwe **Uitgebreide beveiliging** invoegtoepassing.

Deze invoegtoepassing bevat momenteel twee ecosysteemfuncties:

* [Secure CMK-integratie](#secure-cmk-integration)

* [Veilige VPN-tunneling](#secure-vpn-tunneling)

## Secure CMK-integratie {#secure-cmk-integration}

**Veilige integratie van CMK (Customer Managed Key)** staat u toe om uw instantie en uw gegevens te coderen gebruikend uw eigen sleutel door uw AWS rekening<!--instead of Adobe-owned keys-->. Door u verantwoordelijk te maken voor het produceren en beheren van encryptiesleutels, laat deze capaciteit u toe om meer controle over hen te hebben, met inbegrip van het intrekken van een sleutel.

>[!CAUTION]
>
>Als u een sleutel intrekt, moet u zich bewust zijn van de effecten. [Meer informatie](#cmk-callouts)

Volg onderstaande stappen om deze functie in te schakelen:

1. Zorg ervoor dat u een [AWS](https://aws.amazon.com/){target="_blank"} account.

1. Een sleutel met automatische rotatie genereren via de AWS Key Management Service (KMS). [Meer informatie](https://docs.aws.amazon.com/kms/latest/developerguide/create-keys.html){target="_blank"}

1. Pas het beleid toe dat u via Adobe hebt ontvangen op uw AWS-account, zodat u toegang hebt tot uw bronnen. [Meer informatie](https://docs.aws.amazon.com/kms/latest/developerguide/key-policy-services.html){target="_blank"} <!--link TBC-->

1. Amazon Resource Name (key ARN) delen met [!DNL Adobe Campaign]. Neem hiervoor contact op met uw Adobe. <!--or Adobe transition manager?-->

1. Maak en test de Amazon EventBridge-regels om het controleren van uw toetsen op Adobe in te schakelen. &#x200B; [Meer informatie](https://docs.aws.amazon.com/eventbridge/latest/userguide/eb-rules.html){target="_blank"}

## Veilige VPN-tunneling {#secure-vpn-tunneling}

**Beveiligd VPN-tunneling (Virtual Private Network)** is plaats-aan-plaats VPN dat veilige toegang voor uw gegevens in doorvoer over een privé netwerk, van uw gebouwen aan het [!DNL Adobe Campaign] -instantie.

<!--As it connects two networks together, it is a site-to-site VPN.-->

Om hoge beschikbaarheid (HA) te verzekeren, gebruikt het twee tunnels om elke stroomonderbreking te vermijden in het geval een kwestie op één tunnel gebeurt

Er worden drie gebruiksgevallen ondersteund:

* FDA boven VPN<!--to access your on-premise database from the Campaign instance over VPN-->

* Inloggen van de instantie via VPN van een dikke cliënt

* Instance SFTP-toegang via VPN

>[!CAUTION]
>
>Alleen on-premise databases en AWS-compatibele VPN-apparaten worden ondersteund. [Meer informatie](#vpn-callouts)

Volg onderstaande richtlijnen om ervoor te zorgen dat deze functie correct wordt gebruikt:

* Opstelling uw kant VPN die op de Adobe-kant configuratie van VPN wordt gebaseerd.

* Houd beide tunnels omhoog voor HA.

* Controleer uw zijtunnel.

* U moet de initiatiefnemer van de tunnel zijn, en worden gericht om de verbinding opnieuw in werking te stellen als de tunnel daalt.

* Stel een mechanisme voor opnieuw proberen in als er verbindingsfouten optreden.

## Guardrails {#callouts}

Enkele instructies en beperkingen met betrekking tot de uitgebreide beveiligingsfuncties worden hieronder vermeld.

* Zorg ervoor al uw Veilige integratie CMK/Veilige het een tunnel graven van VPN gebruiksgevallen werkt.

<!--* Adobe shall reach out to you or your technical team if any issue is found on your side.

* Currently, when using Enhanced security features, any communication with Adobe must be performed manually via email.-->

* de Adobe zal toezien op :

   * De beschikbaarheid van de instantie en ga verder met de waarschuwing als de sleutel niet beschikbaar is.

   * De tunnels van VPN, en ga met het alarm te werk voor het geval om het even welke kwestie zich voordoet.

### Beveiligde CMK-integratiegaranties {#cmk-callouts}

* Adobe levert geen AWS-account. U moet uw eigen AWS-account hebben en deze instellen om uw sleutel te genereren en met Adobe te delen.

* Alleen [AWS Key Management Service](https://docs.aws.amazon.com/kms/latest/developerguide/overview.html){target="_blank"} (KMS)-toetsen worden ondersteund. Er kunnen geen door de klant gegenereerde sleutels buiten KMS worden gebruikt. &#x200B;

* Voor de eerste keer wordt een aantal downtime gebruikt. &#x200B;De downtime is afhankelijk van de grootte van de database.

* Aangezien u bezit en de sleutel handhaaft, moet u naar Adobe in het geval van om het even welke verandering in uw sleutel reiken. &#x200B;

* U kunt uw sleutel controleren gebruikend [AWS CloudTrail](https://docs.aws.amazon.com/awscloudtrail/latest/userguide/cloudtrail-user-guide.html){target="_blank"} en herroepen indien nodig. &#x200B;

* Als u de sleutel intrekt, uitschakelt of verwijdert, zijn de gecodeerde bronnen en instanties pas toegankelijk als u de bijbehorende actie hebt teruggezet.

  >[!CAUTION]
  >
  >Als u de toets uitschakelt en deze handeling niet binnen 7 dagen terugzet, kan uw database alleen worden hersteld vanaf een back-up.
  >
  >Als u de sleutel verwijdert en deze actie niet binnen 30 dagen terugzet, worden al uw gegevens definitief verwijderd en verloren. &#x200B;

### Beveiligde VPN-tunneling-handleidingen {#vpn-callouts}

* Momenteel worden alleen on-premise databases ondersteund, zoals<!--Richa to check the list with PM-->:

   * MySQL
   * Netezza 
   * Oracle 
   * SAP HANA 
   * SQL Server 
   * Sybase 
   * Teradata 
   * Hadoop via HiveSQL

* Alleen AWS-compatibele VPN-apparaten worden ondersteund. Een lijst met compatibele apparaten is beschikbaar op [deze pagina](https://docs.aws.amazon.com/vpn/latest/s2svpn/your-cgw.html#example-configuration-files){target="_blank"}<!--check which list should be communicated-->.

* De connectiviteit van VPN aan derden of externe verkopers wordt niet gesteund.

* Adobe-beheerde extra VPNs aan privé gegevensbestanden van de Wolk is niet inbegrepen.
