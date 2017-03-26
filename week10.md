# What is RealDictCursor and how does setting the isolation-level to autocommit make the DBMS more developer-friendly?


## RealDictCursor

- imported from psycopg2.extras
- a cursor that uses a real dict as the base type for rows
  -allows access to column names as dict keys
- extremely specialized and does not allow the normal access (using integer indices) to fetched data
  -If you need to access database rows both as a dictionary and a list, then use the generic DictCursor instead
- can be specified in the connection
``` python
psycopg2.connect(cursor_factory=RealDictCursor)
```
- http://initd.org/psycopg/docs/extras.html
- https://www.peterbe.com/plog/from-postgres-to-json-strings


## Isolation-level Autocommit

- also from psycopg2.extras
- you dont have to commit at the end of each sql statement

``` python
connection.set_isolation_level(psycopg2.extensions.ISOLATION_LEVEL_AUTOCOMMIT)
```
- http://initd.org/psycopg/docs/extensions.html?highlight=autocommit#psycopg2.extensions.ISOLATION_LEVEL_AUTOCOMMIT
