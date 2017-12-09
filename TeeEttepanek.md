---
permalink: TeeEttepanek
---

# Tee ettepanek

- uue nõude lisamiseks
- aegunud nõude eemaldamiseks
- nõude sõnastuse parandamiseks
- või nõuete refaktoorimiseks (ühendamiseks, lahkulöömiseks).

Tee ettepanek:
- <a href='https://github.com/e-gov/MFN/issues' target='_new'>avades issue</a> MFN-i repos
- esitades _pull request_-i [MFN-i repos](https://github.com/e-gov/MFN/)
- saates e-kirja RIA arhitektide siselisti.

Igaühel on õigus teha ettepanekuid nõuete lisamiseks, ümbersõnastamiseks ja ka eemaldamiseks. Ettepanekud arutatakse läbi. 

Hea nõue:
- suunab tellijat ja seejärel ka arendajat
- ei piirdu üksiku kogemusega, vaid pakkub standardset lahendusteed sageliesinevale, tüüpilisele vajadusele või probleemile
- toimib ka meelespeana (et olulist asja ära ei unustataks).

Nõuete lõppeesmärk on, et tekiks kasutajatele väärtust pakkuv ja turvaline tarkvara, mille arendus- ja käitluskulud on madalad; tarkvara, mida on võimalik agiilselt arendada ja mis on jätkusuutlik ka pikemas perspektiivis.

Vt ka:
- [mittefunktsionaalsed nõuded](https://et.wikipedia.org/wiki/Mittefunktsionaalsed_n%C3%B5uded) (Vikipeedia)
- Riigi Infosüsteemide Arenduskeskus (2006) [Mittefunktsionaalsete nõuete kirjeldamise juhend](https://www.ria.ee/public/publikatsioonid/Mittefunk_nouded.doc) v 0.2.

Nõude `staatus` on kasutusel nõude elukäigu järgu esitamiseks, nt hiljuti lisatud (`UUS`) ja eriti oluliste nõuete (`NB!`) markeerimiseks. Võimalikud on ka muud staatused, nt `AEGUNUD` (_deprecated_). Vaikimisi on nõude staatus 'Kehtib'.

Loetavuse huvides on nõued organiseeritud ___kategooriatesse___. Nõudel peaks olema selge, lühike, üldjuhul kindlas kõneviisis ___sõnastus___, mida kommenteerib, vajadusel ka pehmendab ___selgitus___. Nõuded nummerdatakse.

Tehniliselt kirjeldatakse nõue [MFN repo](https://github.com/e-gov/MFN/) kasutas `_data` asuvas YAML-failis `Nouded.yml`.
