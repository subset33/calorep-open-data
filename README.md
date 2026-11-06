# Calorep food catalogue

Contains data from Open Food Facts (https://world.openfoodfacts.org/data).
The catalogue database is available under the Open Database License 1.0:
https://opendatacommons.org/licenses/odbl/1-0/
Open Food Facts individual database contents are available under the DbCL:
https://opendatacommons.org/licenses/dbcl/1-0/

Unzip the archive. Each part is a gzip-compressed JSON array of rows.
Each directory has a manifest with file hashes and row counts. The row columns
below are listed in order. IDs refer to the same source generation throughout.

- editorial/groups: id, name, family_id, preparation, storage, product_count
- editorial/products: id, group_id, name, brand, language, basis, calories_milli, protein_mg, carbs_mg, fat_mg, url
- editorial/documents: id, group_id, product_id, name, brand
- editorial/brands: norm, name, support
- extended/representatives: id, identity_key, group_id, family_id, preparation, storage, basis, source_id, calories_milli, support, kind, legacy_id
- extended/links: group_id, brand_scope, food_id

Join extended representatives to editorial products by source_id = id and to
editorial groups by group_id = id. The representative carries its own energy;
the linked product carries its macros. Nutrition uses fixed-point milligrams
and milli-kilocalories per basis. Metadata describes families and food profiles.
Generics are the separately versioned per-100-g catalogue. Localization and
portion data augment the profiles. Search packs are the published lookup data.
