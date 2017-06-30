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

