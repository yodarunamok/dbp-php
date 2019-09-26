# dbp-php

For some time now I've wanted a really powerful database abstraction class. My first stab at this grew from my first
ever PHP project and is called FX.php. However, being my first PHP project, it's not really as well designed as it
could be -- it could be both more streamlined and easier to use.

Rather than trying to cram all of my learning into that project, my thought was to create something new. Enter db|.php
(read as "D B pipe dot P H P"). The name feels so perfect, I was surprised that no one seemed to have used it. On the
other hand, it is somewhat ostentatious, so maybe others just have better sense.

After mucking around a bit, the syntax I've come up with looks something like this:
```php
<?php
$query = new DB\FMX\Query("db_config.ini");
$query->where("size")->equalTo("large");
$query->where("color")->notEqualTo("red");
$results = $query->execute();
```
Beautiful, no?

Some features of db|.php worth noting:

- `.ini` files can be used for settings (PHP has some very powerful associated functionality.)
- Query syntax makes sense without prior knowledge of the class.
- In PHP arrays have some very powerful, object-like behavior; so that's leveraged where it makes sense.

Now to make it work... Heh!

--Chris Hansen

Initial thoughts on data sources to support:
- `PGS` - PostgreSQL (this should also give us CockroachDB for free)
- `FMD` - FileMaker Data API
- `FMX` - FileMaker XML
- `MYS` - MySQL
- `ELS` - Elasticsearch
- `RED` - Redis
- `ODB` - ODBC
- `DDR` - FileMaker Data Design Report (XML syntax)
- `PGN` - PostgreSQL native libpq
