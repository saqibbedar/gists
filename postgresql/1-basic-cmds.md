## Basic commands

- **Check version**: `psql --version`

- **Check status**: `sudo systemctl status postgresql`

- **Stop service**: `sudo systemctl stop postgresql`

- **Restart service**: `sudo systemctl restart postgresql`

- **Start service**: `sudo systemctl start postgresql`

- **Enable auto-start on boot**: `sudo systemctl enable postgresql`


## Shell Commands

```bash
# login as a postgres superuser and init postgres cli
sudo -i -u postgres psql            # -i: interactive shell, -u postgres: specific user instead of root user
# or use sudo -u postgres psql
# sudo -u postgres psql -d postgres (select database directly -> -d postgres)

# create password for default user
ALTER USER postgres WITH PASSWORD 'my_secure_password';

# list databases (show databases;)
\l                                  # or (\list)

# switch to specific database
\c db_name

# get back to interactive terminal
exit                                # or logout, or ctrl + D

# list tables inside your database
\dt

# quit shell
\q
```