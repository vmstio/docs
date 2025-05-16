# PostgreSQL

[PostgreSQL](https://www.postgresql.org), often referred to as Postgres, is an open-source relational database management system.
In Mastodon, it is used as the primary database to store and manage various types of data required for the functioning of the platform.
PostgreSQL plays a crucial role in Mastodon's architecture, providing persistence, data integrity, and efficient querying capabilities.

We use the DigitalOcean managed PostgresSQL database service, which delivers a highly available database backend.
Updates and maintenance are performed by DigitalOcean, independent of our administration efforts.

We have highly available database cluster ([Majel](https://memory-alpha.fandom.com/wiki/Majel_Barrett_Roddenberry)) with two nodes running 4 vCPU and 16GB of memory, with dedicated vCPU cores allocated.
We use PostgreSQL 16.x.
The primary database node handles all of the write activity, which is then actively replicated to the standby node which is then used as a read-replica for Mastodon.

DigitalOcean Droplet "T-Shirt" sizes for databases are determined by vCPU, memory, disk size, and connections to the database.
The connection count limits are based on sizing best practices for PostgreSQL, with a few held in reserve for their use to manage the service.

DigitalOcean has an integrated "Connection Pool" feature of their platform, which, in practice, puts the [PgBouncer](https://www.pgbouncer.org) utility in front of the database.
This acts as a reverse proxy / load balancer for the database, to ensure that connections to the database by Mastodon cannot stay open and consume resources longer than needed.

There are a [few options for pooling modes](https://docs.digitalocean.com/products/databases/postgresql/how-to/manage-connection-pools/#pooling-modes) with DigitalOcean, but the default _Transaction Mode_ is the required option for Mastodon.

Example of `.env.production` configuration settings relevant to PostgreSQL:

```text
# PostgreSQL
DB_HOST=path-to-postgresql-database.ondigitalocean.com
DB_PORT=25061
DB_NAME=the_mastodon_connection_pool
DB_USER=the_mastodon_user
DB_PASS=Ourpassw0rd!sNoneofyourbu$iness
PREPARED_STATEMENTS=false
```

The `PREPARED_STATEMENTS=false` is [required of Mastodon to use PgBouncer](https://docs.joinmastodon.org/admin/scaling/#pgbouncer).
When performing upgrades of Mastodon that require changes to the database schema, you **must** temporarily modify the configuration on the system running the schema change to bypass PgBouncer and go directly to the database.
You will need to remove the line with the prepared statement configuration or set it to true, then change the DB port and DB name values.
