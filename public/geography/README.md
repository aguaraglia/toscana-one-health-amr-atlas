# Geografia pubblica

La cartografia pubblica dell'edizione Toscana comprende:

- `atlas_region.geojson`: confine regionale ISTAT 2026 (codice 09);
- `atlas_provinces.geojson`: 10 unità sovracomunali ISTAT 2026: Massa-Carrara (MS 045), Lucca (LU 046), Pistoia (PT 047), Firenze (FI 248, città metropolitana), Livorno (LI 049), Pisa (PI 050), Arezzo (AR 051), Siena (SI 052), Grosseto (GR 053), Prato (PO 100);
- `atlas_municipalities.geojson`: 273 comuni ISTAT al 1/1/2026.

I file sono letti in UTF-8 dal DBF ISTAT.

Gli studi della letteratura curata stanno in layer distinti sotto `public/data/`. Sei strutture nominate sono geocodificate tramite OSM Nominatim (AOU Pisana-Cisanello, AOU Meyer, AOU Careggi, AOU Senese-Le Scotte, Ospedale San Luca di Lucca, Ospedale Didattico Veterinario di Pisa). Gli studi con città, aree protette o province nominate usano i poligoni ISTAT corrispondenti; gli studi regionali usano il contorno regionale. Nessuna RSA, azienda agricola, canile, depuratore non nominato o struttura non nominata è localizzata.
