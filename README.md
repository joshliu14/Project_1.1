# Project 1.1 (Joshua Liu and Ben Deitch)

## Overview

This project was created from [YourOwnIMDb](https://github.com/SSD-Brandeis/YourOwnIMDb) and is built up to the point specified in Programming Assignment 1.1.

## Running the Project

To run the project, [clone the project](https://docs.github.com/en/repositories/creating-and-managing-repositories/cloning-a-repository) and download MariaDB:

For Mac:

```
brew install mariadb
```

For Ubuntu/Debian:

```
sudo apt install mariadb-server
```

For Windows:
Download and install from [MariaDB Official Website](https://mariadb.org/)

Then start MariaDB server:

```
# MacOS
brew services start mariadb

# Linux
sudo systemctl start mariadb
```

Then run:

```
mysql -u root -p
```
It will ask for a password. If installing MariaDB for the first time, just hit enter. Otherwise give the password you set. If that still does not work, try [resetting your root password](https://www.digitalocean.com/community/tutorials/how-to-reset-your-mysql-or-mariadb-root-password).

Then inside MariaDB run:

```
CREATE DATABASE moviedb;

CREATE USER 'imdb'@'localhost' IDENTIFIED BY 'cosi-127b';

GRANT ALL PRIVILEGES ON moviedb.* TO 'imdb'@'localhost';

FLUSH PRIVILEGES;
```

Exit and go to the root directory of this project and run the following command:

```
mysql -u root -p < schema_initialization.sql
```

This will populate moviedb with the necessary tables.

Then run:

```
mysql -u root -p < data/data.sql
```

This will populate the database with the given data.

Then install requirements:

```
pip install -r requirements.txt
```

Then run the application:

```
python run.py
```

The application will be running on http://127.0.0.1:5000/
