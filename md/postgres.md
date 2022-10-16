[return to maine page](../readme.md)

# install postgres

```
# Create the file repository configuration:
    sudo sh -c 'echo "deb http://apt.postgresql.org/pub/repos/apt $(lsb_release -cs)-pgdg main" > /etc/apt/sources.list.d/pgdg.list'

# Import the repository signing key:
    wget --quiet -O - https://www.postgresql.org/media/keys/ACCC4CF8.asc | sudo apt-key add -

# Update the package lists:
    sudo apt-get update

# Install the latest version of PostgreSQL.
# If you want a specific version, use 'postgresql-12' or similar instead of 'postgresql':
    sudo apt-get -y install postgresql
```

# switch to postgres

```
    sudo -i -u postgres (then use)
    psql -U postgres -W
```

# list of all databases

```
    \l
```

# select the database

```
    \c database name
```

# list all the tables

```
    \dt
```

# change the user password

```
    ALTER USER postgres PASSWORD 'Password'
```

# create the database

```
    create database dbname;
```

# add data to database

```
    pg_restore --dbname=database_name --verbose database_file
```

# describe table

```
    \d tablesName
```

# rename table

```
    ALTER TABLE table_name RENAME TO new_name
```

# add column in table

```
    ALTER TABLE table_name
    ADD COLUMN column_name data_type
```

# select statement

it will return the data from the database

```
   SELECT column_names FROM table_name;
   eg
   SELECT first_name FROM customer;
```

# concat two columns with alias

```
   SELECT first_name || ' ' || last_name AS full_name FROM customer;
```

# sort data
