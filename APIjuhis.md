---
title: API
permalink: API
pais: false
---

<!-- {% increment nn %} -->

# API-de projekteerimisjuhis
{: .no_toc}

v0.4, 12.12.2017

Juhis esitab terminoloogia, nõuded ja soovitused REST API-de projekteerimiseks, testimiseks ja dokumenteerimiseks.

***Sisukord***
{: .no_toc}

- TOC
{:toc}

## 1 API elutsükkel

***API*** (_application programming interface_) e ***masinliides*** on eraldi käitatavate ja/või arendatavate süsteemide või komponentide sidumise viis. API-del põhineb süsteemide lõimimine (_systems integration_), hajusarhitektuursed lahendused, sh mikroteenused ja üldse suur osa tänapäevasest infotöötlusest.

***API-põhine arhitektuur***, nn ***API first*** strateegia [API First Government, Kütt 2016](https://www.slideshare.net/AndresKtt/api-first-government), toob kaasa API-de arvu ja keerukuse kasvu. Süsteemid, ka taristud, arenevad selles suunas, et kõik andmed ja kogu funktsionaalsus on kasutatavad API-de kaudu. Masinloetav API ja inimkasutaja liides toetavad ja täiendavad teineteist. Vt ka Kütt, A (2016) [Reference Architecture for Cloud-Ready Government Systems](https://github.com/e-gov/fox), nn "Rebaseregister".

{% capture abi %}{% increment nn %}{% endcapture %}
Nõue {{ abi }}. Süsteem peaks kogu oma andmestikku pakkuma masinloetaval kujul s.t API kaudu.
{: .noue}

***API elutsükli*** moodustavad hulk  tegevusi: 

- API kavandamine
- API projekteerimine
- API dokumenteerimine
- API teostamine (programmeerimine)
- API testimine
- API haldamine
- API valitsemine (_API governance_)
- API turvamine
- API rahakspööramine (_monetization_)
- API kasutajaskonna kasvatamine
- APi kasutuse analüüs (API analüütika).

API arendamisel tuleb kõiki neid aspekte adekvaatselt käsitleda.

## 2 API-juhised

API kavandamisel saab eeskuju võtta muuhulgas järgmistest juhistest jm materjalidest:

- Google API disainijuhis, [Google API Design Guide](https://cloud.google.com/apis/design), avaldati 2017. a veeburaris. See on üks parimaid materjale REST API-de disaini vallas. Juhisesse on kogutud Google-is 2014. a alates rakendatud API-de disaininõuded ja -põhimõtted. Seejuures on püütud ühtselt käsitleda REST ja RPC teenuseid. REST API-de kujundamisel on otstarbekas lähtuda eelkõige Google API disainijuhisest. Kuid tuleb arvestada, et kõik Google nõuded ei ole kohaldatavad.
- [APIs for Dummies](http://www.appythings.nl/sites/default/files/api_for_dummies.pdf) on hea populaarne ülevaade ja sissejuhatus "API-majandusse" (_API economy_), kuid ei ole kasutatav disainijuhendina.
- [Amazon API Gateway Developer Guide](http://docs.aws.amazon.com/apigateway/latest/developerguide/apigateway-dg.pdf) on Amazoni-spetsiifiline, kuid annab aimu API loomise ja haldamise erinevatest aspektidest.
- [White House Web API Standards](https://github.com/WhiteHouse/api-standards) on kompaktne, hea juhis REST API-de kujundamiseks.
- [Todo-backend](http://todobackend.com/) näitab kuidas lihtsat API-t (TO DO märkmed) teostada erinevate tehnoloogiatega.

## 3 API kavandamise lähteparameetrid

Kavandamist mõjutavad liidese kavandatavad kasutusparameetrid: 1) kas liides on avalik, kõigile vabalt kasutamiseks või on vaja ligipääsu piirata? 2) kas liides on mõeldud kasutamiseks turvatud sisevõrgus või avalikus internetis? 3) kas kasutatakse REST, SOAP või mõnda muud stiili? Käesolev juhis keskendub [REST API](https://spring.io/understanding/REST)-dele.

## 4 API tööriistad

API-de arendamise, dokumenteerimise, testimise ja turvamise keerukus on tinginud mitmesuguste ***API tööriistade*** (redaktorite, avaldamisvahendite, validaatorite) teket. Näiteks: 

- [Open API Initiative](https://www.openapis.org/), endine ***Swagger*** on REST API-de formaalse kirjeldamise keel (omataoliste seas hetkel levinuim)
- [Postman](https://www.getpostman.com/) on populaarne API-de testimise vahend
- [curl](https://curl.haxx.se/) (Windows-i keskkonnas saadav Git Bash-i koosseisus) on populaarne REST API-de testimise vahend
- [SoapUI](https://www.soapui.org/) on raamistik nii SOAP kui ka REST API-de testimiseks, sh testimise automatiseerimiseks. 

***API-de arendamise ja haldamise platvormid*** üritavad pakkuda tööriistade kogumeid ja API elutsükli täistoetust. Tähtsamad API-platvormid on [Apiary](https://apiary.io/) ja [Agigee](https://apigee.com). API-platvormide arengut näitab Apiary ostmine Oracle poolt (Jan 2017) ja Apigee ostmine Google poolt (Nov 2016). API-platvormi kasutamine väikese API-de arvu korral tõenäoliselt ei ole õigustatud. Kuid tuleb tajuda, et API arendamine pole ühekordne ettevõtmine, vaid pikemaajaline protsess. 

## 5 API teenusenimi

***API teenuse nimi*** peab olema [RFC1035](https://www.ietf.org/rfc/rfc1035.txt) kohane domeeninimi, mis lahendub üheks või mitmeks võrguaadressiks. Nt `riha.eesti.ee`. Kui API kujundatakse mitmest teenusest koosnevana, siis peab teenusenimede valik toetama teenuste ülesleitavust. Mitut teenust saab ka pakkuda sama teenusenime all, esitades need pöördumistees teenuse versiooninumbri järel. Nt `riha.eesti.ee/v1/Producer` ja `riha.eesti.ee/v1/Publisher` (Google käsitlus). Vt Google disainijuhis, jaotis [Naming Conventions](https://cloud.google.com/apis/design/naming_convention#ListFilterField).

{% capture abi %}{% increment nn %}{% endcapture %}
Nõue {{ abi }}. API-l peab olema selge teenusenimi.
{: .noue}

## 6 Ressursid

***Ressursid*** jagunevad ***lihtressurssideks*** (_simple resource_) ja ***kogumressurssideks*** (_collection resource_). Ressursil on ***olek*** (_state_) ja võivad olla ***alamressursid*** (_sub-resources_).

***Ressursi nimi*** moodustub ressursi ID-st, vanemressursside ID-dest ja API teenuse nimest (Google käsitlus).

{% capture abi %}{% increment nn %}{% endcapture %}
Nõue {{ abi }}. Igal ressursil peab olema unikaalne nimi.
{: .noue}

Nt: `systems` (RIHA-s kirjeldatud infosüsteemide kogum) ja `systems/ETIS` (RIHAs kirjeldatud infosüsteem ETIS). 

***Ressursi täisnimi*** sarnaneb URL-le, kuid ei ole viimasega samaväärne, sest sama ressurss võib olla eksponeeritud mitme erineva protokolli ja API versiooni kaudu (Google käsitlus). Ressursi täisnimi moodustatakse järgmiselt: 1) lisada teenuse nime ette HTTPS skeem; 2) lisada ressursitee ette API major versioon; 3) kasutada URL-escape-i (%-encoding).

***Ressursi suhteline nimi*** identifitseerib ressurssi API teenuse kontekstis.

***Ressursi ID*** on ressurssi oma vanemressursi kontekstis identifitseeriv URI segment. Nt: `ETIS` (RIHAs kirjeldatud infosüsteem ETIS).

Peab selgelt dokumenteerima, kas ressursi ID moodustatakse kliendi (kasutaja) või serveri poolt (Google disainijuhend).

{% capture abi %}{% increment nn %}{% endcapture %}
Nõue {{ abi }}. Nimemustri kujundamisel arvestada ka seda, et kasutajad mustrist aru saaksid ja nime oleks kerge kasutada.
{: .noue}

***Kogumressursi ID*** (_collection ID_) peab olema mitmuses. Nt: `systems` (RIHA-s kirjeldatud infosüsteemide kogum). Vt Google disainijuhis, jaotis [Resource Names](https://cloud.google.com/apis/design/resource_names). 

## 7 Meetodid

***Meetodid*** rakenduvad ressurssidele ja jagunevad standardmeetoditeks ja erimeetoditeks. ***Standardmeetodid*** Google käsitluses on `List`, `Get`, `Create`, `Update` ja `Delete`. Need esitatakse HTTP meetodite abil järgmiselt:

|  Meetod   |  Vastav HTTP meetodimuster         |  HTTP päringu keha |  HTTP vastuse keha | 
|:---------:|:----------------------------------:|:------------------:|:------------------:| 
|  `List`   |  `GET <kogumi URL>`            |  tühi              |  ressursikogum | 
|  `Get`    |  `GET <ressursi URL>`              |  tühi              |  ressurss          | 
|  `Create` |  `POST <ressursi URL>`           |  ressurss          |  ressurss          | 
|  `Update` |  `PUT` või `PATCH <ressursi URL>`|  ressurss          |  ressurss          | 
|  `Delete` |  `DELETE <ressursi URL>`         |  tühi              |  tühi              | 

Nendest reeglitest on erisusi, vt Google disainijuhis, jaotis [Standard Methods](https://cloud.google.com/apis/design/standard_methods).

***Erimeetod*** on selline, mis kaldub kõrvale standardsest REST semantikast. Nt infosüsteemi omaniku vahetus.

{% capture abi %}{% increment nn %}{% endcapture %}
Nõue {{ abi }}. Kus vähegi võimalik, tuleks kasutada REST standardmeetodeid.
{: .noue}

Google disainijuhis, jaotis [Custom Methods](https://cloud.google.com/apis/design/custom_methods) pakub skeemi erimeetodite vormindamiseks (_custom verb_).

## 8 Protokollid

Arvestada turvatud HTTP protokolli kasutamisega (HTTPS, aga mitte näiteks [WebSocket](https://en.wikipedia.org/wiki/WebSocket). Viimane on uuem, TCP-põhine, veebisirvija ja -serveri vahel üheaegselt kahes suunas andmeedastust (_full-duplex_) võimaldav andmevahetusprotokoll).

## 9 Päringu moodustamine

Andmete saatmiseks päringus on järgmised võimalused:

1) URL-i osana (_URL-encoded_);

2) JSON-vormingus päringu kehas (_HTTP request body_). MIME meediatüüp sellisel juhul on `application/json`;

3) `POST` päringutes kasutatakse ka nn _form-urlencoded_ esitust, kus HTML-vormilt loetud andmed saadetakse _query string_-kujul, kuid päringu kehas (MIME meediatüüp `application/x-www-form-urlencoded`). 

## 10 Filtreerimine ja sortimine

Kui API pakub tulemuste nimekirja filtreerimist või sortimist, siis võiks järgida SQL süntaksit. Vt ka Google disainijuhend, jaotis [Sorting Order](https://cloud.google.com/apis/design/design_patterns#sorting_order).

## 11 Kauakestvad operatsioonid

Kui API meetodi täitmine võtab tüüpiliselt kauem aega, siis võib meetodi projekteerida nii, et tagastatakse tagasikutse (_callback_, Google terminoloogias - _Long Running Operation_), mille abil klient saab jälgida edenemist ja saada lõpptulemuse. Vrdl Google disainijuhend, jaotis [Common Design Patterns](https://cloud.google.com/apis/design/design_patterns).

## 12 Andmete väljastamine leheküljeti

Andmete väljastamine leheküljeti tuleks teostada ka väikesemahuliste, kuid kasvada võivate ressursikogumite puhul. Google soovitus on "_listable collections should support pagination, even if results are typically small._" Vt Google disainijuhend, jaotis [Common Design Patterns](https://cloud.google.com/apis/design/design_patterns).

## 13 Päringu samajõulisus

Väga soovitav on teha päringud samajõuliseks (idempotentseteks). See tähendab, et sama päringut saab võrgutõrke korral ilma kahjulike kõrvalmõjudeta uuesti saata. Kui päringut ei saa teha idempotentseks, siis peaks iga päringsõnum sisaldama unikaalset ***idempotentsus-ID-d***. Vt: Leach (2017) [Designing robust and predictable APIs with idempotency](https://stripe.com/blog/idempotency); Google disainijuhis, jaotis [Request Duplication](https://cloud.google.com/apis/design/design_patterns#sorting_order).

## 14 API turvamine

{% capture abi %}{% increment nn %}{% endcapture %}
Nõue {{ abi }}. Reeglina tuleb API-d kaitsta TLS-ga, ka sisevõrgus. (See tähendab, et pöördumine toimub HTTPS-ga). 
{: .noue}

Juurdepääs väliseks kasutuseks mõeldud API-le võib olla kas piiramata või piiratud ***autentimistokeni*** abil, mis tuleb päringule kaasa panna kas ühe parameetri või HTTP päises oleva väärtusena. Eelistatud on JWT ([JSON Web Token](https://jwt.io/)) autentimine. Vt Stankovic (2016), [JWT Authentication Tutorial: An example using Spring Boot](http://www.svlada.com/jwt-token-authentication-with-spring-boot/). Siiski tuleb igal konkreetselt juhul selgitada, kas JWT kasutamine on arendajale jõukohane ja äriliselt ning tehniliselt põhjendatud.

## 15 API versioneerimine

API struktuuris tuleb taodelda stabiilsust.

{% capture abi %}{% increment nn %}{% endcapture %}
Nõue {{ abi }}. Kui on ette näha API muutumisvõimalust, siis tuleb API versioneerida.
{: .noue}

Versioneerimisel on otstarbekas kasutada [semantilist versioneerimist](http://semver.org/). Vt Google disainijuhis, jaotised [Compatibility](https://cloud.google.com/apis/design/compatibility) ja [Versioning](https://cloud.google.com/apis/design/versioning).

## 16 API disainimine

[Google API Design Guide](https://cloud.google.com/apis/design/resources) soovitab järgmist tööde järjekorda (_design flow_): 1) määrata API-s pakutavad ressursitüübid (_resource types_); 2) määrata ressurssidevahelised seosed; 3)  määrata nimemustrid e -skeemid (_resource name schemes_); 4) määrata ressursiskeemid; 5) siduda minimaalne hulk meetodeid ressurssidega.

## 17 API spetsifitseerimine

***Kirjelduse täielikkus***.

{% capture abi %}{% increment nn %}{% endcapture %}
Nõue {{ abi }}. API tuleb täpselt ja täielikult dokumenteerida. "_Discovery-based documentation_" (API käitumise väljaselgitamine katse-eksituse teel) ei ole aktsepteeritav.
{: .noue}

***Formalismi kasutamine***.

{% capture abi %}{% increment nn %}{% endcapture %}
Nõue {{ abi }}. Vajalik on formaalne kirjeldus, mis ühtlasi peab olema ka inimloetav. "Vabas vormis" dokumenteerimine on vastuvõetav ainult triviaalsete liideste puhul.
{: .noue}

Formaalne kirjeldamine ei ole eesmärk omaette, vaid vahend kirjelduse täielikkuse ja üheseltmõistetavuse saavutamiseks. REST API-de dokumenteerimise kohta on kaks laialtlevinud standardit: 1) [OpenAPI Specification](https://github.com/OAI/OpenAPI-Specification), endise nimega ***Swagger***, kasutab aluskeelena YAML-i või JSON-it; 2) [API Blueprint](https://apiblueprint.org/) kasutab aluskeelena Markdown-i ("_a powerful high-level API description language_"). Eelistatud on OpenAPI kirjelduskeele kasutamine. [Extended Backus-Naur Form (EBNF)](https://cloud.google.com/apis/design/design_patterns#grammar_syntax) on samuti hea formalism.

{% capture abi %}{% increment nn %}{% endcapture %}
Nõue {{ abi }}. API tuleb kirjeldada OpenAPI (Swaggeri) spetsifikatsiooni kohaselt.
{: .noue}

***Näited***. Näite või näidete lisamine on tingimata vajalik. Seejuures kirjeldamine ainuüksi näite abil ei ole piisav.
{: .noue}

***Navigeeritavus***. API kirjeldus peaks olema navigeeritav.

***Avalikkus***.

{% capture abi %}{% increment nn %}{% endcapture %}
Nõue {{ abi }}. API kirjeldus tuleb selgelt, tavaliselt avalikult, publitseerida. 
{: .noue}

***Ajakohasus***.

{% capture abi %}{% increment nn %}{% endcapture %}
Nõue {{ abi }}. API kirjeldust tuleb hoida ajakohasena. See tähendab, et API käitumine peab vastama kirjeldusele.
{: .noue}

## 18 API tarkvaraline teostamine

REST API-de tegemise vahendeid pakutakse paljudel platvormidel ja raamistikes. Mõnda platvormi on API-d vaikimisi sisse ehitatud. Nt: [Spring Boot](https://spring.io/guides/gs/actuator-service/); [PostgreSQL Restful API](https://www.postgresql.org/about/news/1616/); [Google Apps Script](https://trevorfox.com/2015/03/rest-api-with-google-apps-script/). Vt ka jaotis "API tööriistad".

## 19 API testimine

***Testide katvus***. 

{% capture abi %}{% increment nn %}{% endcapture %}
Nõue {{ abi }}. API testid peavad hõlmama kõiki ressursitüüpe ja kõiki meetodeid.
{: .noue}

***Automatiseerimine***. 

{% capture abi %}{% increment nn %}{% endcapture %}
Nõue {{ abi }}. API testid tuleb automatiseerida vähemalt testikogumit käitava skripti tasemel.
{: .noue}

## 20 API kasutuse mõõtmine

Ei ole mõtet teha liidest, mida keegi ei kasuta. API kasutuse mõõtmine (statistika kogumine) peaks olema API elutsükli standardne osa. Vajalik võib olla ka API kasutuse monitooring (turvakaalutlustel). Vastavad võimalused tuleks ette näha juba API kavandamisel.
