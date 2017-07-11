## Global reference files/control paramteres

#### `sector.csv`

id|name|colour
---|---|---
other-sectors-grouped|Other sectors (grouped)|grey-mid

The `other-sectors-grouped` sector is used with the multilateral profiles. It is based on a business rule that groups sectors together. The logic is: get top 5 sectors for an organization and group all the other sectors into one category.

#### `oda_bundle.csv`

UPDATE global.oda_bundle
SET id = 'gis-nngos' WHERE id = 'gpgs-nngos';

"Global public goods & NNGOs" was changed to "Global initiatives & NNGOs".
