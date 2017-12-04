---
permalink: /
---

<img src='img/LOVID.png' style='width: 80px;'>

# Mittefunktsionaalsed nõuded
{: .no_toc}

v 3.2  26.06.2017

Sisukord

- TOC
{:toc}

Lisa 1. Java Checkstyle seadistusfail

Käesolev dokument sätestab mittefunktsionaalsed nõuded RIA tellitavale tarkvarale.

## Lühendid ja mõisted

___MFN___ - mittefunktsionaalsed nõuded (ka nõuete dokumendi mõistes)<br>
___tarkvara___ - hõlmab ka dokumentatsiooni, sh kavandeid

{% assign c = 0 %}
| Nõude liik | Nr  | Nõue | Selgitus |
|------------|:---:|------|----------|
| meta       | {% increment counter %} |  |  |
|  | {% increment counter %}  |  |  |
|  |  |  |  |
|  |  |  |  |
|  |  |  |  |
|  |  |  |  |
|  |  |  |  |
|  |  |  |  |
|  |  |  |  |
|  |  |  |  |
|  |  |  |  |
|  |  |  |  |
|  |  |  |  |
|  |  |  |  |
|  |  |  |  |
|  |  |  |  |
|  |  |  |  |

## 1 Nõuete struktuur ja rakendamine

1.1 Adekvaatne rakendamine. Konkreetse tarkvara puhul rakenduvad ainult need nõuded, mis on selle tarkvara iseloomu, ülesehituse ja kasutatavate komponentide tõttu on adekvaatselt rakendatavad.

1.2 MFN-de hierarhia. Kõiki tarkvarasid hõlmava, täieliku nõuetekogumi loomine ei ole otstarbekas. Seetõttu organiseeritakse mittefunktsionaalsed nõuded hierarhiliselt, kolme tasandi nõudekogumitena.

RIA MFN-s kirjeldatakse nõuded, mida peab rakendama kõigis RIA infosüsteemides. Valdkonna MFN-s kirjeldatakse nõuded, mida rakendatakse ainult antud valdkonna tarkvaras. (Nt X.tee MFN). Valdkonna MFN kirjutatakse asutuse taseme MFN täiendusena. Hanke MFN-i nõuded täpsustavad asutuse või valdkonna nõudeid.

1.3 Nõude ülekate jm muudatused. Kui valdkonna või hanke MFN muudab ülemise taseme MFN-s kirjeldatut, siis tuleb muudatus täpselt määratleda. Muudatuse tüübiks võib olla:

    loobumine –  loobutakse mõnest asutuse taseme MFN-ga kehtestatud nõudest – näidatakse täpselt ära milline asutuse või taseme nõude (number) valdkonnas ei kehti;
    ülekate – muudetakse asutuse taseme MFN-ga kehtestatud mõne nõude sisu – näidatakse muudetud nõue (number) ja kirjutatakse nõude uus täistekst;
    lisandus – kehtestatakse nõue, mida asutuse taseme MFN-s ei ole.

1.4 Hanke MFN. Konkreetse hanke MFN moodustub hanke toimumise  hetkel kehtivate asutuse ja valdkonna MFN-des kehtestatud piirangutest, millele lisanduvad hanke MFN-s kirjeldatud täiendavad piirangud.  Selliselt moodustunud  MFN-i  puhul kehtib reegel, mis ütleb, et konkreetsete tööde teostamisel kohanduvad ainult need piirangud, mis konkreetsete tööde puhul on kohaldatavad st. ei saa rakendada nõudeid, mis ei haaku konkreetse tööga.

Kui siseriiklikult on sama projektiga seotud mitu organisatsiooni, siis rakendatakse asutuse MFN-na selle asutuse ja valdkonna MFN-e, mis on tööde tegelikuks tellijaks. Teiste organisatsioonide MFN-dest tulenevad erinevused kirjeldatakse hangete MFN-des. Suuremate projektide puhul on õigus rakendada samu nõudeid, mis kehtivad rahvusvaheliste takvara arenduste MFN-de koostamisel.

1.5 Rahvusvahelise koostöö vormis toimuva arenduse puhul luuakse eraldiseisev mittefunktsionaalsete nõuete kirjeldus, mida saab täpsustada iga konkreetse projekti või hanke korral. Mittefunktsionaalsed nõude sellise projekti jaoks luuakse kahe tasemelise struktureeritud nõuete kogumina: a) koostööprojekti tasemel kehtivad mittefunktsionaalsed nõuded (näit. X-tee MFN); b)hankega täpsustatud koostööprojekti mittefunktsionaalsed nõuded (pakkumuskutse osa). Koostööprojekti taseme MFN-s kirjeldatakse ainult need piirangud, mida peab rakendama kõigis antud projekti raames loodavates infosüsteemides.

Hanke MFN-s muudetavad piirangud saavad täpsustada olemasolevaid koostööprojekti MFN-i. Kui hanke  MFN muudab koostööprojekti taseme MFN-s kirjeldatut siis tuleb määratleda täpselt, millise muudatusega on tegemist (vt muudatustüübid ülalpool). Konkreetse hanke MFN moodustub hanke toimumise  hetkel kehtivate koostööprojekti MFN-s kehtestatud piirangutest, millele lisanduvad hanke MFN-s kirjeldatud täiendavad piirangud.

## 2 Kodeering

2.1 Andmebaasid ja rakendused peavad kasutama UTF-8 kodeeringut.

2.2 Ühe faili piires kasutatakse alati sama reavahetuse kodeeringut - kas Windowsi standardile vastavat (CR+LF; 0x0D0A; U+000D U+000A) või Linux/Unix standardile vastavat (LF; 0x0A; U+000A).

## 3 Litsents

3.1 Loodud teose autoriõigused tuleb selgelt välja tuua. Standardseks vahendiks selleks on litsents. 

<strike>Lähtekood peab olema faili päises markeeritud litsentsiga. Litsents esitatakse ka dokumentatsioonis.</strike> Nõue on "üle võlli" paljudel juhtudel. Piisab litsentsi nähtaval kohal väljapanemisest.
{: .teade}

3.2 Litsents esitatakse ühel või mitmel alljärgnevatest viisidest:
- LICENCE

## 4 Tõrkekindlus

4.1 Rakenduse liidesed peavad olema tõrkekindlad. Välise süsteemi tõrge tohib mõjutada ainult sellest otseselt sõltuvate kasutuslugude toimimist.

## 5 Moodulehitus

5. 1 Rakendus peab olema tehniliselt tükeldatud vastavalt loogilisele jaotusele. Saadud osised peavad olema eraldi versioneeritavad ja paigaldatavad. Näiteks, kui rakendusel on eraldi turvakontekstidega liidesed ametnikule ja kodanikule, peab rakendus olema jaotatud kaheks eraldi liidesekomponendiks ning nende mõlema poolt kasutatavaks andmebaasiks.

## 6 Koodi kvaliteet

6.1 Lähtekoodi dokumentatsioon, lähtekood ise ning logiteated peavad olema läbivalt inglisekeelsed.

6.2 Lähtekood peab olema varustatud ühiktestidega.

6.3 Java puhul kasutatakse stiilikontrolli.  Checkstyle (http://checkstyle.sourceforge.net/) ei tohi käivitamisel Lisas 1 oleva konfiguratsioonifailiga väljastada ühtegi viga.

6.4 Java puhul staatilise koodianalüüsi PMD (http://pmd.sourceforge.net/) reeglistikud „Basic Rules“, „Import Statement Rules“, „Security Code Guidelines“ ja „Unused Code Rules“ ei tohi väljastada ühtegi viga.

## 7 Kasutajaliides

7.1 CSS-failide kasutamine. Stiilid peavad asuma CSS-failides, st style elementi ja style parameetrit CSS-koodiga ei tohi kasutada.

7.2 Otselinkide kasutamine. Süsteemis tuleb rakendada otselinke (deeplinking). Igal lehel peab olema unikaalne, automaatselt genereeritud ja inimloetav veebiaadress (URL) ning see ei tohi olla seotud kasutaja sessiooniga ega kasutaja tundlike isikuandmetega.

7.3. Kasutajale arusaadavad veateated. Süsteem peab asendama vaikimisi veateate (404 jms) lehekülje, kuid säilitama algse HTTP vastuskoodi.

7.4 Tänapäevased veebistandardid. Tuleb kasutada veebistandardeid HTML5 ja CSS3.

7.5. Veebisirvija tugi. Kasutajaliides peab veatult toimima veebisirvijaga, mida toetab eID baastarkvara. Toetatakse kahte viimast ID-kaardi baastarkvara versiooni (major version).

Kui kasutajaliides, mille poole kasutaja pöördub, ei ole ühilduv kasutatava veebisirvijaga, peab rakendus arusaadaval ja juhendaval viisil sellest kasutajata teavitama.
8 Identiteedi- ja pääsuhaldus

8.1 Registrikoodide kasutamine. Riiklikesse registritesse kantavad objektid (isikud, katastriüksused jne) kantakse andmebaasi nende registrikoodiga, mida täiendab riigiprefiks vastavalt ISO3166-1 Alpha 2 standardile. Näiteks isikute sidumiseks süsteemi kasutajakontoga peab kasutama isikukoodi rahvastikuregistrist.

8.2 Füüsilise isiku identifitseerimine. Mittekodanike isikuidentifikaator saadakse järgmisel viisil:

riigikood + sookood + sünniaeg + [ dok_nr | id_riigis ]
 
riigikood - kolmekohaline ISO 3166-1 alpha-3 standardile vastav riigi kood
sookood - soo identifikaator nii nagu Eesti Vabariigi isikukoodis
sünniaeg - sünniaeg formaadis YYYYMMDD
id_riigis - kui see on olemas, tuleb kasutada isiku koduriigi isikuidentifikaatorit. 16 kohta, 0-polsterdatud vasakult  
dok_nr - kui isiku koduriigis isikuidentifikaatorit ei ole, siis kasutatakse isiku dokumendi numbrit. Dokumendi number, 16 kohta, 0-polsterdatud vasakult.

Eesti Vabariigi kodanik identifitseeritakse Eesti Vabariigi poolt väljastatud eIDga. Igasuguse muu identifitseerimisevahendi kasutamine peab olema selgelt põhjendatud

8.4 Olemasoleva autentimissüsteemi kasutamine. Rakendus ei tohi luua uut autentimissüsteemi, tuleb tugineda olemasolevatele riiklikele (ID-kaart) või põhiliste op-süsteemide süsteemidele (PAM, Kerberos jms).

8.5 Autentimisdirektiivi kasutamine. Rakenduse väliste kasutajate, so. Eesti Vabariigi residentide ja EL teiste liikmesriikide residentide, autentimislahenduse loomisel tuleb lähtuda dokumendist „EESTI VABARIIGI INFOSÜSTEEMIS AUTENTIMISLAHENDUSTELE KEHTIVAD NÕUDED”   

8.6. Väline rollihaldus. Rakenduse mitteavalike osade kasutajate rollid asuvad rakendusevälises LDAPs serveris või muus autentimislahenduses. Süsteem ei tohi realiseerida omaenda rollide haldamist.

8.7 Süsteemist väljumine. Süsteemist väljumine peab toimuma sõnaselgelt, kasutajale arusaadaval ja turvalisel viisil. Kasutaja saab süsteemist väljuda kahel viisil: tema sessioon on pikem, kui sessiooni pikkuse seadistatav piirväärtus (eraldi määratletavad piirangud kogu sessioonile ning tegevuseta perioodile sessioonis) või kasutaja lõpetab sessiooni enda algatusel.

Juhul kui rakenduse turvanõuded näevad seda ette, peab olema võimalus koheselt lõpetada kasutaja sessiooni nii, et kasutaja saaks arusaadava ja põhjendatud teate sessiooni lõpetamise kohta.

8.8. Sessiooniküpsised. Rakendus tohib sessioonihalduse jaoks kasutada vaid sessiooniküpsiseid.
9 Andmebaas

9.1 Süsteemsed andmebaasikasutajad. Andmebaasi kasutaval rakendusel on vähemalt kaks andmebaasikasutajat:

    <rakendus> nimeline andmebaasi skeem kuulub andmebaasi kasutajale <rakendus> (roll db owner, skeemid ja seal paiknevad objektid kuuluvad sellele kasutajale).
    <rakendus> nimelises andmebaasi skeemis on defineeritud <rakendus>_app nimeline kasutaja, kes omab ligipääsu (SELECT, INSERT, UPDATE, DELETE) ainult rakenduse käitamiseks vajalikele tabelitele/protseduuridele/funktsioonidele.

9.2 Andmebaasivõtmed. Ühest andmetabelist teise viitamisel tuleb kasutada välisvõtmeid (foreign key). Kõik välisvõtmed (foreign key) peavad olema indekseeritud mitteunikaalse indeksiga ja välisvõtmetena kirjeldatud.

Kõigis andmebaasi tabelites peab olema defineeritud integer-tüüpi primaarvõti, mis on surrogaatvõti. Primaarvõtmena ei tohi kasutada reaalse eluga seotud andmevälju.

Kõik primaarvõtmed (primary key) peavad olema indekseeritud unikaalse indeksiga.

9.3. Kirjete versioneerimine. Kui andmebaasis olevate andmete ISKE tervikluse klass on 2 või kõrgem, siis tuleb kõik klass 2 infot sisaldavad andmebaasi kirjed versioneerida.

9.3 Väljade pikkused. Andmebaasi väljade pikkused tuleb andmekirjelduskeeles (DDL-is) kirjeldada sümbolites, mitte baitides.

9.4 Konstantide päringutes kasutamise keeld. Andmebaasi poole pöördumisel päringulausetega tuleb päringulause filtris kasutada päringumuutujaid (variable binding) st. päringulaused ei tohi sisaldada konstantidena sisse kirjutatud  päringutingimuse võrdlusväärtusi.

9.5 Objektinimetuste keel. Andmebaasi objektide nimetused peavad olema inglisekeelsed. Nimetused tohivad sisaldada ainult Latin1 (ISO8859-1) kodeeringu tähti a-z;A-Z, numbreid 0-9, ning alakriipsu _. Objektide nimetused ei tohi alata numbritega. Andmebaasiobjektide nimed peavad olema semantilised st. objekti tähendust avavad.

9.6 Agnostilisus partitsioneerimise suhtes. Rakendus peab olema tabelite partitsioneerimise (http://en.wikipedia.org/wiki/Partition_%28database%29) suhtes agnostiline st. tabelite partitsioneerimisstruktuuride muutmine ei tohi mõjutada rakenduse tööd.
10 Logimine

10.1 Standardsete vahendite kasutamine. Rakenduse logimine peab olema organiseeritud kasutades selleks ettenähtud standardseid vahendeid viisil, mis võimaldab rakenduse administraatoril määratleda ja muuta logide väljundit (vähemalt fail, andmebaas, syslogd), logimise taset ja logimise formaati. Igasugune logimine muul viisil on keelatud.

Java rakenduste korral logitakse SLF4J raamistiku abil (vt http://www.slf4j.org).

10.2 Enese tutvustamine. Süsteemi iga eraldi paigaldatav osa peab logimisel (näiteks aadressil heartbeat.json) väljastama masinloetaval kujul oma nime ja versiooninumbri, oluliste väliste süsteemide oleku, viimase käivitamise aja, pakendamise aja ning serveriaja.

10.3 Logide keel. Logid kirjutatakse inglise keeles (välja arvatud kasutajale näidatud teated).

10.4 Turvalogi. Turvalisuse seisukohalt kriitilised sündmused (sisenemine, väljumine, rolli muut(u)mine) ning tegevused, mis toovad kaasa rahalisi või juriidilisi tagajärgi, logitakse eraldi konfigureeritavasse turvalogisse.
11 Keskkond, paigaldus ja seaded

11.1 Keskkonna muutmise keeld. Kui funktsionaalsetes nõuetes pole sõnaselgelt teisiti sätestatud, ei tohi rakendus paigaldamise järel teda sisaldavat süsteemi mitte mingil viisil muuta. Keelatud on muu hulgas keskkonnamuutujatesse kirjutamine, kohalikku failisüsteemi failide loomine jms. Lubatud on ainult logide kirjutamine. Lubatud on ka operatsioonisüsteemi toimimise sekundaardsed efektid.

11.2 Väline postiagent. Rakendus tohib e-kirja saata ainult välise postiagendi (näiteks Postfix) kaudu.

11.3 Siseliideste eraldihoidmine. Rakenduse funktsionaalsuses tuleb selgelt eraldada avaliku teenuse liides muudest mitteavalikest, sisemistest, konfigureerimis jms. liidestest

11.4 Rakendusserveri tarkvarast sõltumatus. Rakendus peab olema loodud sõltumatuna rakendusserveri tarkvarast. Rakendust peab olema võimalik konfiguratsioonimuudatuste abil paigaldada teisele samatüübilisele rakendusserverile. Kui see ei ole võimalik tuleb rakendusele luua sobituspaketid põhiliselt kasutatavate rakendusserverite jaoks.

11.5 Versiooniuuenduste tagasipööratavus. Kõik rakenduse versiooniuuendused (sealhulgas muudatused andmebaasi struktuuris ja koodis) peavad kuni järgmise versiooniuuenduseni olema täielikult tagasi pööratavad st. koos versiooni uuendusega peavad olema loodud vahendid ja kirjeldatud protseduurid versiooniuuenduse tagasi võtmiseks.

11.6 Keskkonna turvalisuse eeldamise keeld. Rakendus ei tohi eeldada paigalduskeskkonna turvalisust. Kõik liidesed rakenduse eri osade vahel peavad olema vajadusel kaitstavad kahepoolset tuvastamist ja krüpteerimist võimaldava protokolliga.

11.7 Klasterdamine. Rakendusservereid peab olema võimalik lisada teenust pakkuvasse klastrisse ja sealt eemaldada vastavalt vajadusele.

11.8 Otsese välisviitamise keeld. Rakendus ei tohi kasutada konfigureerimata viiteid failidele või välistele süsteemidele st. kõik viited peavad olema programmikoodi välised.

11.9 Andmebaasiühendused. Kõik andmebaasiühendused tuleb kirjeldada täispika URI abil. Java rakendustes kasutatakse JNDI ühendusi.

Andmebaasi JNDI objekti Datasource'i nimetamisel tuleb kasutada prefiksit jdbc ning ühesõnaliste lühendite korral väiketähti. Nt: jdbc/system1; jdbc/system2 jne.

11.10 Paigaldamise automatiseerimine. Rakenduse (RIA poolt hallatavasse serverisse) pakendamine, paigaldamine, uuendamine, muudatuse taastamine ja testide käivitamine peavad olema automatiseeritud standardse üldkasutatava vahendi abil (ant, maven, make vms). Loetletud toimingud peavad olema ühikulised, st tohivad sõltuda ainult tarne käigus üle antust.

11.11. Pakke nimi. Ehitatud pakke nimi peab sisaldama projekti nime, keskkonna nime ja versiooni ning tohib sisaldada ainult tähemärke [a-z;0-9] ja - (miinus) ja _ (alakriips) (nt projektinimi-keskkond—1_0_23).

11.12 Andmebaasi paigaldamisõigused. Rakenduse andmebaasi/andmeskeemi paigaldamine ei tohi nõuda punktis 9.1 kirjeldatust erinevaid kasutajaõigusi.

11.13 Hoidlast paigaldamine. Rakendused paigaldatakse ainult lähtekoodihoidlast, selle üheselt viidatud harust.
12 Infoturve

Vt ka: 10.4 Turvalogi, 11.6 Keskkonna turvalisuse eeldamise keeld

12.1 Kui ei ole määratud teisiti, peab rakendus olema kasutatav ISKE klassile K2T2S2 vastavate süsteemide loomisel.

12.2 Süsteem ei tohi võimaldada kasutajale ligipääsu süsteemi toimimise informatsioonile, nagu failide täisnimed, kutsepinud (stack trace) jms.

12.3 Kaitsmata avalik võrguliiklus ei ole lubatud. Igasugune avalik võrguliiklus on krüpteeritud. SSL keskkonna parameetrid on administraatori, mitte arendaja kontrolli all. Erandjuhul, kui edastatav informatsioon ei sisalda konfidentsiaalseid andmeid, on lubatud andmete edastamine krüpteerimata kujul kuid viisil, mis võimaldab andmete vastu võtjal veenduda saadetise tervikluses st. allkirjastatult või ajatembeldatult (X-tee turvaserveri seadistuse edastamise näide).
13 Ajaesitus

13.1 ISO 8601 kasutamine. Kuupäeva, kuupäeva ja kellaaja, kellaaja, kestvuse ning ajaintervalli (perioodi) talletamisel tekst-kujul lähtutakse rahvusvahelisest standardist ISO 8601.

Kuupäevad kirjutatakse kujul AAAA-KK-PP. Näide: 2. juuni 2012. kirjutada kujul 2012-06-02.

Kellaajad kirjutatakse kujul hh:mm:ss , kus hh järgib 24-tunnist kellaajaformaati. Millisekundi täpsusega kellaaja teksti kujul esitamisel kasutatakse formaati hh:mm:ss,nnnn, kus nnnn on millisekundite arv.

Kuupäev ja kellaaeg samas andmeväljas esitatakse kujul, kus kuupäevavormingu ja kellaajavorming vahele lisatakse täht T.

Kestvus esitatakse kujul P[ [<n>Y][<n>M][<n>D]][T[<n>H][<n>M][<n>S] ] või P<n>W, kus […] tähistab kombinatsiooni puudumise võimalikkust, P - tähistab kestvuse määrangu algust, <n> tähendab kestvuse pikkust ja Y, M, D, H, M (pärast T-d, mis tähistab kellaajavorningu algust), S ja W tähistavad vastavalt kestust aastates, kuudes, päevades, tundides, minutites (M pärast T-d, mis tähistab kellaajavormingu algust), sekundites ja nädalates.

Ajaintervallide kirjeldamiseks kasutatakse kahte sama täpsusega (kuupäev, kellaaeg või kuupäev ja kellaaeg) ajavormingut (algus ja lõpp), mis eraldatakse sümboliga  /.

13.2 Aja esitus andmebaasides. Andmebaasides salvestatakse kuupäev, kellaaeg ja kuupäev-kellaaeg ajavormingus andmed vastava andmebaasisüsteemi poolt realiseeritud kuupäev-kellaaeg tüüpi andmeväljades. Ajaintervalli (perioodi talletamiseks) kasutatakse kahte andmevälja, milledest ühte talletatakse perioodi algusaeg ja teise lõpu aeg. Kestusi talletatakse andmebaasides tekst-kujul.

Andmebaasides esitatakse sündmuspõhised (tegevuse tegemise aeg jms.) ajamäärused alati kõige täpsemas võimalikus vormingus st. kas sekundi või millisekundi täpsusega, sõltuvalt konkreetse andmebaasi võimalustest.

Kui andmebaasis esitatakse kuupäev, kellaaeg või kuupäev ja kellaaeg teksti kujul siis lähtutakse käesolevas jaotises kirjeldatud formaatidest. Ajavormingu andmebaasides teksti kujul esitamise ainukeseks põhjuseks on selle vormingu esinemine pikema teksti sees (näiteks logikirje tekstiline osa).
14 Muud kohustuslikud standardid

14.1 ADS-i kasutamine. Eesti aadressiandmete sisestamisel, kuvamisel ja hoidmisel tuleb lähtuda Vabariigi Valitsuse 8. oktoobri 2015. a määrusest nr 103 „Aadressiandmete süsteem“.

14.2 EMTAK-i kasutamine. Eesti tegevusalade andmete sisestamisel, kuvamisel ja hoidmisel tuleb lähtuda Vabariigi Valitsuse 10. jaanuari 2008. a määrusest nr 11 „Klassifikaatorite süsteem“ ja kasutada EMTAK infosüsteemis kehtivat klassifikaatorit.

14.3 EVS 8:2008 kasutamine. Rakendustes kasutatud eesti keelsetele tekstidele kehtivad infotehnoloogia reeglid Eesti keele ja kultuuri keskkonnas EVS 8:2008.







----

[Mittefunktsionaalsed nõuded](https://et.wikipedia.org/wiki/Mittefunktsionaalsed_n%C3%B5uded)

----

Vt ka nõuded dokumentatsioonile

[Riigipilve MFN BI allnõukogule](https://confluence.ria.ee/pages/viewpage.action?pageId=19562975)

[RIA MFN dokumendi arendustsükkel](https://confluence.ria.ee/pages/viewpage.action?pageId=40698241)

[RIA mittefunktsionaalsed nõuded](https://confluence.ria.ee/pages/viewpage.action?pageId=47548375)

----

## MFN-de praktika

nt automaattestide MFN (X-tee testide automatiseerimise projektis)


## Riigi teiste asutuste MFN-e

- RIK
  - [IT profiil](http://www.rik.ee/et/asutusest/it-profiil) 
- RMIT
  - üldised mittefunktsionaalsed ja tehnilised nõuded
  - IT profiil

## Valdkondlikud MFN-id

- ___X-tee___ tuumtarkvara arendatakse ühiselt Soome riigiga. Vastavalt on ka MFN inglise keeles ja avaldatud Soome partnerasutuse GitHub-repos:
  - [X-Road Non-Functional Requirements](https://github.com/vrk-kpa/xroad-joint-development/blob/master/NFR.md) v1.2
- RIHA nõuded asuvad:
  - [arhitektuuriteatmikus](https://arhitektuur.riha.ee/)  
- teavevärav eesti.ee
  - [MFN](https://confluence.ria.ee/pages/viewpage.action?pageId=6619157) &#128274;

## Eelmised versioonid

- [RIA Mittefunktsionaalsed Nõuded 3.0-RELEASE](https://confluence.ria.ee/pages/viewpage.action?pageId=43385016) &#128274;
- Riigi Infosüsteemide Arenduskeskus (2006) [Mittefunktsionaalsete nõuete kirjeldamise juhend](https://www.ria.ee/public/publikatsioonid/Mittefunk_nouded.doc) v 0.2

## Muud

[Riigi Infosüsteemi mittefunktsionaalsed nõuded](https://www.ria.ee/riigiarhitektuur/wiki/doku.php?id=mfn) v 2.0-TRUNK<br>
[Riigi Infosüsteemi mittefunktsionaalsed nõuded](https://www.ria.ee/riigiarhitektuur/wiki/lib/exe/fetch.php?media=riigi_infosu%CC%88steemi_mittefunktsionaalsed_no_uded.pdf) v 1.0, kinnitatud Riigi Infosüsteemi peadirektori 09.04.2014 käskkirjaga nr 1-2/14-016

----

_Viimati muudetud: 28.11.2017_

