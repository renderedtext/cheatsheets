# Postgres

### Dump and import

    pg_dump dbname | gzip > db.gz

Before import, database must be empty.

    gunzip -c db.gz | psql dbname

or
    
    psql dbname -f db.sql

### Get database size

First log in the console with `psql dbname`, then:

    SELECT pg_size_pretty(pg_database_size('dbname'));
