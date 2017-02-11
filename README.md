# threemetres
Television show tracking and recommendation engine

## Requirements
[Python 2.7](https://www.python.org/)
[Django 1.10.5](https://www.djangoproject.com/)
[MySql 5.7](https://www.mysql.com/)

## Data
Television show data comes from [tvdb](https://www.google.com).

Data can be retrieved and updated via their
[api](https://api.thetvdb.com/swagger).

To avoid placing a heavy load on the TVDB server it's also possible to download
an initial dump of the database from this [directory](http://hero6.com/tvdb/).

## Installation of bulk TVDB Data
Start the MySql command line console and create the database.

```sql
CREATE DATABASE tvdb CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci;
```

Create a user who has access to the new tvdb database.

```sql
GRANT ALL ON `tvdb`.* TO 'tvdbuser'@'localhost' IDENTIFIED BY 'secretpassword';
```

Load the bulk TVDB data into the newly created database.

```bash
mysql --password --user tvdbuser tvdb < tvdb.sql
```
