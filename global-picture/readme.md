# Global picture related narratives and refrence files go here.

#### `global_picture.theme` table definition

```
data_hub=# \d global_picture.theme
           Table "global_picture.theme"
      Column       |       Type        | Modifiers 
-------------------+-------------------+-----------
 id                | character varying | not null
 name              | character varying | not null
 default_indicator | character varying | not null
 position          | smallint          | not null
Indexes:
    "global_picture_theme_pkey" PRIMARY KEY, btree (id)
    "theme_default_indicator_key" UNIQUE CONSTRAINT, btree (default_indicator)
    "theme_name_key" UNIQUE CONSTRAINT, btree (name)
    "theme_position_key" UNIQUE CONSTRAINT, btree ("position")
Check constraints:
    "valid_position" CHECK ("position" > 0)
Foreign-key constraints:
    "global_picture_theme_default_indicator_fkey" FOREIGN KEY (default_indicator) REFERENCES indicator(id) ON UPDATE CASCADE ON DELETE RESTRICT
Referenced by:
    TABLE "indicator" CONSTRAINT "global_picture_indicator_theme_fkey" FOREIGN KEY (theme) REFERENCES theme(id) ON UPDATE CASCADE ON DELETE RESTRICT
```

#### `global_picture.indicator` table definition

NOTE: a number of columns will be deleted from this table when we finish. It's here for your temporary information.

```
              Table "global_picture.indicator"
           Column            |       Type        | Modifiers 
-----------------------------+-------------------+-----------
 series                      | character varying | 
 id                          | character varying | not null
 type                        | character varying | 
 parent                      | character varying | 
 name                        | character varying | 
 columns                     | character varying | 
 description                 | character varying | 
 default_scale               | character varying | 
 theme                       | character varying | 
 map_theme                   | character varying | 
 theme_position              | smallint          | 
 global_picture_colour_ramp  | character varying | 
 uom                         | character varying | 
 uom_display                 | character varying | 
 source                      | character varying | 
 calculation                 | character varying | 
 format                      | character varying | 
 high_or_low                 | character varying | 
 range                       | character varying | 
 interpolated                | character varying | 
 missing_donor               | character varying | 
 missing_recipient           | character varying | 
 laymans_decription          | character varying | 
 laymans_heading             | character varying | 
 source_link                 | character varying | 
 staging                     | character varying | 
 theme_year                  | character varying | 
 notes                       | character varying | 
 appear_in_bubble_chart      | smallint          | 
 include_in_methodology_page | smallint          | 
Indexes:
    "global_picture_indicator_pkey" PRIMARY KEY, btree (id)
Check constraints:
    "valid_theme_position" CHECK (theme_position > 0)
Foreign-key constraints:
    "global_picture_indicator_theme_fkey" FOREIGN KEY (theme) REFERENCES theme(id) ON UPDATE CASCADE ON DELETE RESTRICT
Referenced by:
    TABLE "theme" CONSTRAINT "global_picture_theme_default_indicator_fkey" FOREIGN KEY (default_indicator) REFERENCES indicator(id) ON UPDATE CASCADE ON DELETE RESTRICT
```

