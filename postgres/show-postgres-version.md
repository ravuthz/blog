---
title: "Get PostgreSQL version"
publishDate: "2023-06-13T12:31:00+07:00"
draft: false
featured: true
categories:
  - "Site"
series: "Site Series"
tags:
  - "Blog"
  - "Site"
  - "Query"
  - "PostgreSQL"
description: "Show the Postgres-SQL version"
---

# Show PostgreSQL version

## Using command line

To display the version of PostgreSQL using **postgres** or **psql** command-line utilities, you can follow these steps:

1. Find the **postgres** or **psql** with **locate**, **where** or **which** command-line

```bash
locate bin/postgres
# /usr/lib/postgresql/9.3/bin/postgres

where psql
# /opt/homebrew/opt/postgresql@11/bin/psql

which psql
# /opt/homebrew/opt/postgresql@11/bin/psql

```

2. Execute the **postgres** or **psql** command-line with **-V** or **--version** options

```bash
postgres -V
# postgres (PostgreSQL) 11.18

psql -version
# psql (PostgreSQL) 11.18
```

## Using query

To display the version of PostgreSQL installed on your system, you can use the following SQL query:

```sql
-- SELECT version FROM pg_catalog.version();
SELECT version();
-- +-------------------------------------------------------------------------------------------+
-- |version                                                                                    |
-- +-------------------------------------------------------------------------------------------+
-- |PostgreSQL 12.15 on x86_64-pc-linux-gnu, compiled by gcc, a 2c4e4d7dba p 6a7005436d, 64-bit|
-- +-------------------------------------------------------------------------------------------+

```

This query will return a single row containing the version information.

| version                                                                                     |
| :------------------------------------------------------------------------------------------ |
| PostgreSQL 12.15 on x86_64-pc-linux-gnu, compiled by gcc, a 2c4e4d7dba p 6a7005436d, 64-bit |

```sql
SHOW SERVER_VERSION;
+--------------+
|server_version|
+--------------+
|12.15         |
+--------------+

```

| server_version |
| :------------- |
| 12.15          |

To execute this query, you can use a **PostgreSQL client** such as **psql** or any other **SQL tools** that can connect to your PostgreSQL server.
