---
title: Invoegtoepassing uitgebreide beveiliging voor campagne
description: Ga aan de slag met de uitgebreide beveiligingsinvoegtoepassing Campagne
feature: Configuration
role: Developer
level: Experienced
exl-id: 7c586836-82e1-45fb-9c28-18361572e1fa
source-git-commit: 24b252373923a9724743650b13a69d4f2c8dcd24
workflow-type: tm+mt
source-wordcount: '737'
ht-degree: 2%

---


# Invoegtoepassing uitgebreide beveiliging voor campagne {#enhanced-security}

Om uw netwerkverbinding veiliger te maken en betere veiligheid voor uw middelen te verstrekken, [!DNL Adobe Campaign] biedt een nieuwe **Verbeterde veiligheid** toe:voegen-op aan.

Deze invoegtoepassing bevat twee ecosysteemfuncties:

* [Veilige integratie van CMK (Customer Managed Key)](#secure-cmk-integration)

* [Beveiligd VPN-tunneling (Virtual Private Network)](#secure-vpn-tunneling)

Deze functies worden hieronder beschreven.

Enkele instructies en beperkingen met betrekking tot de uitgebreide beveiligingsfuncties worden op deze pagina weergegeven. Bovendien moet u ervoor zorgen al uw Veilige integratie CMK/Veilige het een tunnel graven van VPN gebruiksgevallen werken.

Als deze mogelijkheden eenmaal zijn geïmplementeerd, bewaakt Adobe:

* De beschikbaarheid van de instantie en ga verder met de waarschuwing als de sleutel niet beschikbaar is.

* De tunnels van VPN, en ga met het alarm te werk voor het geval om het even welke kwestie zich voordoet.

## Veilige integratie van sleutels die door de klant worden beheerd {#secure-cmk-integration}

De **Veilige Customer-Beheerde Zeer belangrijke (CMK) integratie** staat u toe om gegevens in rust te coderen gebruikend uw eigen sleutel door uw rekening van Amazon Web Services (AWS).

Door de klant beheerde sleutels zijn Key Management Service (KMS)-sleutels in uw AWS-account die u maakt, bezit en beheert. U hebt volledige controle over deze sleutels KMS, en gebruikt hen om gegevens te coderen en te decrypteren. Door u verantwoordelijk te maken voor het produceren en beheren van encryptiesleutels, laat deze capaciteit u toe om meer controle over hen te hebben, met inbegrip van het intrekken van een sleutel.

>[!CAUTION]
>
>Als u een sleutel intrekt, moet u zich bewust zijn van de effecten. [Meer informatie](#cmk-callouts)

Voer de volgende stappen uit om de CMK-integratie met Campagne in te schakelen:

1. Verbind met uw [ Amazon Web Services (AWS) ](https://aws.amazon.com/){target="_blank"} rekening.

1. Een sleutel met automatische rotatie genereren via de AWS Key Management Service (KMS). [ leer hoe ](https://docs.aws.amazon.com/kms/latest/developerguide/create-keys.html){target="_blank"}.

1. Pas het beleid toe dat Adobe u biedt op uw AWS-account, zodat u toegang hebt tot uw bronnen. [ leer meer ](https://docs.aws.amazon.com/kms/latest/developerguide/key-policy-services.html){target="_blank"}. <!--link TBC-->

1. Deel uw [ Naam van het Middel van Amazon (zeer belangrijke ARN) ](https://docs.aws.amazon.com/kms/latest/developerguide/find-cmk-id-arn.html){target="_blank"} met [!DNL Adobe Campaign]. Neem hiervoor contact op met uw Adobe-vertegenwoordiger. <!--or Adobe transition manager?-->

1. Maak en test de Amazon EventBridge-regels om het controleren van uw sleutels door Adobe mogelijk te maken. &#x200B; [Meer informatie](https://docs.aws.amazon.com/eventbridge/latest/userguide/eb-rules.html){target="_blank"}.


### Afvoerkanalen en beperkingen {#cmk-callouts}

De volgende instructies en beperkingen zijn van toepassing op de CMK-integratie met Adobe Campaign v8:

* Adobe verstrekt geen [ Amazon Web Services (AWS) ](https://aws.amazon.com/){target="_blank"} rekening. U moet uw eigen AWS-account hebben en deze instellen om uw sleutel te genereren en te delen met Adobe.

* Slechts worden de slechts ](https://docs.aws.amazon.com/kms/latest/developerguide/overview.html){target="_blank"} (KMS) sleutels van de Dienst van het Beheer van AWS Key gesteund. [ Er kunnen geen door de klant gegenereerde sleutels buiten KMS worden gebruikt. &#x200B;

* Downtime wordt verwacht tijdens de eerste installatie. &#x200B;De downtime is afhankelijk van de grootte van de database.

* Als klant hebt u de sleutel en houdt u deze bij. Je moet Adobe bereiken voor het geval je sleutel verandert. &#x200B;

* U kunt uw sleutel controleren gebruikend [ AWS CloudTrail ](https://docs.aws.amazon.com/awscloudtrail/latest/userguide/cloudtrail-user-guide.html){target="_blank"} en het herroepen indien nodig. &#x200B;

* Als u de sleutel intrekt, uitschakelt of verwijdert, zijn de gecodeerde bronnen en instanties pas toegankelijk als u de bijbehorende actie hebt teruggezet.

  >[!CAUTION]
  >
  >Als u de toets uitschakelt en deze handeling niet binnen 7 dagen terugzet, kan uw database alleen worden hersteld vanaf een back-up.
  >
  >Als u de sleutel verwijdert en deze actie niet binnen 30 dagen terugzet, worden al uw gegevens definitief verwijderd en verloren. &#x200B;

## Beveiligd Virtual Private Network-tunneling {#secure-vpn-tunneling}

Het **Veilige Virtuele Privé Netwerk (VPN) het een tunnel graven** is plaats-aan-plaats VPN dat veilige toegang voor uw gegevens in doorvoer over een privé netwerk, van uw gebouwen aan de [!DNL Adobe Campaign] instantie verleent.

<!--As it connects two networks together, it is a site-to-site VPN.-->

Om hoge beschikbaarheid (HA) te verzekeren, gebruikt het twee tunnels om elke stroomonderbreking te vermijden in het geval een kwestie op één tunnel gebeurt.

Er worden drie gebruiksgevallen ondersteund:

* Federated Data Access (FDA) via VPN, om toegang te krijgen tot uw on-premise database via de Campagne-instantie via VPN

* Inloggen van de instantie via VPN van een dikke cliënt

* Instance SFTP-toegang via VPN

>[!CAUTION]
>
>Alleen on-premise databases en AWS-compatibele VPN-apparaten worden ondersteund. [Meer informatie](#vpn-databases)

Volg onderstaande richtlijnen om ervoor te zorgen dat deze functie correct wordt gebruikt:

* Opstelling uw kant VPN die op de configuratie van Adobe-kantVPN wordt gebaseerd.

* Houd beide tunnels omhoog voor Hoge Beschikbaarheid.

* Controleer uw zijtunnel.

* U moet de initiatiefnemer van de tunnel zijn, en worden gericht om de verbinding opnieuw in werking te stellen als de tunnel daalt.

* Stel een mechanisme voor opnieuw proberen in als er verbindingsfouten optreden.

### Ondersteunde databases en apparaten {#vpn-databases}

De volgende databases op locatie worden ondersteund:

* MySQL
* Netezza
* Oracle
* SAP HANA
* SQL Server
* Sybase
* Teradata
* Hadoop via HiveSQL

Alleen AWS-compatibele VPN-apparaten worden ondersteund. Een lijst van compatibele apparaten is beschikbaar op [ deze pagina ](https://docs.aws.amazon.com/vpn/latest/s2svpn/your-cgw.html#example-configuration-files){target="_blank"}.

>[!NOTE]
>
>* De connectiviteit van VPN aan derden of externe verkopers wordt niet gesteund.
>
>* Door Adobe beheerde extra VPN&#39;s naar privéCloud-databases worden niet opgenomen.
