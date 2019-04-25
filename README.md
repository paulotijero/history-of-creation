```sql
CREATE TABLE adan(
  id SERIAL PRIMARY KEY,
  costillas integer,
  sky boolean CONSTRAIN paraiso DEFAULT true
);
```

```sql
INSERT INTO adan(costillas) VALUES (2);
```

```sql
SELECT costillas FROM adan LIMIT 1;
```

```sql
CREATE TABLE eva(
  id SERIAL PRIMARY KEY,
  costillas integer,
  sky boolean CONSTRAIN paraiso DEFAULT true,
  idAdan integer FOREIGN KEY REFERENCES adan(id)
);
```

```sql
UPDATE adan set constillas = (SELECT count(constillas)-1 FROM adan);
```

```sql
CREATE TABLE serpiente(
  id SERIAL PRIMARY KEY,
  especie string CONSTRAINT diablo
);
```

```sql
CREATE TABLE arbol(
  id SERIAL PRIMARY KEY,
  ubicacion string,
  fruto string CONSTRAINT fruto_prohibido
);
```

```sql
ALTER TABLE arbol RENAME CONSTRAINT fruto_prohibido TO fruto_del_saber;
```

```sql
CREATE TABLE arbol(
  id SERIAL PRIMARY KEY,
  ubicacion string,
  fruto string CONSTRAINT fruto_del_saber
);
```

```sql
CREATE TABLE fruto_que_comio(
  id SERIAL PRIMARY KEY,
  idArbol integer FOREIGN KEY REFERENCES arbol(id),
  idEva integer FOREIGN KEY REFERENCES eva(id),
  idSerpiente integer FOREIGN KEY REFERENCES serpiente(id)
);
```

```sql
UPDATE eva set sky = false;
```

```sql
UPDATE adan set sky = false;
```

```sql
ALTER TABLE eva RENAME CONSTRAINT paraiso to la_tierra DEFAULT false
```

```sql
ALTER TABLE adan RENAME CONSTRAINT paraiso to la_tierra DEFAULT false
```
