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

# SQLite

## Sqlite'a giriş
1.Sqlite herhangi bir yazılım veya sunucu kurulumu gerektirmez.

2.Sqlite, öteki pek çok veritabanı alternatifine göre basittir.

3.Sqlite’ın sade ve basit olması sizi yanıltmasın. Bu özelliklerine bakarak, Sqlite’ın yeteneksiz bir veritabanı sistemi olduğunu düşünmeyin. Bugün Sqlite’ı aktif olarak kullanan pek çok büyük ve tanınmış şirket bulunur. Mesela, Adobe, Apple, Mozilla/Firefox, Google, Symbian ve Sun bu şirketlerden bazılarıdır.

## Sqlite’ın yapısı

Bütün ilişkisel veritabanlarında olduğu gibi, Sqlite da bu verileri tablo benzeri bir yapı içinde tutar. Ve bu tablolar birbirlerine idler kolonu ile bağlanır, ilişkisel olduğundan dolayı bu idlere topluca ulaşıp işi kolaylaştırır.

**Ve Sqlitebrowser aracı ile de sqlite görüntülenmesi ve işlenmesi yapılabilir. **
