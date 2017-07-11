## Global reference files/control paramteres
---
#### `sector.csv`

id|name|colour
---|---|---
other_sectors_grouped|Other sectors (grouped)|grey_mid

The `other-sectors-grouped` sector is used with the multilateral profiles. It is based on a business rule that groups sectors together. The logic is: get top 5 sectors for an organization and group all the other sectors into one category.

---

#### `oda_bundle.csv`

UPDATE global.oda_bundle
SET id = 'gis_nngos' WHERE id = 'gpgs_nngos';

"Global public goods & NNGOs" was changed to "Global initiatives & NNGOs".
