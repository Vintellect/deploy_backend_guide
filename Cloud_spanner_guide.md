# Cloud Spanner Guide

Before you begin, make sure to read the documentation for Cloud Spanner [here](https://cloud.google.com/spanner?hl=fr).

## Creating a Spanner Instance:

The first step is to create an instance. Ensure you select the appropriate region for your requirements.

## Creating User Databases:

Next, create the user databases. You can name these databases as you like, but remember that they will be usefull for setting up microservices later on. Select 'Google Standard SQL' for the database. Then, execute the following SQL commands:

```sql
CREATE TABLE feedback (
  user_id STRING(32) NOT NULL,
  wine_id INT64 NOT NULL,
  note INT64 NOT NULL,
  comment STRING(2048) NOT NULL,
) PRIMARY KEY(user_id, wine_id);

CREATE TABLE sequences (
  name STRING(64) NOT NULL,
  next_value INT64 NOT NULL,
) PRIMARY KEY(name);

CREATE TABLE user (
  id INT64 NOT NULL,
  is_admin BOOL NOT NULL,
  mail STRING(255) NOT NULL,
) PRIMARY KEY(id);
```

## Creating Wine Databases:

Similarly, create the wine databases. These will also be use for microservices setup later. Again, choose 'Google Standard SQL' and use the following SQL scripts:

```sql
CREATE TABLE advice (
  id INT64 NOT NULL,
  advice STRING(255),
) PRIMARY KEY(id);

CREATE TABLE appellation (
  id INT64 NOT NULL,
  appellation STRING(255),
) PRIMARY KEY(id);

-- Additional tables omitted for brevity --

CREATE TABLE wine (
  id INT64 NOT NULL,
  id_advice INT64 NOT NULL,
  id_productor INT64 NOT NULL,
  id_cuve INT64,
  id_appellation INT64,
  id_region INT64 NOT NULL,
  years INT64 NOT NULL,
  code_barre STRING(255) NOT NULL,
  percent FLOAT64 NOT NULL,
  id_type INT64 NOT NULL,
  id_warning INT64 NOT NULL,
  img_url STRING(255),
) PRIMARY KEY(id);
```