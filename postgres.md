# Postgres

### Dump and import

    pg_dump dbname | gzip > db.gz

Before import, database must be empty.

    gunzip -c db.gz | psql dbname

or
    
    psql dbname -f db.sql