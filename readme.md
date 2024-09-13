This repo uses PostgreSQL as a backing store for the rest catalog.

Use the following commands to bring up and down environments.

    docker compose up
    
    docker compose down

Connect to the PostgreSQL database container using the following command:

    docker exec -it pg-catalog psql -U iceberg


    Use the following commands on psql
    \l                  to list databases
    \c db_name          to connect to the named database
    \d                  to list the relations(tables)

Connect to spark-sql using the following command
    
    docker exec -it spark-iceberg spark-sql

If is also possible to connect to minio here:

    localhost:9001

By creating some tables and views on top of these tables, you should be able to see Apache Iceberg in action.

This uses ideas from : https://github.com/tabular-io/docker-spark-iceberg.git

It is possible to skip the rest catalog and use postgresql as catalog directly

    docker compose -f docker-compose-postgres.sql up

It is necessary to download the jdbc driver for postgres before the above command

    curl https://jdbc.postgresql.org/download/postgresql-42.6.0.jar -o postgresql-42.6.0.jar

