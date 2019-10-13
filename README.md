# SQL

SQL bir sorgulama dilidir. SQL ,   veritabanında bulunan tabloları seçmek ve onlar üzerinde işlemler yapamaya yarar. 

Sql ve pandas birlikte kullanılırsa işlemler çok hızlı şekilde gerçekleşir.

Sql ile tabloları çekilir.Pandas ile bu tabloları işlenir.

### Kütüphane çağrıldı

```python

import sqlite3
import pandas as pd 

```

### Bağlantı kuruldu

```python

db = sqlite3.connect("vt.sqlite")

```

### sqlite_master ile veritabanı hakkında bilgi alınır. Ve aşağıda veritabanında bulunan tabloların isimleri alındı.

```python

table_names = "SELECT name FROM sqlite_master WHERE type='table';"

df_table_names=pd.read_sql_query(table_names, db)

print(df_table_names)

```

### df_table_names 'ın 0. indeksdeki tablo ismi alınıp, o tablo okundu

```python

content = "SELECT * FROM '%s' "%(table_names[0])

df_content=pd.read_sql_query(content, db)

```

### Veritabanına yeni tablo eklendi

```python

new_df = pd.DataFrame(...)

new_df.to_sql("new table", db, if_exists="replace")#new table

```


### Ve veritabanı kapatıldı
```python

db.close()

```

### Pandas ile de veri işlenir.
```python
pd....
```

