# Getting the data
These datasets come from a number of different places. These are some of our notes on reproducing our figures with original data from online sources.

## Automobile dataset
https://archive.ics.uci.edu/ml/datasets/Automobile

## Les Miserables
Knuth's "Les Miserables" dataset came from http://www-cs-staff.stanford.edu/~knuth/sgb.html and has been translated into a useful JSON format at 
https://bost.ocks.org/mike/miserables/miserables.json 

For the figures in the book, we truncated to the first 30 or so names

## Consumer complaints

The original source of the data is from https://catalog.data.gov/dataset/consumer-complaint-database 

```bash
csvsql --db sqlite:///complaints.db Consumer_Complaints.csv -y 1000 --insert
```

```sql
select "Date received", "Product", "Sub-product", "Company", "State", "ZIP code", "Consumer consent provided?", "Submitted via", "Company response to consumer", "Timely response?", "Consumer disputed?"
from Consumer_Complaints
where ("Date received" like '2012%' or "Date received" like '2013%' or "Date received" like '2014%' or "Date received" like '2015%' or "Date received" like '2016%') and ("Product" = 'Mortgage' or "Product" = 'Credit reporting' or "Product" = 'Debt collection' or "Product" = 'Credit card' or "Product" like 'Bank account%')
order by random()
limit 20000;
```

```bash
sqlite3 complaints.db -header -csv < query.sql > complaints.cs
```

## CO2 and Temperature data

https://www.ncdc.noaa.gov/cag/time-series/global/globe/land_ocean/ytd/12/1880-2017
http://data.okfn.org/data/core/co2-ppm

## Income data
For images in the book, we trimmed some income levels and some unrendered regions (e.g. Puerto Rico)