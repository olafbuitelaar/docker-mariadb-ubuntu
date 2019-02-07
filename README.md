MariaDB with various extras
==================

Based on the [official MariaDB image](https://registry.hub.docker.com/_/mariadb/)

See the official image for usage documentation.

#### Tags

These tags are available `10.1`, `10.2`, `10.3`, `10.4`

#### Differences from the official image

- Includes tools not included in the official image: lz4, 7z, bzip2 and pigz, mariabackup
- Includes the [MyRocks](http://myrocks.io/) [RocksDB](https://en.wikipedia.org/wiki/RocksDB) plugin for MariaDB (10.2, 10.3 and 10.4 only)
- Includes the cracklib plugin
- Restore has been extended to support lz4 and 7z compressed sql files
- gzip compressed sql files are uncompressed using pigz
- Does not include 5.x and 10.0 images as those do not support LZ4 page compression

#### Restoring backups

- As documented in the official image documentation: Map a directory containing files with one of these exentions `*.sh`, `*.sql`, `*.sql.gz`, `*.sql.7z`, `*.sql.lz4` to `/docker-entrypoint-initdb.d/`

MariaBackup is included but using it for restore is a manual process for now.

