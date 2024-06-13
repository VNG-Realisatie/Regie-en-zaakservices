---
layout: page-with-side-nav
title: Compliancy Regie- en zaakservices
---
# Compliancy Regie- en zaakservices

|   |   |
| --- | --- |
| Testsetversie: | 1.0 |
| Status | In gebruik |
| Datum laatst gewijzigd | 2 juli 2014 |

## Inleiding

De standaard [Regie en zaakservices 1.0](https://vng-realisatie.github.io/Regie-en-zaakservices/Documentatie) is op 7 oktober 2015 formeel vastgesteld door de StUF Regiegroep. Daarmee heeft de standaard de status ‘In gebruik’ en wordt gemeenten aanbevolen om deze standaard te gebruiken.

Voor een juiste toepassing van de standaard Regie en zaakservices worden door VNG Realisatie compliancy instrumenten ontwikkeld met als doel interoperabiliteitsproblemen tussen applicaties bij gemeenten preventief te verminderen. In de paragraaf 2.1 ”Wanneer is een softwareproduct compliant” is aangegeven wanneer een softwareproduct compliant is aan de Regie en zaakservices 1.0.

<!--VNG Realisatie adviseert gemeenten bij aanschaf van software die moet voldoen aan deze standaard gebruik te maken van de [Handreiking Levering en Acceptatievoorwaarden ICT](documenten/130131_Leverings_en_acceptatievoorwaarden_versie_2_Definitief.pdf). Daarin zijn voorwaarden opgenomen over het gebruik van compliancy instrumenten.-->

Op 1 juni 2014 heeft VNG Realisatie de technische professionals van leveranciers tekst en uitleg gegeven over het deze testset en het gebruik van het StUF Testplatform. Onderliggend document maakt deel uit van de compliancy instrumenten van VNG Realisatie.

## Doel van document
Doel van dit document is het definiëren van een standaard testset voor het testen van koppelingen die gebaseerd zijn op de Regie en zaakservices 1.0. Deze testset beschrijft de tests die minimaal voorafgaand aan het in productie nemen van (aangepaste of nieuwe) software door de betreffende softwareleverancier uitgevoerd moeten worden.

De testen dienen uitgevoerd te worden conform deze beschrijving en met behulp en conform de voorwaarden van het StUF Testplatform. Voor gebruik van deze testset is een abonnement nodig op het StUF Testplatform nodig. Organisaties dienen zich, voor zover ze nog geen abonnement hebben, aan te melden. Zie: [StUF Testplatform](http://www.stuftestplatform.nl).

Indien voldaan wordt aan alle compliancy eisen uit kan de betreffende leverancier aangeven dat het geteste softwareproduct compliant is aan de Regie en zaakservices 1.0.

## Wanneer is een softwareproduct compliant
Een softwareproduct is compliant aan de Regie en zaakservices 1.0 (*), indien aan alle onderstaande vijf eisen wordt voldaan:

| Nr  | Eis |
|---- |---- |
| 1	  | Het betreffende softwareproduct getest is conform de eisen en voorwaarden uit onderliggende document inclusief de bijlagen en |
| 2	  | De uitvoering heeft plaatsgevonden op en conform de voorwaarden van het StUF testplatform en |
| 3	  | Een foutloos testresultaat is behaald en |
| 4	  | Finale en authentieke testrapporten openbaar zijn gemaakt op het internet en |
| 5	  | In de [GEMMA softwarecatalogus](https://www.softwarecatalogus.nl/) heeft u het authentieke testrapport uit stap 4 gepubliceerd bij het betreffende softwareproduct en aangegeven (aangevinkt) dat u compliant bent. |

(*) Hoewel een foutloos testresultaat van deze testset geen absolute zekerheid geeft van 100% interoperabiliteit tussen applicaties, geeft dit wel een goede indicatie van de kwaliteit van de ondersteuning van de standaard.

## Specificatie van testset
Leveranciers van gemeentelijke software dienen koppelingen te leveren die volledig voldoen aan de standaard. Afhankelijk van de GEMMA referentiecomponent(en) die een softwareproduct invult binnen het toepassingsgebied van de standaard, stelt de standaard andere eisen. Daardoor is de testscope niet voor alle applicaties gelijk.

De specificatie beschrijft services voor de volgende referentiecomponenten:

* Zaaksysteem
* Zakenmagazijn
* Documentbeheersysteem
* Gemeentelijke servicebus
* Abonnementenbeheer (nieuw gedefinieerd)
* Regiesysteem
* Sectorspecifieke backoffice-applicaties (niet limitatief)
  * Budgetadvies en schuldbemiddeling
  * Inburgeringadministratie
  * Leerlingenbeheer
  * Leerlingvervoer
  * Loket voortijdig schoolverlater (RMC)
  * Re-integratie en werkzoekendenadministratie
  * Subsidies
  * Wmo-voorzieningenadministratie
  * WWB-ondersteuning
  * -

Voor een omschrijving van wat het betreffende referentiecomponent inhoudt en welke softwareproducten van welke leveranciers daar invulling aan geven, wordt verwezen naar de [GEMMA Softwarecatalogus](http://www.gemmasoftwarecatalogus.nl/).

<img src="./images/Regie_en_zaakservices_architectuur.png" width="800"/>

## Consumer en provider testen
Bij elke test is middels een P of C aangegeven of het een Provider of Consumer test betreft. Bij een provider test moet de te testen applicatie een service beschikbaar stellen aan het StUF Testplatform; het StUF Testplatform zal één of meerdere berichten versturen naar de te testen applicatie. In geval van een consumer test levert het StUF Testplatform een service aan de te testen applicatie. De te testen applicatie moet in deze gevallen één of meerdere berichten versturen naar het StUF Testplatform. Afhankelijk of een test een provider of consumer test is verwacht het StUF Testplatform dus een bericht van de te testen applicatie of verstuurt het StUF Testplatform een bericht naar de te testen applicatie.

<img src="./images/Interactiepatroon.png" width="900"/>

In de volgende paragrafen wordt per referentiecomponent/rol(*) beschreven welke testen uitgevoerd moeten worden, de testscope. Indien een softwareproduct invulling geeft aan meerdere referentiecomponenten dan is de testscope voor het softwareproduct gelijk aan de gezamenlijke testscope van alle ingevulde referentiecomponenten. Bijvoorbeeld, als een softwareproduct zowel de functionaliteit levert van de referentiecomponent Zaaksysteem als van een Document Management systeem, dan dienen zowel de testen van het referentiecomponent Zaaksysteem als Document Management systeem uitgevoerd te worden.

*Een rol kan gezien worden als een groep van referentiecomponenten die dezelfde generieke functionaliteit bieden. Een voorbeeld hiervan is de Zaakservice consumer. Indien een softwareproduct de rol van Zaakservice consumer invult dan betekent dit dat in dit softwareproduct zaakgerelateerde informatie ontstaat of wordt aangepast en dat deze informatie volgens de services uit de Zaak- en Documentservices wordt ontsloten naar een Zaaksysteem. Vrijwel elk softwareproduct kan de rol van Zaakservice consumer invullen. Denk aan vergunningsystemen, handhavingssystemen, uitkeringensysteem etc.

## Testscope Zaaksysteem
Indien een softwareproduct invulling geeft aan de referentiecomponent Zaaksysteem, dan moet op het StUF Testplatform de testset Zaak en Regieservices uitgevoerd worden voor de rol Zaaksysteem.

Tijdens de testset uitvoering mogen geen fouten geconstateerd worden door het StUF Testplatform.

Er worden berichten naar het te testen softwareproduct gestuurd waarin zowel verplichte als optionele elementen voorkomen. Tijdens de testuitvoering worden de volgende services getest:

1. genereerZaakIdentificatie (P)
2. creeerZaak (P) - Gezinsplan
3. creeerZaak (P) - Levensdomeinplan
4. creeerZaak (P) - Deelplan
5. genereerDocumentidentificatie (P)
6. voegZaakdocumentToe (P)
7. geefZaakdocumentbewerken (P)
8. updateZaakdocument (P)
9. updateZaak (P) - Gezinsplan
10. updateZaak (P) - Levensdomeinplan
11. updateZaak (P) - Deelplan
12. actualiseerZaakstatus (P)
13. geefZaakstatus (P)
14. geefZaakdetails (P)
15. geefLijstZaakdocumenten (P)
16. geefZaakdocumentLezen (P)

## Testscope Regiesysteem
Indien een softwareproduct invulling geeft aan de referentiecomponent Regiesysteem dan moet op het StUF Testplatform de testset Zaak en Regieservices uitgevoerd worden voor de rol Regiesysteem.

Tijdens de testset uitvoering mogen geen fouten geconstateerd worden door het StUF Testplatform.

Er worden berichten naar het te testen softwareproduct gestuurd waarin zowel verplichte als optionele elementen voorkomen. Tijdens de testuitvoering worden de volgende services getest:

1. genereerZaakidentificatie en creëerZaak (C) - Gezinsplan
2. genereerZaakidentificatie en creëerZaak (C) - Levensdomeinplan
3. genereerZaakidentificatie en creëerZaak (C) - Deelplan
4. genereerDocumentidentificatie (C)
5. voegZaakdocumentToe (C)
6. geefZaakdocumentBewerken (C)
7. updateZaakdocument (C)
8. updateZaak (C) - Gezinsplan
9. updateZaak (C) - Levensdomeinplan
10. updateZaak (C) - Deelplan
11. actualiseerZaakstatus (C)
12. notificeerOverZaak (P)
13. geefZaakstatus (C)
14. geefZaakdetails (C)
15. geefLijstZaakdocumenten (C)
16. geefZaakdocumentLezen (C)
17. overdragenZaak (C)

## Testscope Zaakmagazijn
Indien een softwareproduct invulling geeft aan de referentiecomponent Zaakmagazijn, dan moet op het StUF Testplatform de testset Zaak en Regieservices uitgevoerd worden voor de rol Zaakmagazijn.

Tijdens de testset uitvoering mogen geen fouten geconstateerd worden door het StUF Testplatform.

Er worden berichten naar het te testen softwareproduct gestuurd waarin zowel verplichte als optionele elementen voorkomen. Tijdens de testuitvoering worden de volgende services getest:

1. genereerZaakIdentificatie (P)
2. creeerZaak (P) - Gezinsplan
3. creeerZaak (P) - Levensdomeinplan
4. creeerZaak (P) - Deelplan
5. genereerDocumentidentificatie (P)
6. voegZaakdocumentToe (P)
7. updateZaakdocument (P)
8. updateZaak (P) - Gezinsplan
9. updateZaak (P) - Levensdomeinplan
10. updateZaak (P) - Deelplan
11. actualiseerZaakstatus (P)
12. geefZaakstatus (P)
13. geefZaakdetails (P)
14. geefLijstZaakdocumenten (P)
15. geefZaakdocumentLezen (P)

## Testscope Documentbeheer systeem
Er zijn geen aanvullende compliancy tests gedefinieerd.

## Testscope Gemeentelijke servicebus
Indien een softwareproduct invulling geeft aan de referentiecomponent Gemeentelijke servicebus, dan moet op het StUF Testplatform de testset Zaak en Regieservices uitgevoerd worden voor de rol Gemeentelijke servicebus.

Tijdens de testset uitvoering mogen geen fouten geconstateerd worden door het StUF Testplatform.

Er worden berichten naar het te testen softwareproduct gestuurd waarin zowel verplichte als optionele elementen voorkomen. Tijdens de testuitvoering worden de volgende services getest:

1. initieerNotificeerOverZaak (C)

## Testscope Abonnementenbeheer
Indien een softwareproduct invulling geeft aan de referentiecomponent Abonnementenbeheer, dan moet op het StUF Testplatform de testset Zaak en Regieservices uitgevoerd worden voor de rol Abonnementenbeheer.

Tijdens de testset uitvoering mogen geen fouten geconstateerd worden door het StUF Testplatform.

Er worden berichten naar het te testen softwareproduct gestuurd waarin zowel verplichte als optionele elementen voorkomen. Tijdens de testuitvoering worden de volgende services getest:

1. initieerNotificeerOverZaak (creeer zaak) (P)
2. notificeerOverZaak (creeer zaak) (C)
3. initieerNotificeerOverZaak (document) (P)
4. notificeerOverZaak (document) (C)
5. initieerNotificeerOverZaak (update zaak) (P)
6. notificeerOverZaak (update zaak) (C)
7. initieerNotificeerOverZaak (zaakstatus) (P)
8. notificeerOverZaak (zaakstatus) (C)
9. initieerNotificeerOverZaak (update zaakdocument) (P)
10. notificeerOverZaak (update zaakdocument) (C)

## Testscope Sectorspecifieke backoffice-applicaties
Indien een softwareproduct invulling geeft aan de referentiecomponent Sectorspecifieke backoffice-applicaties, dan moet op het StUF Testplatform de testset Zaak en Regieservices uitgevoerd worden voor de rol Taakspecifieke applicatie.

Tijdens de testset uitvoering mogen geen fouten geconstateerd worden door het StUF Testplatform.

Er worden berichten naar het te testen softwareproduct gestuurd waarin zowel verplichte als optionele elementen voorkomen. Tijdens de testuitvoering worden de volgende services getest:

1. genereerZaakIdentificatie (C)
2. creeerZaak (C) - Gezinsplan
3. creeerZaak (C) - Levensdomeinplan
4. creeerZaak (C) - Deelplan
5. genereerDocumentidentificatie (C)
6. voegZaakdocumentToe (C)
7. geefZaakdocumentbewerken (C)
8. updateZaakdocument (C)
9. updateZaak (C) - Gezinsplan
10. updateZaak (C) - Levensdomeinplan
11. updateZaak (C) - Deelplan
12. actualiseerZaakstatus (C)
13. notificeerOverZaak (C)
14. geefZaakstatus (C)
15. geefZaakdetails (C)
16. geefLijstZaakdocumenten (C)
17. geefZaakdocumentLezen (C)
18. overdragenZaak (P)

## Beschrijving testset scenario’s
De testscenario’s behorende bij deze testset zijn beschreven in een spreadsheet.

Per referentiecomponent/rol is een tabblad opgenomen waar u de testscenario’s vindt die relevant zijn voor softwareproducten die deze referentiecomponent/rol invullen. Een testscenario beschrijving bestaat uit een sequence diagram (in UML) en een tabel waarin wordt toegelicht welke acties uitgevoerd moeten worden en wat daarbij het resultaat moet zijn.

<img src="./images/Testscenario_afbeelding_1.png" width="800"/>

Afbeelding 2: voorbeeld scenariobeschrijving

Het sequence diagram geeft aan in welke volgorde de berichten verstuurd moeten worden door het StUF Testplatform of de te testen applicatie. De rode bolletjes geven de scenariostappen weer.

<img src="./images/Testscenario_afbeelding_2.png" width="500"/>

Afbeelding 3: voorbeeld sequence diagram

## Gebruik van het StUF Testplatform

Het StUF Testplatform is een onafhankelijk en formeel toetsinginstrument voor het testen van koppelingen gebaseerd op standaarden uit de StUF familie. Het platform is vanaf eind 2011 in productie en wordt beheerd en doorontwikkeld door VNG Realisatie.

Primair is het StUF Testplatform voor ICT softwareleveranciers die werkzaam zijn op de gemeentelijke markt. Zij kunnen vroegtijdig tijdens de ontwikkeling van software testen of applicatie-applicatiekoppelingen voldoen aan StUF. Leveranciers worden geacht een (preventieve) test uit te voeren op het StUF Testplatform voordat een softwareproduct in productie wordt genomen.

In de [handleiding StUF Testplatform](./documenten/Gebruikershandleiding_StUF_Testplatform.pdf) wordt verder toegelicht hoe het testplatform gebruikt kan worden.
