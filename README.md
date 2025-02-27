# Project 1.1 (Joshua Liu and Ben Deitch)

## Overview

This project was created from [YourOwnIMDb](https://github.com/SSD-Brandeis/YourOwnIMDb) and is built up to the point specified in Programming Assignment 1.1.

## Running the Project

To run the project, download mariaDB according to the directions in [YourOwnIMDb](https://github.com/SSD-Brandeis/YourOwnIMDb) and the Programming Assignment 1.1 document.

Run:

```
mysql -u root -p
```
and then inside mariadb run:

```
CREATE DATABASE moviedb;

DROP USER 'imdb'@'localhost';

CREATE USER 'imdb'@'localhost' IDENTIFIED BY 'cosi-127b';

GRANT ALL PRIVILEGES ON moviedb.* TO 'imdb'@'localhost';

FLUSH PRIVILEGES;
```

Go to the root directory of this project and run the following command:

```
mysql -u root -p < schema_initialization.sql
```

This will create the database moviedb and populate it with the necessary tables.

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
