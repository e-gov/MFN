---
permalink: Kasutuslugu
---

# Kasutusloo standard (Gherkin eesti dialekt)

Käesolev juhis esitab standardse formaadi (keele) kasutus- ja testilugude kirjapanemiseks. Formaat on:

- struktuurne
- ühtaegu nii inimloetav kui ka masintöödeldav
- toetatud erinevate arendusvahendite poolt.

Formaadi aluseks on BDD (*Behavior Driven Development*, "käitumispõhine arendus") arendusprotsessis defineeritud Gherkin keel, mida on mugandatud eesti keelele vastavaks.

Formaati saab kasutada nii kasutuslugude ja -juhtude (ingl *use case*, *user story*) kui ka testilugude ja -stsenaariumite kirjapanemiseks. (Kasutuslugu on tavaliselt ühtlasi ka testilugu). Järgnevas kasutame mõistet "testilugu".

## Formaat

Testilood salvestatakse failides. Faili nimekuju on `<omaduse-kirjeldus>.feature`. Iga  `.feature` fail sisaldab ühe testitava omaduse (ingl *feature*) testilugusid.

Testilugu on kirja pandud struktuurses keeles (nn Gherkin süntaksi eestikeelne mugandus):

- testilool on sildid (ingl *tag*), mis aitavad neid struktureerida (algab märgiga `@`);
- testilool on nimetus (märgendiga `Stsenaarium` või `Raamstsenaarium`);
- testiloos kirjeldatakse mingi olukord (märgendid `Eeldades` või `Taust`), toiming (märgend `Kui`) ja oodatav tulemus (`Siis`, `Kuid`);
- nii olukorra, toimingu kui ka oodatava tulemuse kirjeldus koosneb ühest või enamast sammust (ingl *step*); sammude järjekord näidatakse loogikatehtega *Ja*.

Testid liigitatakse omaduste ja stsenaariumite sildistamise abil. Kasutatavate siltide tähendus on järgmine:

- `@api` - API testid;
- `@needs-decision` - stsenaarium ootab otsuseid;
- `@manual` - stsenaarium on mõeldud käsitsi testimiseks (kuid võib olla läbitav ka automaattestide abil);
- `@mod-<name>` - testitava mooduli nimi;
- `@noauto` - stsenaariumit pole võimalik või mõttekas automaatselt testida;
- `@no-story-or-req` - stsenaariumil puudub viide kasutusloole või nõudele;
- `@req-<id>` - stsenaarium katab märgitud nõuet;
- `@story-<id>` - stsenaarium katab märgitud kasutuslugu (juhul, kui kasutus- ja testilugude vahel pole üksühest vastavust);
- `@ts-<id>` - stsenaariumi identifikaator.

Kommentaarid lisatakse reaalguse tärgi `#` abil.

## Näide

```gherkin
# X süsteemitestid 
# Käsitsitestimise stsenaarim TS-016

Omadus: Kasutajale on võimalik lisada rollimääranguid

@mod-pas
 @story-pas-3
 @manual
 @ts-016

 Stsenaarium: Endale rollimäärangu lisamine

 Eeldades kasutajal on konto
 Ja kasutajal on kehtiv rollimäärang "Peakasutaja"
 Ja kasutajal puudub rollimäärang "Kandidaat"
 Ja kasutaja on sisse logitud
 Ja kasutajal on avatud enda andmete muutmise vorm

 Kui kasutaja lisab kasutajale rolli "Kandidaat"
 Ja kasutaja salvestab vormi
 Siis kasutajale väljastatakse teade operatsiooni nurjumise kohta
 Ja kasutajal puudub rollimäärang "Kandidaat"
```

## Arendusvahendite tugi

Näited:

- VSCode Cucumber (Gherkin) Language Support - süntaksivärvimist jm võimalusi pakkuv pistikmoodul tekstiredaktorile Visual Studio Code
- behave, Gherkin testilugude automeerimise raamistik.
