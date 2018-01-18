## PostgreSql

Install and init service:

```sh
yaourt -S postgresql
sudo passwd postgres
su - postgres -c "initdb --locale en_GB.UTF-8 -D '/var/lib/postgres/data'"
sudo systemctl start postgresql.service
```

Setup new database:
```sh
su postgres
createdb xms-dev
createuser dev
psql
grant all on database "xms-dev" to dev
\q
```

### PG Admin 4

Install using Python's virtualenv:

```sh
sudo pip install setuptools virtualenv
virtualenv pgadmin4
cd pgadmin4
source bin/activate
pip install https://ftp.postgresql.org/pub/pgadmin/pgadmin4/v2.0/pip/pgadmin4-2.0-py2.py3-none-any.whl
```

Create local configuration file:
```sh
vim ./lib/python3.6/site-packages/pgadmin4/config_local.py
```

Contents:

```python
import os
DATA_DIR = os.path.realpath(os.path.expanduser(u'~/.pgadmin/'))
LOG_FILE = os.path.join(DATA_DIR, 'pgadmin4.log')
SQLITE_PATH = os.path.join(DATA_DIR, 'pgadmin4.db')
SESSION_DB_PATH = os.path.join(DATA_DIR, 'sessions')
STORAGE_DIR = os.path.join(DATA_DIR, 'storage')
SERVER_MODE = False
```

Reference: https://askubuntu.com/questions/831262/how-to-install-pgadmin-4-in-desktop-mode-on-ubuntu
