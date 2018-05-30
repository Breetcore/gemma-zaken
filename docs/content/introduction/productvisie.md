# ZAKEN Productvisie ZDS

## Inhoud
* [Introductie](#introductie)
* [Productvisie ZDS](#productvisie-zds)
* [Centraal aanbieden](#centraal-aanbieden)
* [Uitgangspunten](#uitgangspunten)
* [Realisatie](#realisatie)
* [Gerelateerde trajecten](#gerelateerde-trajecten)


## Introductie

Om Zaakgericht Werken een stap verder te brengen worden Zaak- en Documentservices (ZDS) versie 2 ontwikkeld. Hierbij wordt een andere vorm van standaardisatie toegepast. Op basis van een gegeven informatiemodel (RGBZ 2) wordt met zowel publieke als private partijen in een agile proces vorm gegeven aan RESTful API's die concreet invulling geven aan de gewenste standaard. De standaard wordt tegelijk met een referentie-implementatie ontwikkeld om de implementeerbaarheid aan te tonen, en als referentie te dienen voor latere implementaties. 

Binnen de Gemeentelijke Model Architectuur (GEMMA) versie 2 is het [Katern Zaakgericht Werken](https://www.gemmaonline.nl/index.php/GEMMA_2_Katern_Zaakgericht_Werken) beschikbaar. Hierin wordt uitvoerig beschreven hoe Zaakgericht Werken bedoeld is. Dit is verder uitgewerkt in de GEMMA Informatiearchitectuur in o.a. [referentiecomponenten en Integratiepatronen Zaakgericht werken](https://www.gemmaonline.nl/index.php/ZGW_in_GEMMA_2).

Vanaf mei 2018 wordt met een aantal partijen [samengewerkt](./samenwerking.md) aan realisatie van de "ZDS 2.0" [1].

_[1]: De naam Zaak- en Documentservices (ZDS) wordt gebruik om duidelijk te maken wat het uitgangspunt is maar er worden uiteindelijk wellicht aparte API's ontwikkeld in het kader van de Common Ground visie._


## Productvisie ZDS

De visie op de te realiseren Zaak- en Documentservices is als volgt:

- De services worden vormgegeven op basis van heldere user stories ontleend aan de praktijk, dus op basis van daadwerkelijk gebruik in plaats van op basis van een theoretische inschatting van wat nodig is;

- Alles rond "zaken" vindt zoveel mogelijk geautomatiseerd en op de achtergrond plaats. Medewerkers zijn bezig met inhoudelijke activiteiten, niet met zaken;

- Ook [klantcontacten](https://www.gemmaonline.nl/index.php/Klantcontacten_en_het_RGBZ) worden uitgewerkt in de API.

- De inhoud van de zaaktypecatalogus (ZTC) wordt zoveel mogelijk gestandaardiseerd, rekening houdend met de [zaakgerichte selectielijst](https://vng.nl/files/vng/20170706-selectielijst-gemeenten-intergemeentelijke-organen-2017.pdf)(pdf) en GEMMA 2 processen. Gestreefd wordt naar het centraal aanbieden van een ZTC. Deze kan bijv. dienen als repository, waar gemeenten zaaktypen 1 op 1 uit kunnen overnemen of deze voor eigen gebruik wijzigen waar nodig.

- Eisen rond [Duurzame toegankelijkheid](https://wiki.nationaalarchief.nl/pagina/DUTO:Kwaliteitseisen) worden vanaf het begin in de standaarden verwerkt.

- Archivering speelt een rol bij de uitvoering van elk proces, vanaf de start tot aan [overbrenging](https://wiki.nationaalarchief.nl/pagina/DUTO:Overbrenging) of [vernietiging](https://wiki.nationaalarchief.nl/pagina/DUTO:Vernietigen). Daar waar nodig worden externe standaarden zoals bijv. [TMLO](https://archief2020.nl/nieuws/toepassingsprofiel-metadatering-lokale-overheden), hoewel suboptimaal, geïntegreerd in de standaard.


## Centraal aanbieden      

Het principe "raadplegen bij de bron" veronderstelt waar mogelijk een enkele bron die wordt bijgehouden door de verantwoordelijke en welke kan worden geraadpleegd door afnemers.

Binnen het DSO (zie: [Gerelateerde trajecten](#gerelateerde_trajecten)) is een centrale *Zaakregistratiecomponent* (ZRC) wellicht een welkome oplossing.

Een centrale *Zaaktypecatalogus* (ZTC) kan dienen als repository van content die voor veel gemeenten gelijk zal blijken.

Wanneer componenten centraal worden aangeboden moeten deze worden ondergebracht bij een  *centrale beheerorganisatie*.


##	Uitgangspunten

Bij de start van dit traject hanteren we de volgende uitgangspunten:

- GEMMA 2 standaarden worden gevolgd

- Daar waar GEMMA 2 niets voorschrijft worden Open Standaarden gevolgd

- Daar waar GEMMA 2 nog niet (helemaal) in lijn is met Common Ground, wordt Common Ground gevolgd

- Alle code die ontstaat in dit traject wordt Open Source, gepubliceerd onder de EUPL licentie

- RGBZ 2 (GEMMA 2) is het startpunt, maar wanneer blijkt dat aanpassingen nodig zijn voor goede werking van de Zaak- en Documentservices dan is dit mogelijk. RGBZ 1 bestaat sinds 2010, RGBZ 2 is sinds 2012 in ontwikkeling en nog altijd niet in productie. Met ingang van dit traject komen betrokken standaarden in een "permanent beta" toestand, waarbij deze voortdurend op basis van behoefte en consensus worden gewijzigd.

- Voor de specificatie van API's wordt de onlangs door Forum Standaardisatie op de "Pas toe of leg uit"-lijst geplaatste OpenAPI Specification v3.x gebruikt.

- De principes volgend uit de [Common Ground visie](https://github.com/VNG-Realisatie/common-ground/blob/master/cg-vision.md) (EN) worden als volgt toegepast:
  - Goede scheiding zaakafhandeling en -registratie (ook conform GEMMA 2 met Zaakregistratiecomponent en Zaakafhandelcomponent)
  - Bij eventueel centraal aangeboden voorzieningen worden API's ontsloten via NLX
  - Grote informatiemodellen worden waar nuttig opgesplitst in kleinere informatiemodellen die hoog-frequent kunnen wijzigen

- De [API en URI strategie](https://aandeslagmetdeomgevingswet.nl/digitaal-stelsel/documenten/documenten/api-uri-strategie/) zoals opgesteld binnen het programma Digitaal Stelsel Omgevingswet worden waar mogelijk toegepast.


##	Realisatie

De realisatie gaat van start zonder complete blauwdruk van wat gebouwd moet worden. Door user stories zo goed mogelijk in te vullen en vanuit oogpunt architectuur in de gaten te houden dat design choices worden gemaakt die ruimte openlaten voor verdere ontwikkeling in de richting van de visie, komt de nieuwe standaard stukje bij beetje tot stand.

Ontwikkeling valt uiteen in 3 delen die niet los van elkaar gezien kunnen worden:
- Realiseren van een open source zakenregistratiecomponent
- Opstellen en realiseren van een nieuwe ZDS 2.0 API
- Realiseren van toepassingen voor burgers of gemeenten die gebruik maken van zaakgegevens uit het zakenregistratiecomponent, via de gestandaardiseerde API

Om een snelle start te maken wordt gestart met alle gemeenten en partijen waarvan de interesse bekend is. Aanhakers zijn nadrukkelijk welkom.

De ontwikkeling gebeurt geheel Open Source, in de GitHub repository [VNG-Realisatie/gemma-zaken](https://github.com/VNG-Realisatie/gemma-zaken).

Ook de backlog wordt publiek bijgehouden, samengesteld uit GitHub issues op dit open [Kanban bord](https://github.com/VNG-Realisatie/gemma-zaken/projects/1).

Bij de ontwikkeling van de API's wordt gestreefd naar backwards compatibility. 

Voor meer informatie over de samenwerking, zie [samenwerking.md](./samenwerking.md)


## Gerelateerde trajecten

- Binnen het [Digitaal Stelsel Omgevingswet](https://www.omgevingswetportaal.nl/wet-en-regelgeving/dso) zijn wellicht kansen om Zaakgericht Werken zoals gemeenten dat kennen te introduceren op basis van de ZDS 2.0 API's. Momenteel wordt samenwerking daar voorzien door middel van een omgeving waar bestanden kunnen worden gedeeld.

- De gemeenten Almere, Amsterdam, Haarlem, Heerenveen, Hoorn, Medemblik (en wellicht nog meer) zijn voornemens gezamelijk een Open Source Mijn Gemeente website te produceren. Daarbij is ZDS 2.0 wellicht een interessante aanvulling, hier liggen kansen om samen op te trekken.

- Dimpact en Atos stellen de Atos e-Suite in de context van Common Ground beschikbaar als platform voor proeven die innovatie en ontwikkeling stimuleren.

- Het project Landelijke Online Diensten (LOD) heeft een landelijke dienst voor aangifte overlijden en aangifte verhuizing gerealiseerd. Voor de koppeling tussen deze dienst (de voorkant) en de verwerkende systemen in de gemeente (de achterkant) worden twee "productaanvragen" API's ontworpen en gerealiseerd.
