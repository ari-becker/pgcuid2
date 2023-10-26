# pgcuid2

Use [`cuid2`](https://github.com/paralleldrive/cuid2) from directly within PostgreSQL.

This allows you to write DDL like:

```postgresql
CREATE TABLE foo (
    id TEXT DEFAULT cuid2_create_id() PRIMARY KEY,
    name TEXT
);
```

then inserting data:

```postgresql
INSERT INTO foo (name) values ('Foo');
```

and running `SELECT * from foo;` will return something like

```text
            id            | name 
--------------------------+------
 v11s7ykor7sv3uo1lcdkgs1p | Foo
(1 row)
```

## Appreciation
This would not be possible without:

* Eric Elliot's work on [`cuid2`](https://github.com/paralleldrive/cuid2).
* [`pgrx`](https://github.com/pgcentralfoundation/pgrx), which made it so easy.

Thank you!