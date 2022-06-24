# rgi
randolf glacier inventory

https://nsidc.org/data/nsidc-0770

```
wget https://daacdata.apps.nsidc.org/pub/DATASETS/nsidc0770_rgi_v6/nsidc0770_15.rgi60.SouthAsiaEast.zip
unzip nsidc0770_15.rgi60.SouthAsiaEast.zip
ogr2ogr -of GPKG 15_rgi60_SouthAsiaEast.gpkg 15_rgi60_SouthAsiaEast.shp
ogr2ogr -of GeoJSON 15_rgi60_SouthAsiaEast.geojson 15_rgi60_SouthAsiaEast.shp
```
