## Global reference files/control paramteres
---
#### `sector.csv`

id|name|colour
---|---|---
other_sectors_grouped|Other sectors (grouped)|grey_mid

The [`other-sectors-grouped`](https://github.com/devinit/datahub-cms/blob/master/global/sector.csv#L16) sector is used with the [multilateral profiles](http://data.devinit.org/#!/multilaterals). It is based on a business rule that groups sectors together. The logic is: get top 5 sectors for an organization and group all the other sectors into one category.

---

#### `oda_bundle.csv`

UPDATE global.oda_bundle
SET id = 'gis_nngos' WHERE id = ['gpgs_nngos'](https://github.com/devinit/datahub-cms/blob/master/global/bundle.csv#L5);

"Global public goods & NNGOs" was changed to "Global initiatives & NNGOs".
