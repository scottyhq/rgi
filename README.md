# rgi
randolf glacier inventory

https://nsidc.org/data/nsidc-0770

```
wget https://daacdata.apps.nsidc.org/pub/DATASETS/nsidc0770_rgi_v6/nsidc0770_15.rgi60.SouthAsiaEast.zip
unzip nsidc0770_15.rgi60.SouthAsiaEast.zip
ogr2ogr -of GPKG 15_rgi60_SouthAsiaEast.gpkg 15_rgi60_SouthAsiaEast.shp
ogr2ogr -of GeoJSON 15_rgi60_SouthAsiaEast.geojson 15_rgi60_SouthAsiaEast.shp
```

Nice thing about GeoJSON is that github renders a map for you (but complains for files above 50MB, which this is)
https://github.com/scottyhq/rgi/blob/main/15_rgi60_SouthAsiaEast.geojson

Geopackage is much more compact and is a great single-file alternative to .shps (https://www.geopackage.org). Also either geojson or geopackage can be loaded directly from URLs with geopandas so the github raw link:


```python
gf = gpd.read_file('https://github.com/scottyhq/rgi/raw/main/15_rgi60_SouthAsiaEast.gpkg')
gf.head()
#            RGIId         GLIMSId   BgnDate   EndDate      CenLon  ...  TermType Surging Linkages  Name                                           geometry
#0  RGI60-15.00001  G102044E29941N  19990920  -9999999  102.044042  ...         0       9        9  None  POLYGON ((102.03759 29.93828, 102.03759 29.938...
```
