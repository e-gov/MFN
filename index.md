---
permalink: /
---

<img src='img/LOVID.png' style='width: 80px;'>

# Mittefunktsionaalsed nõuded
{: .no_toc}

v 4.0 (tööversioon) &nbsp;&nbsp; 04.12.2017

Märkus. Käesolev dokument on tööversioon. Ametlik, kinnitatud versioon avaldatakse RIA veebilehel.
{:.note}

Nõuetekogum on mõeldud kasutamiseks:<br>
- ___RIA arhitektidele, toote- ja projektijuhtidele___ -  tarkvara kavandamisel ja arendustööde tellimisel ning kontrollimisel<br>
- ___arendajatele___ - arenduslepingute täitmisel.

_Nõuded suunavad tellijat ja seejärel ka arendajat, pakkudes olulisemate nõuete valmissõnastusi ja toimides meelespeana. Lõppeesmärk on kasutajatele väärtust pakkuv ja turvaline tarkvara, mille arendus- ja käitluskulud on madalad; tarkvara, mida on võimalik agiilselt arendada ja mis on jätkusuutlik ka pikemas perspektiivis._

_Dokumendi varasema versiooniga võrreldes on mõned raskesti kohaldatavad või ebaselged nõuded kõrvaldatud. Mitmeid nõudeid on üritatud selgemalt sõnastada. Nõuete sõnastamisel on lähtutud rakendatavuse ja konkreetsuse printsiibist. Nõuded on liigitatud. Kus vaja, on nõuet lahti selgitatud. Järgides partnerasutuste (RIK, RMIT) head praktikat, on nõuded esitatud tabelina._

_Dokument loomulikult sa saa katta kõiki võimalikke mittefunktsionaalseid nõudeid. Meeles tasub pidada ka, et nõuded üksinda ei ole  imerohi, mis asendaks tarkvaraarenduses vajalikke kogemusi, teadmisi, talenti ja tööd._

_Võimalikest vigadest palume teada anda ja ettepanekuid dokumendi täiendamiseks teha arutelude algatamisega dokumendi [GitHub-repos](https://github.com/e-gov/MFN/issues)._ 

## Lühendid ja mõisted

___MFN___ - mittefunktsionaalsed nõuded; vt [mittefunktsionaalsed nõuded](https://et.wikipedia.org/wiki/Mittefunktsionaalsed_n%C3%B5uded) (Vikipeedia).<br>
___tarkvara___ - hõlmab ka dokumentatsiooni, sh kavandeid.

## Nõuded

{% assign ln = 0 %}

| Liik       | Nr                      | Nõude sõnastus   | Nõude selgitus |
|------------|:-----------------------:|------------------|----------------|
| {% increment ln %} {% capture lnimetus %}meta{% endcapture %} {% assign n = 0 %} | {{ ln }}.{% increment n %}<a id='#1.{{ lnimetus }}'></a> | Nõuete rakendamisel arvestada konkreetse tarkvara eripära. | Rakenduvad ainult need nõuded, mida konkreetse tarkvara iseloomu, ülesehituse ja kasutatavate komponentide kontekstis on mõistlik rakendada. |
| {{ ln }} meta | {{ ln }}.{% increment n %}<a id='#1.{{ lnimetus }}'></a> | Nõudeid rakendada hierarhia põhimõttel. | RIA MFN-i nõudeid tuleb rakendada kõigis RIA infosüsteemides. Valdkonna MFN määratleb valdkonna tarkvara spetsiifilised nõuded. Hanke MFN-i nõuded täpsustavad ja täiendavad asutuse või valdkonna nõudeid.<br>- ___X-tee___ tuumtarkvara arendatakse ühiselt Soome riigiga. Vastavalt on ka MFN inglise keeles ja avaldatud Soome partnerasutuse GitHub-repos: [X-Road Non-Functional Requirements](https://github.com/vrk-kpa/xroad-joint-development/blob/master/NFR.md)<br>- ___RIHA___ nõuded asuvad [arhitektuuriteatmikus](https://arhitektuur.riha.ee/)<br>- teabevärava ___eesti.ee___ [MFN](https://confluence.ria.ee/pages/viewpage.action?pageId=6619157) &#128274;<br> |
| {% increment ln %} {% capture lnimetus %}vorming{% endcapture %} {% assign n = 0 %} | {{ ln }}.{% increment n %}<a id='#1.{{ lnimetus }}'></a> | Andmebaasides ja rakendustes kasutada UTF-8 kodeeringut. |                |
| {{ ln }} vorming | {{ ln }}.{% increment n %}<a id='#1.{{ lnimetus }}'></a> | Ühe faili piires kasutada alati sama reavahetuse kodeeringut - kas Windowsi (`CR+LF; 0x0D0A; U+000D U+000A`) või Linux/Unix standardile vastavat (`LF; 0x0A; U+000A`). |                |
| vorming | {{ ln }}.{% increment n %}<a id='#1.{{ lnimetus }}'></a> | Kuupäeva, kuupäeva ja kellaaja, kellaaja, kestvuse ning ajaintervalli (perioodi) talletamisel tekstikujul lähtuda rahvusvahelisest standardist ISO 8601. | ___Kuupäevad___ kirjutatakse kujul `AAAA-KK-PP`. Näide: `2. juuni 2012` kirjutada kujul `2012-06-02`. ___Kellaajad___ kirjutatakse kujul `hh:mm:ss`, kus `hh` järgib 24-tunnist kellaajaformaati. Millisekundi täpsusega kellaaja teksti kujul esitamisel kasutatakse formaati `hh:mm:ss,nnnn`, kus `nnnn` on millisekundite arv. ___Kuupäev ja kellaaeg samas andmeväljas___ esitatakse kujul, kus kuupäevavormingu ja kellaajavorming vahele lisatakse täht `T`. ___Kestvus___ esitatakse kujul `P[ [<n>Y][<n>M][<n>D]][T[<n>H][<n>M][<n>S] ]` või `P<n>W`, kus `[…]` tähistab kombinatsiooni puudumise võimalikkust, `P` tähistab kestvuse määrangu algust, `<n>` tähendab kestvuse pikkust ja `Y`, `M`, `D`, `H`, `M` (pärast `T`-d, mis tähistab kellaajavorningu algust), `S` ja `W` tähistavad vastavalt kestust aastates, kuudes, päevades, tundides, minutites (`M` pärast `T`-d, mis tähistab kellaajavormingu algust), sekundites ja nädalates. ___Ajaintervallide___ kirjeldamiseks kasutatakse kahte sama täpsusega (kuupäev, kellaaeg või kuupäev ja kellaaeg) ajavormingut (algus ja lõpp), mis eraldatakse sümboliga `/`. |
| litsents | 4.{% increment lit %} | Tarkvara markeerida litsentsiga. | Teose autoriõigused tuleb selgelt välja tuua. Standardseks vahendiks selleks on litsents. Litsents esitatakse ühel või mõlemal alljärgnevatest viisidest: 1) LICENCE-fail repos; 2) litsentsi tekst iga faili päises. RIA põhimõte on arendada tarkvara avatult ja avaldada tarkvara vaba litsentsiga. Erandid turva- jm õigusega pandud piirangute korral. Soovitatav on kasutada [MIT litsentsi](https://en.wikipedia.org/wiki/MIT_License) - nii tagatakse paremini tarkvarade litsentsiline ühtesobivus. |
| moodulstruktuur | 5.{% increment mod %}<a id='#5.{{ mod }}'></a> | Rakenduse välissõltuvused peavad olema ilmutatult, selgelt välja toodud. | |
| moodulstruktuur | 5.{% increment mod %}<a id='#5.{{ mod }}'></a> | Rakendus peab olema väliste süsteemide tõrgete suhtes vastupanuvõimeline. | Välise süsteemi tõrge tohib mõjutada ainult sellest otseselt sõltuvate kasutuslugude toimimist. |
| moodulstruktuur | 5.{% increment mod %}<a id='#5.{{ mod }}'></a> | Rakendus peab olema tehniliselt tükeldatud vastavalt loogilisele jaotusele. Saadud osised peavad olema eraldi versioneeritavad ja paigaldatavad. |  Näiteks, kui rakendusel on eraldi turvakontekstidega liidesed ametnikule ja kodanikule, peab rakendus olema jaotatud kaheks eraldi liidesekomponendiks ning nende mõlema poolt kasutatavaks andmebaasiks. |
| keel | 6.{% increment keel %}<a id='#6.{{ keel }}'></a> | Lähtekoodi dokumentatsioon, lähtekood ise ning logiteated peavad olema läbivalt inglisekeelsed. |                |
| keel | 6.{% increment keel %}<a id='#6.{{ keel }}'></a> | Rakendustes kasutatud eestikeelsetele tekstidele kehtivad infotehnoloogia reeglid Eesti keele ja kultuuri keskkonnas EVS 8:2008. |                |
| testimine | 7.{% increment tst %}<a id='#7.{{ tst }}'></a> | Lähtekood peab olema varustatud ühiktestidega. |                |
| testimine | 7.{% increment tst %}<a id='#7.{{ tst }}'></a> | Tarkvara peab olema enne toodangusse paigaldamist läbinud turvatestimise. |                |
| koodi kvaliteet | {% increment c %} | Lõplik kood peab olema läbinud staatilise koodianalüüsi. | Kasutada otstarbekat tööriista: Java puhul [Checkstyle](https://github.com/checkstyle/checkstyle), [PMD](https://pmd.github.io/), [SonaQube](https://www.sonarqube.org/) vms; Javascripti puhul [ESLint](https://eslint.org/). Samuti kasutada arendusredaktoritesse sisseehitatud kontrollijaid. |
| frontend | {% increment c %} | Stiiliteave asetada CSS-failidesse. | Stiile ei tohiks sisse kirjutada HTML-teksti, ei `<style>` taagide vahelise tekstina ega `style`-atribuutidena. |
| frontend | {% increment c %} | Mahukate laadilehtede puhul kaaluda [Sass](http://sass-lang.com/)-i kasutamist. | Sass võib suurendada laadilehtede loetavust ja hallatavust.  |
| frontend | {% increment c %} | Järgida ajakohaseid veebistandardeid. | HTML5, CSS3 jms.  |
| frontend | {% increment c %} | Rakendus peab töötama veebisirvijaga, mida toetavad eID baastarkvara kaks viimast versiooni. | |
| frontend | {% increment c %} | Veebisirvija toe puudumisel andku rakendus veateade. | Kui kasutajaliides, mille poole kasutaja pöördub, ei ole ühilduv kasutatava veebisirvijaga, peab rakendus arusaadaval ja juhendaval viisil sellest kasutajat teavitama. |
| URL-id | {% increment c %} | Kasutada selge, ühtse mustriga, inimloetavaid veebiaadresse (URL-e). |                |
| URL-id | {% increment c %} | Igal lehel peab olema unikaalne veebiaadress. |                |
| URL-id | {% increment c %} | URL ei tohi sisaldada tundlikke isikuandmeid. |                |
| URL-id | {% increment c %} | URL ei tohi sisaldada sessioonivõtit. |                |
| teated | {% increment c %} | Vea- jm teated peavad oleva arusaadavad. | Muuhulgas peab rakendus asendama vaikimisi veateate (`404` vms) lehekülje, kuid säilitama algse HTTP vastuskoodi. |
| koodid | {% increment c %} | Objektid identifitseerida registrikoodide abil. | Riiklikesse registritesse kantavad objektid (isikud, katastriüksused jne) kantakse andmebaasi nende registrikoodiga, mida täiendab riigiprefiks vastavalt ISO3166-1 Alpha 2 standardile. Näiteks isikute sidumiseks süsteemi kasutajakontoga peab kasutama isikukoodi rahvastikuregistrist.<br>Eesti Vabariigi kodanik identifitseeritakse Eesti Vabariigi poolt väljastatud eIDga. Igasuguse muu identifitseerimisevahendi kasutamine peab olema selgelt põhjendatud.<br>Mittekodanike isikuidentifikaator saadakse järgmisel viisil: `riigikood + sookood + sünniaeg + [ dok_nr | id_riigis ]`, kus<br>`riigikood` - kolmekohaline ISO 3166-1 Alpha-3 standardile vastav riigi kood<br>`sookood` - soo identifikaator nii nagu Eesti Vabariigi isikukoodis<br>`sünniaeg` - sünniaeg formaadis `YYYYMMDD`<br>`id_riigis` - kui see on olemas, tuleb kasutada isiku koduriigi isikuidentifikaatorit. 16 kohta, 0-polsterdatud vasakult<br>`dok_nr` - kui isiku koduriigis isikuidentifikaatorit ei ole, siis kasutatakse isiku dokumendi numbrit. Dokumendi number, 16 kohta, 0-polsterdatud vasakult. |
| koodid | {% increment c %} | Rakendus ei tohi luua uut identiteedisüsteemi. Tuleb tugineda olemasolevatele riiklikele (ID-kaart) või põhiliste op-süsteemide süsteemidele (Kerberos jms). |  |
| autentimine | {% increment c %} | Väliste kasutajate, so. Eesti Vabariigi residentide ja EL teiste liikmesriikide residentide autentimislahenduse loomisel lähtuda dokumendist [Autentimislahendustele kehtivad nõuded](https://www.ria.ee/public/Arhitektuur/Autentimislahendustele-kehtivad-nouded-kavand.pdf). |  |
| rollihaldus | {% increment c %} | Rakenduse mitteavalike osade kasutajate rollid asuvad rakendusevälises LDAPs serveris või muus autentimislahenduses. Süsteem ei tohi realiseerida omaenda rollide haldamist. |  |
| väljumine | {% increment c %} | Süsteemist väljumine peab toimuma sõnaselgelt, kasutajale arusaadaval ja turvalisel viisil. | Kasutaja saab süsteemist väljuda kahel viisil: tema sessioon on pikem, kui sessiooni pikkuse seadistatav piirväärtus (eraldi määratletavad piirangud kogu sessioonile ning tegevuseta perioodile sessioonis) või kasutaja lõpetab sessiooni enda algatusel. |
| väljumine | {% increment c %} | Juhul kui rakenduse turvanõuded näevad seda ette, peab olema võimalus koheselt lõpetada kasutaja sessiooni nii, et kasutaja saaks arusaadava ja põhjendatud teate sessiooni lõpetamise kohta. |  |
| andmebaas | {% increment c %} | Andmebaasi kasutaval rakendusel on vähemalt kaks andmebaasikasutajat:<br>`<rakendus>` nimeline andmebaasi skeem kuulub andmebaasi kasutajale `<rakendus>` (roll `db owner`, skeemid ja seal paiknevad objektid kuuluvad sellele kasutajale).<br>`<rakendus>` nimelises andmebaasi skeemis on defineeritud `<rakendus>_app` nimeline kasutaja, kes omab ligipääsu (`SELECT`, `INSERT`, `UPDATE`, `DELETE`) ainult rakenduse käitamiseks vajalikele tabelitele, protseduuridele või funktsioonidele. |  |
| andmebaas | {% increment c %} | Ühest andmetabelist teise viitamisel tuleb kasutada välisvõtmeid (_foreign key_). Kõik välisvõtmed (_foreign key_) peavad olema indekseeritud mitteunikaalse indeksiga ja välisvõtmetena kirjeldatud. |  |
| andmebaas | {% increment c %} | Kõigis andmebaasi tabelites peab olema defineeritud `integer`-tüüpi primaarvõti, mis on surrogaatvõti. Primaarvõtmena ei tohi kasutada reaalse eluga seotud andmevälju. |  |
| andmebaas | {% increment c %} | Kõik primaarvõtmed (_primary key_) peavad olema indekseeritud unikaalse indeksiga. |  |
| andmebaas | {% increment c %} | Kui andmebaasis olevate andmete ISKE tervikluse klass on 2 või kõrgem, siis tuleb kõik klass 2 infot sisaldavad andmebaasi kirjed versioneerida. |  |
| andmebaas | {% increment c %} | Andmebaasi väljade pikkused tuleb andmekirjelduskeeles (DDL-is) kirjeldada sümbolites, mitte baitides. |  |
| andmebaas | {% increment c %} | Päringulaused ei tohi sisaldada konstantidena sisse kirjutatud  päringutingimuse võrdlusväärtusi. | Kasutada päringumuutujaid (_variable binding_). |
| andmebaas | {% increment c %} | Andmebaasi objektide nimetused peavad olema inglisekeelsed. Nimetused tohivad sisaldada ainult Latin1 (ISO8859-1) kodeeringu tähti `a-z; A-Z`, numbreid `0-9`, ning alakriipsu `_`. Objektide nimetused ei tohi alata numbritega. Andmebaasiobjektide nimed peavad olema semantilised st. objekti tähendust avavad. |  |
| andmebaas | {% increment c %} | Rakendus peab olema tabelite [partitsioneerimise](http://en.wikipedia.org/wiki/Partition_%28database%29) suhtes agnostiline st. tabelite partitsioneerimisstruktuuride muutmine ei tohi mõjutada rakenduse tööd. |  |
| logi | {% increment c %} | Rakenduse logimine peab olema organiseeritud kasutades selleks ettenähtud standardseid vahendeid viisil, mis võimaldab rakenduse administraatoril määratleda ja muuta logide väljundit (vähemalt fail, andmebaas, syslogd), logimise taset ja logimise formaati. Igasugune logimine muul viisil on keelatud. |  |
| logi | {% increment c %} | Java rakenduste korral logitakse [SLF4J](vt http://www.slf4j.org) raamistiku abil. |  |
| logi | {% increment c %} | Süsteemi iga eraldi paigaldatav osa peab logimisel (näiteks aadressil heartbeat.json) väljastama masinloetaval kujul oma nime ja versiooninumbri, oluliste väliste süsteemide oleku, viimase käivitamise aja, pakendamise aja ning serveriaja. |  |
| logi | {% increment c %} | Logid kirjutatakse inglise keeles (välja arvatud kasutajale näidatud teated). |  |
| logi | {% increment c %} | Turvalisuse seisukohalt kriitilised sündmused (sisenemine, väljumine, rolli muut(u)mine) ning tegevused, mis toovad kaasa rahalisi või juriidilisi tagajärgi, logitakse eraldi konfigureeritavasse turvalogisse. |  |
| paigaldus | {% increment c %} | Kui funktsionaalsetes nõuetes pole sõnaselgelt teisiti sätestatud, ei tohi rakendus paigaldamise järel teda sisaldavat süsteemi mitte mingil viisil muuta. Keelatud on muu hulgas keskkonnamuutujatesse kirjutamine, kohalikku failisüsteemi failide loomine jms. | Lubatud on ainult logide kirjutamine. Lubatud on ka operatsioonisüsteemi toimimise sekundaardsed efektid. |
| paigaldus | {% increment c %} | Rakendus tohib e-kirja saata ainult välise postiagendi (näiteks Postfix) kaudu. |  |
| paigaldus | {% increment c %} | Rakenduse funktsionaalsuses tuleb selgelt eraldada avaliku teenuse liides muudest mitteavalikest, sisemistest, konfigureerimis jms. liidestest. |  |
| paigaldus | {% increment c %} | Rakendus peab olema loodud sõltumatuna rakendusserveri tarkvarast. | Rakendust peab olema võimalik konfiguratsioonimuudatuste abil paigaldada teisele samatüübilisele rakendusserverile. Kui see ei ole võimalik tuleb rakendusele luua sobituspaketid põhiliselt kasutatavate rakendusserverite jaoks. |
| paigaldus | {% increment c %} | Kõik rakenduse versiooniuuendused (sealhulgas muudatused andmebaasi struktuuris ja koodis) peavad kuni järgmise versiooniuuenduseni olema täielikult tagasi pööratavad st. koos versiooni uuendusega peavad olema loodud vahendid ja kirjeldatud protseduurid versiooniuuenduse tagasi võtmiseks. |  |
| paigaldus | {% increment c %} | Rakendus ei tohi eeldada paigalduskeskkonna turvalisust. Kõik liidesed rakenduse eri osade vahel peavad olema vajadusel kaitstavad kahepoolset tuvastamist ja krüpteerimist võimaldava protokolliga. |  |
| paigaldus | {% increment c %} | Rakendusservereid peab olema võimalik lisada teenust pakkuvasse klastrisse ja sealt eemaldada vastavalt vajadusele. |  |
| paigaldus | {% increment c %} | Rakendus ei tohi kasutada konfigureerimata viiteid failidele või välistele süsteemidele st. kõik viited peavad olema programmikoodi välised. |  |
| paigaldus | {% increment c %} |  Kõik andmebaasiühendused tuleb kirjeldada täispika URI abil. Java rakendustes kasutatakse JNDI ühendusi. |  |
| teated | {% increment c %} | Andmebaasi JNDI objekti Datasource'i nimetamisel tuleb kasutada prefiksit `jdbc` ning ühesõnaliste lühendite korral väiketähti. Nt: `jdbc/system1`, `jdbc/system2` jne. |  |
| paigaldus | {% increment c %} | Rakenduse (RIA poolt hallatavasse serverisse) pakendamine, paigaldamine, uuendamine, muudatuse taastamine ja testide käivitamine peavad olema automatiseeritud standardse üldkasutatava vahendi abil (Maven vms). |  |
| paigaldus | {% increment c %} | Ehitatud pakke nimi peab sisaldama projekti nime, keskkonna nime ja versiooni ning tohib sisaldada ainult tähemärke `[a-z;0-9]` ja `-` (miinus) ja `_` (alakriips) (nt `projektinimi-keskkond—1_0_23`). |  |
| paigaldus | {% increment c %} | Rakenduse andmebaasi või andmeskeemi paigaldamine ei tohi nõuda punktis erilisi kasutajaõigusi. |  |
| paigaldus | {% increment c %} | Rakendused paigaldatakse ainult lähtekoodihoidlast, selle üheselt viidatud harust. |  |
| turve | {% increment c %} | Kui ei ole määratud teisiti, peab rakendus olema kasutatav ISKE klassile `K2T2S2` vastavate süsteemide loomisel. |  |
| turve | {% increment c %} | Süsteem ei tohi võimaldada kasutajale ligipääsu süsteemi toimimise informatsioonile, nagu failide täisnimed, kutsepinud (_stack trace_) jms. |  |
| turve | {% increment c %} | Kaitsmata avalik võrguliiklus ei ole lubatud. Igasugune avalik võrguliiklus on krüpteeritud. TLS keskkonna parameetrid on administraatori, mitte arendaja kontrolli all. Erandjuhul, kui edastatav informatsioon ei sisalda konfidentsiaalseid andmeid, on lubatud andmete edastamine krüpteerimata kujul, kuid viisil, mis võimaldab andmete vastu võtjal veenduda saadetise tervikluses st. allkirjastatult või ajatembeldatult (X-tee turvaserveri seadistuse edastamise näide). |  |
| turve | {% increment c %} | Krüptograafiliste algoritmide ja meetodite valmisel lähtuda kehtivast RIA tellitud [krüptograafiliste algoritmide elutsükli uuringust](https://www.ria.ee/ee/kruptograafiliste-algoritmide-elutsukli-uuringud.html). |  |
| aadressid | {% increment c %} | Eesti aadressiandmete sisestamisel, kuvamisel ja hoidmisel lähtuda Vabariigi Valitsuse 8. oktoobri 2015. a määrusest nr 103 „Aadressiandmete süsteem“. |  |
| tegevusalad | {% increment c %} | Eesti tegevusalade andmete sisestamisel, kuvamisel ja hoidmisel lähtuda Vabariigi Valitsuse 10. jaanuari 2008. a määrusest nr 11 „Klassifikaatorite süsteem“ ja kasutada EMTAK infosüsteemis kehtivat klassifikaatorit. |  |

## Viiteid

[Riigipilve MFN BI allnõukogule](https://confluence.ria.ee/pages/viewpage.action?pageId=19562975) &#128274;

[RIA MFN dokumendi arendustsükkel](https://confluence.ria.ee/pages/viewpage.action?pageId=40698241) &#128274;

[RIA mittefunktsionaalsed nõuded](https://confluence.ria.ee/pages/viewpage.action?pageId=47548375) &#128274;

RIK arendusnõuded &#128274;<br>[IT profiil](http://www.rik.ee/et/asutusest/it-profiil) 

RMIT üldised mittefunktsionaalsed ja tehnilised nõuded &#128274;<br>
IT profiil &#128274;

[RIA Mittefunktsionaalsed Nõuded 3.0-RELEASE](https://confluence.ria.ee/pages/viewpage.action?pageId=43385016) &#128274; (eelmine versioon)

Riigi Infosüsteemide Arenduskeskus (2006) [Mittefunktsionaalsete nõuete kirjeldamise juhend](https://www.ria.ee/public/publikatsioonid/Mittefunk_nouded.doc) v 0.2

[Riigi Infosüsteemi mittefunktsionaalsed nõuded](https://www.ria.ee/riigiarhitektuur/wiki/doku.php?id=mfn) v 2.0-TRUNK<br>
[Riigi Infosüsteemi mittefunktsionaalsed nõuded](https://www.ria.ee/riigiarhitektuur/wiki/lib/exe/fetch.php?media=riigi_infosu%CC%88steemi_mittefunktsionaalsed_no_uded.pdf) v 1.0, kinnitatud Riigi Infosüsteemi peadirektori 09.04.2014 käskkirjaga nr 1-2/14-016

----

_Viimati muudetud: 04.12.2017_

