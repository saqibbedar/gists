# 1. Verify status and activate psql service

```bash
sudo systemctl status postgresql        # if service is active then follow below heading steps otherwise use following command to activate it

# activate service
sudo systemctl start postgresql
```

# 2. Create a PostgreSQL Database and User (option 1)

```bash
# 1. login to default postgres administrative account
sudo -i -u postgres psql

# 2. Inside psql prompt(postgres=#), execute following commands

# create new database for fastapi project
create database fastapi_project;

# create a new user with secure password for this database project
create user fastapi_db_admin with password 'secure_password';

# grant connection and ownership privileges on the database to the user
grant all privileges on database fastapi_project to fastapi_db_admin;

# Connect to the newly created database to configure schema permissions
\c fastapi_project

# Grant permission to create tables and objects inside the public schema
grant all on schema public to fastapi_db_admin;

# 3. Create .env file and setup db_url for sql alchemy
DATABASE_URL=postgresql+psycopg://fastapi_db_admin:secure_password@localhost:5432/fastapi_project
```

# 3. Create a PostgreSQL Database (option 2)

Instead of creating a new user we can simply use existing super user by altering or giving a new password to him and then utilize his credentials for our new database.

```bash
# 1. login to psql prompt
sudo -i -u postgres psql

# 2. create database
create database fastapi_project;

# give the default postgres user a password so your app can log in
# NOTE: PostgreSQL requires single quotes (') for string literals like passwords
alter user postgres with password 'secure_password';

# 3. sql alchemy url (async(v3): psycopg)
DATABASE_URL=postgresql+psycopg://postgres:secure_password@localhost:5432/fastapi_project


# breakdown: postgresql+psycopg://postgres:secure_password@localhost:5432/fastapi_project
# - postgresql+psycopg: the database dialect and modern async/sync driver (Psycopg v3)
# - postgres: master admin username
# - secure_password: master admin's password
# - localhost: your local machine
# - 5432: default postgres port
# - fastapi_project: the database you just created
```