
[sPostgreSQL](sPostgreSQL) Tutorial in PDq
udo -i -u postgres - change user to postgres then psql
sudo -u postgres psql - change user and log in

# connecting database from os prompt
psql [dbname] [username]
psql -h [ localhost | host ] -p [ 5432 | post] -U [ postgress | dbusername ] [ testdb | dbname]

## connecting database from postgres prompt
\c database_name - connect to database

\l - show all databases OR
    select * from pg_database; - show all databses

\dt OR \d - show all tables
\dt * . * - show all tables in all schemas
\dt myschema.* - show all tables in schema myschema

\d [tablename] - show table description

\dv - show all views

\t - toogle only tuples (add/remove headers)


\conninfo - information about the conection - user, database, port



\du - show all users

## Watch for changes
With output clear in backticks
```
\C `clear` SELECT * FROM pg_tables \watch 10
```

## Reset id 
select setval('api_payments_id_seq', COALESCE((select max(id)+1 from api_payments), 1), false)
