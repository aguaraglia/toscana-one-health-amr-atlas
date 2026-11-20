# Toscana One Health AMR Atlas

Edizione regionale `toscana_amr_atlas`, pubblicata da Codex Vitae ETS sulla stessa
base delle edizioni Piemonte e Friuli Venezia Giulia.

## Stato

La letteratura pubblicata con collegamento territoriale esplicito alla Toscana
è concentrata su Pisa (AOU Pisana-Cisanello e l'Ospedale Didattico Veterinario)
e su Firenze (Careggi e Meyer). Ne restano 60 inclusi (20 novembre 2026).

Sei strutture nominate, georiferite con Nominatim (© OpenStreetMap
contributors, ODbL):

- AOU Pisana, Ospedale di Cisanello: 11 studi;
- AOU Meyer: 7 studi;
- Ospedale Didattico Veterinario di Pisa: 4 studi;
- AOU Careggi: 3 studi;
- AOU Senese, Le Scotte: 2 studi;
- Ospedale San Luca di Lucca: 1 studio.

Per gli studi che citano genericamente l'ospedale universitario di Pisa il
segnaposto è la sede di Cisanello. Oltre alle strutture, la mappa usa comuni,
province, aree nominate e il contorno regionale (28 strutture, 9 comuni,
4 province, 2 aree nominate, 17 studi regionali). Uno studio che tocca più
province conta in ciascuna: Pisa 20, Firenze 13, Lucca 5, Livorno 4, Siena 4,
Grosseto 3, Prato 2, Pistoia 1, Massa-Carrara 1, Arezzo 0.

L'edizione pubblica anche AR-ISS 2024 (copertura 97,1%, rete regionale,
CC BY 4.0) e AIFA Open Data 2024, antibatterici J01 (CC BY 4.0).

Sei layer (AMR umana, veterinaria compresi gli animali d'affezione, alimentare,
ambientale, fauna selvatica, contorno regionale):

- AMR umana: 8 elementi, 29 studi (5 punti ospedalieri; comuni di Firenze, Prato e Pistoia);
- AMR veterinaria: 3 elementi, 6 studi (Ospedale Didattico Veterinario; province di Lucca e di Pisa e Lucca);
- AMR alimentare: 1 elemento (regione);
- AMR ambientale: 3 elementi (comuni di Prato, Livorno e Orbetello);
- AMR nella fauna selvatica: 5 elementi, 7 studi;
- studi a scala regionale: 1 elemento, 14 studi umani.

I layer vuoti e le aree senza segnaposto sono nessuna evidenza pubblicata,
non resistenza zero. Ogni popup cita lo studio e il DOI (o il record PubMed
se il DOI non è assegnato) e ricorda che il segnaposto è il luogo dello
studio, non una prevalenza.

Confini ISTAT 2026 (273 comuni, 10 unità sovracomunali, regione 09), letti in
UTF-8. ARS Toscana, Regione Toscana, AOU Careggi, AOU Meyer, AOU Pisana,
AOU Senese, IZSLT e il PDF OsMed sono esclusi: vedi
`metadata/EXCLUDED_SOURCES.md`.

Il conteggio in homepage e in pubblicazioni legge
`public/data/literature-catalog.json` (60).

## Pagine

Sorgente su `main`. Il sito statico è pubblicato dal branch `gh-pages`
(GitHub Pages, cartella `/`). Nessun file `CNAME`. Analitica: GoatCounter
`https://atlanteamr.goatcounter.com/count`, come le edizioni Piemonte e
Friuli Venezia Giulia.

## Build locale

```bash
python3 -m http.server 8000
```

Aprire `http://localhost:8000/`.

Per rigenerare i dati pubblici servono gli input in `raw/` e, per i confini,
l'archivio ISTAT indicato in `metadata/SNAPSHOTS.tsv`. I DBF ISTAT si leggono
in UTF-8:

```bash
pip install -r requirements-geodata.txt
python3 scripts/build_istat_geography.py --source-root <Limiti01012026_g> --output-root public/geography
python3 scripts/build_literature_catalog.py
python3 scripts/build_study_evidence_layers.py
```

## Directory

- `public/`: dati e asset approvati per il sito;
- `metadata/`: fonti, snapshot, ambito pubblico e fonti escluse;
- `raw/`: curatela, esummary e risposte Nominatim;
- `scripts/`: ricostruzione del catalogo e dei layer;
- `private/`: nessun dato riservato in questa edizione.
