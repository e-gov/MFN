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

| Liik       | Nr                      | Nõude sõnastus   | Nõude selgitus |
|------------|:-----------------------:|------------------|----------------|
| meta       | {% increment c %} | Nõuete rakendamisel arvestada konkreetse tarkvara eripära. | Rakenduvad ainult need nõuded, mida konkreetse tarkvara iseloomu, ülesehituse ja kasutatavate komponentide kontekstis on mõistlik rakendada. |
| meta       | {% increment c %} | Nõudeid rakendada hierarhia põhimõttel. | RIA MFN-i nõudeid tuleb rakendada kõigis RIA infosüsteemides. Valdkonna MFN määratleb valdkonna tarkvara spetsiifilised nõuded. Hanke MFN-i nõuded täpsustavad ja täiendavad asutuse või valdkonna nõudeid.<br>- ___X-tee___ tuumtarkvara arendatakse ühiselt Soome riigiga. Vastavalt on ka MFN inglise keeles ja avaldatud Soome partnerasutuse GitHub-repos: [X-Road Non-Functional Requirements](https://github.com/vrk-kpa/xroad-joint-development/blob/master/NFR.md)<br>RIHA nõuded asuvad [arhitektuuriteatmikus](https://arhitektuur.riha.ee/)<br>teabevärava eesti.ee [MFN](https://confluence.ria.ee/pages/viewpage.action?pageId=6619157) &#128274; |
| andmevorming | {% increment c %} | Andmebaasid ja rakendused peavad kasutama UTF-8 kodeeringut. |                |
| andmevorming | {% increment c %} | Ühe faili piires kasutatakse alati sama reavahetuse kodeeringut - kas Windowsi standardile vastavat (`CR+LF; 0x0D0A; U+000D U+000A`) või Linux/Unix standardile vastavat (`LF; 0x0A; U+000A`). |                |
| litsents | {% increment c %} | Tarkvara tuleb markeerida litsentsiga. | Teose autoriõigused tuleb selgelt välja tuua. Standardseks vahendiks selleks on litsents. Litsents esitatakse ühel või mitmel alljärgnevatest viisidest: 1) LICENCE-fail repos; 2) litsentsi tekst iga faili päises. RIA põhimõte on arendada tarkvara avatult ja avaldada tarkvara vaba litsentsiga, v.a turva- jm õigusega pandud piirangud. Soovitatav on kasutada [MIT litsentsi](https://en.wikipedia.org/wiki/MIT_License) - nii tagatakse paremini tarkvarade litsentsiline ühtesobivus. |
| tõrkekindlus | {% increment c %} | Rakenduse liidesed peavad olema tõrkekindlad. Välise süsteemi tõrge tohib mõjutada ainult sellest otseselt sõltuvate kasutuslugude toimimist. |                |
| moodulehitus | {% increment c %} | Rakendus peab olema tehniliselt tükeldatud vastavalt loogilisele jaotusele. Saadud osised peavad olema eraldi versioneeritavad ja paigaldatavad. |  Näiteks, kui rakendusel on eraldi turvakontekstidega liidesed ametnikule ja kodanikule, peab rakendus olema jaotatud kaheks eraldi liidesekomponendiks ning nende mõlema poolt kasutatavaks andmebaasiks. |
| keel | {% increment c %} | Lähtekoodi dokumentatsioon, lähtekood ise ning logiteated peavad olema läbivalt inglisekeelsed. |                |
| testimine | {% increment c %} | Lähtekood peab olema varustatud ühiktestidega. |                |
| koodi kvaliteet | {% increment c %} | Lõplik kood peab olema läbinud staatilise koodianalüüsi. | Kasutada otstarbekat tööriista: Java puhul [Checkstyle](https://github.com/checkstyle/checkstyle) ja [PMD](https://pmd.github.io/) vms; Javascripti puhul [ESLint](https://eslint.org/). Samuti kasutada arendusredaktoritesse sisseehitatud kontrollijaid. |
| frontend | {% increment c %} | Stiiliteave asetada CSS-failidesse. | Stiile ei tohiks kasutada HTML-tekstis `<style>` taagide vahel antud tekstina ega `style`-atribuutide abil. |
| frontend | {% increment c %} | Mahukate laadilehtede puhul kaaluda [Sass](http://sass-lang.com/)-i kasutamist. | Võib suurendada laadilehtede loetavust ja hallatavust.  |
| frontend | {% increment c %} | Järgida ajakohaseid veebistandardeid. | HTML5, CSS3 jms.  |
| frontend | {% increment c %} | Rakendus peab töötama veebisirvijaga, mida toetavad eID baastarkvara kaks viimast versiooni. | HTML5, CSS3 jms.  |
| frontend | {% increment c %} | Veebisirvija toe puudumisel anda veateade. | Kui kasutajaliides, mille poole kasutaja pöördub, ei ole ühilduv kasutatava veebisirvijaga, peab rakendus arusaadaval ja juhendaval viisil sellest kasutajat teavitama. |
| URL-id | {% increment c %} | Kasutada selge, ühtse mustriga, inimloetavaid veebiaadresse (URL-e). |                |
| URL-id | {% increment c %} | Igal lehel peab olema unikaalne veebiaadress. |                |
| URL-id | {% increment c %} | URL ei tohi sisaldada tundlikke isikuandmeid. |                |
| URL-id | {% increment c %} | URL ei tohi sisaldada sessioonivõtit. |                |
| teated | {% increment c %} | Vea- jm teated peavad oleva arusaadavad. | Muuhulgas, rakendus peab asendama vaikimisi veateate (`404` vms) lehekülje, kuid säilitama algse HTTP vastuskoodi. |
| koodid | {% increment c %} | Objektid identifitseerida registrikoodide abil. | Riiklikesse registritesse kantavad objektid (isikud, katastriüksused jne) kantakse andmebaasi nende registrikoodiga, mida täiendab riigiprefiks vastavalt ISO3166-1 Alpha 2 standardile. Näiteks isikute sidumiseks süsteemi kasutajakontoga peab kasutama isikukoodi rahvastikuregistrist.<br>Eesti Vabariigi kodanik identifitseeritakse Eesti Vabariigi poolt väljastatud eIDga. Igasuguse muu identifitseerimisevahendi kasutamine peab olema selgelt põhjendatud.<br>Mittekodanike isikuidentifikaator saadakse järgmisel viisil: `riigikood + sookood + sünniaeg + [ dok_nr | id_riigis ]`, kus<br>`riigikood` - kolmekohaline ISO 3166-1 Alpha-3 standardile vastav riigi kood<br>`sookood` - soo identifikaator nii nagu Eesti Vabariigi isikukoodis<br>`sünniaeg` - sünniaeg formaadis `YYYYMMDD`<br>`id_riigis` - kui see on olemas, tuleb kasutada isiku koduriigi isikuidentifikaatorit. 16 kohta, 0-polsterdatud vasakult<br>`dok_nr` - kui isiku koduriigis isikuidentifikaatorit ei ole, siis kasutatakse isiku dokumendi numbrit. Dokumendi number, 16 kohta, 0-polsterdatud vasakult. |
| teated | {% increment c %} |  |  |
| teated | {% increment c %} |  |  |
| teated | {% increment c %} |  |  |
| teated | {% increment c %} |  |  |
| teated | {% increment c %} |  |  |
| teated | {% increment c %} |  |  |
| teated | {% increment c %} |  |  |
| teated | {% increment c %} |  |  |
| teated | {% increment c %} |  |  |
| teated | {% increment c %} |  |  |
| teated | {% increment c %} |  |  |
| teated | {% increment c %} |  |  |




8.2 

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

