---
title: Migratie van technische gebruikers naar Adobe Developer-console
description: Leer hoe u het beheer van gebruikerstoegang kunt migreren van Campaign Standard naar Campagne V8
feature: Technote
role: Admin
source-git-commit: ccd60b7ff54bb538ae21693eff41a3943f1c6c88
workflow-type: tm+mt
source-wordcount: '839'
ht-degree: 1%

---

# Toegangsbeheer van gebruikers van Campaign Standard tot Campagne V8 {#user-management-acs}

Zowel Adobe Campaign Standard als Adobe Campaign V8 stellen gebruikers in staat machtigingen voor verschillende gebruikers/operatoren te definiëren en te beheren. Deze toestemmingen bestaan uit specifieke rechten die gebruikers toegang tot diverse eigenschappen van het product verlenen. Nochtans, gebruiken de twee producten verschillende benaderingen en implementaties voor het beheren van gebruikerstoegang.

De volgende concepten worden gebruikt in Adobe Campaign Standard en Campagne V8 om tot beheer van de gebruikerstoegang te komen:

| Campaign Standard | Campagne V8 |
|---------|----------|
| Gebruiker | Operator |
| Rol | Benoemd rechts |
| Beveiligingsgroep | Operator Group |
| Organisatorische eenheid | Mapmachtiging |

## Migratieaanpak van beveiligingsgroep naar operatorgroep

>[!CAUTION]
>
>De mogelijkheden van deze rollen/Benoemde rechten kunnen in implementatie variëren, wat machtigingsproblemen kan veroorzaken (bijvoorbeeld verhoging van bevoegdheden of functieonderbrekingen). Wij adviseren gebruikers om deze afbeeldingen na de overgang te herzien om behoorlijk toegangsbeheer te verzekeren. [ Leer meer op toestemmingen ](../../v8/start/manage-permissions.md)

De onderstaande tabel geeft een overzicht van de migratiebenadering voor gebruikersrolgroepen bij de overgang van Adobe Campaign Standard naar Campagne V8. In Campaign Standard, wordt de groep van de a **Veiligheid**, die als **wordt bedoeld groep van de Exploitant** in Campagne V8, gebruikt om een reeks rollen aan een gebruiker toe te wijzen. Terwijl sommige veiligheidsgroepen/exploitantgroepen uit-van-de-doos beschikbaar zijn, kunnen de gebruikers nieuwe groepen tot stand brengen of bestaande te wijzigen indien nodig.

| | **Campaign Standard** | **Campagne V8** |
|---------|----------|---------|
| **Terminologie**  | Beveiligingsgroep | Operator Group |

In zowel Adobe Campaign Standard als Campagne V8, **de groepen van de Veiligheid** en **groepen van de Exploitant** worden in kaart gebracht aan de profielen van het Product in de console Admin. Als u de groep van de a **Veiligheid** of **Exploitant** aan een gebruiker wilt toewijzen, kunt u het overeenkomstige **profiel van het Product** in de console Admin verbinden. Deze koppeling wordt gesynchroniseerd wanneer de gebruiker zich aanmeldt. [ leer meer op het profiel van het Product ](../../v8/start/manage-permissions.md)

| **de groep van de Veiligheid van het Campaign Standard** | **de groep van de Exploitant van de Campagne V8** |
|----------|---------|
| Beheerders | Beheerders |
| Afleveringstoezichthouders | Beheerders |
| Workflowsupervisors | Workflowsupervisors  |

## Migratiebenadering van gebruikersrollen naar benoemde rechten

In Adobe Campaign Standard, wordt de termijn **rol van de Gebruiker** bedoeld als **Benoemd recht** in Campagne V8. De lijst beschrijft hieronder de terminologie die voor **wordt gebruikt Genoemde rechten** in Campagne V8 die aan **gebruikersrollen** in Campaign Standard beantwoordt.

| **de rol van de Gebruiker van het Campaign Standard** | **Campagne V8 Genoemd recht** | **Beschrijving**  |
|----------|---------|---------|
| Beheer | Beheer | De gebruiker met het recht van het Beleid heeft volledige toegang tot de instantie. |
| Gegevensmodel  | Beheer | Recht om publicaties te leiden en douanemiddelen tot stand te brengen. Functionaliteit voor het maken van schema&#39;s beschikbaar voor Admin in Campagne V8.  |
| Leverbaarheid  | Administratie  | Recht om eerder geanalyseerde leveringen goed te keuren.  |
| Exporteren | Exporteren | Recht op het exporteren van gegevens.  |
| Bestandstoegang  | Toegang tot bestanden  | Recht om eerder geanalyseerde leveringen goed te keuren.  |
| Generieke import  | Importeren  | Recht op het importeren van generieke gegevens |
| Leveringen voorbereiden | Leveringen voorbereiden | Recht om leveringen te maken, te wijzigen, voor te bereiden en te verwijderen.  |
| SQL-scriptuitvoering | SQL-scriptuitvoering | Recht om het even welk SQL bevel direct op het gegevensbestand uit te voeren. |
| Leveringen starten  | Leveringen starten  | Recht om eerder geanalyseerde leveringen goed te keuren.  |
| Uitvoering systeemopdracht | Uitvoering van programma | Recht om systeembevelen op de server uit te voeren. |
| Workflow | Workflow | Recht om de uitvoering van workflows te beheren: starten, stoppen, pauzeren, enz. |

## Migratieaanpak van de organisatie-eenheid

In Adobe Campaign Standard, wordt de **organisatie uni** niet in kaart gebracht aan het bestaande **de hiërarchiemodel van de Omslag** in Campagne V8 om gelijkaardige toegangscontrole te handhaven. [ Leer meer op omslagbeheer ](../../v8/start/folder-permissions.md)

| | **Campaign Standard** | **Campagne V8** |
|---------|----------|---------|
| **Terminologie**  | Organisatorische eenheid | Map |

## Migratiebenadering van het programma

In Campagne V8, **Programma&#39;s** worden vertegenwoordigd als **Omslagen**. Met campagne V8 kunnen mappen worden gemaakt en is de toegang tot deze mappen beperkt.

Door **Groepen** en **Genoemde rechten** te gebruiken, **de Exploitanten** kunnen toegang tot specifieke **Omslagen** binnen de navigatiehiërarchie, met de capaciteit worden verleend om gelezen toe te wijzen, te schrijven en toestemmingen te schrappen. [ Leer meer op omslagbeheer ](../../v8/start/folder-permissions.md)

Aangezien a **Programma** als a **Omslag** in Campagne V8 wordt behandeld, kan zijn toegang op de zelfde manier zoals een andere omslag worden beheerd. Na de migratie kunnen beheerders van Campaigns Standard de volgende stappen uitvoeren:

1. Klik in de verkenner met de rechtermuisknop op een willekeurige map en selecteer **[!UICONTROL Properties...]** .
1. Ga naar het tabblad **[!UICONTROL Security]**.
1. Wijzig de toestemmingen van de exploitantgroep volgens het gewenste toegangsmodel. 

## Productprofieltoewijzing voor toegang tot REST API&#39;s 

Om tot transactie APIs van de uitvoeringsinstantie in Campagne V8 toegang te hebben, wordt een nieuw **profiel van het Product** vereist, naast de **Beheerder** en **het productprofielen van het Centrum van het Bericht**. Dit nieuwe **profiel van het Product** zal aan bestaande of vooraf gecreëerde technische rekeningen in Campaign Standard worden toegevoegd.

Na migratie, zouden de gebruikers van het Campaign Standard hun **afbeeldingen van het Profiel van het Product** moeten herzien en het aangewezen **Profiel van het Product** toewijzen als zij niet hun **Technische rekeningen** aan het **Profiel van het Product van de Beheerder** wensen te verbinden. Voor toekomstige integratie, adviseren wij het gebruiken van Campagne V8 **identiteitskaart van de Huurder** in **REST URL** in plaats van vorige Campaign Standard **identiteitskaart van de Huurder**.

## Migratie van de toegang tot ingebouwde campagnebronnen voor Campaigns Standard

Operatoren die vanuit Campaign Standard zijn gemigreerd, hebben leestoegang tot specifieke ingebouwde bronnen in Campagne V8.

## Niet-gemigreerde veiligheidsgroepen en rollen {#non-migrated-groups-roles}

Hieronder volgt een lijst met rollen van Campaigns Standard die niet zijn overgezet:

* Standaard-releaseaccount 

* Berichten centreren 

Hieronder ziet u een lijst met toewijzingen voor beveiligingsgroepen van Campaigns Standard die niet zijn overgezet.

* Berichtencentrum

* Message Center Push Agents

* Adobe Experience Manager-toepassingsmanagers

* Account terugbetalen
 


 

 


