# wmts-service
[![Build Status](https://travis-ci.org/edigonzales/wmts-service.svg?branch=master)](https://travis-ci.org/edigonzales/wmts-service)

## Building the image

```
docker build -t sogis/wmts-service:latest .
```

## Run
```
docker run -p 8281:8080 -v /tmp:/tiles --rm --name mapcache sogis/wmts-wms
```

Log into container:
```
bash -c "clear && docker exec -it mapcache /bin/bash"
```

Seeding:
```
docker exec -it mapcache mapcache_seed -c /mapcache/mapcache.xml -t ch.so.agi.grundbuchplan_sw -f -z 11,11 -n 4 -d /mapcache/wmts-seeding-perimeter.gpkg -l kanton1000m
```

WMTSCapabilities.xml:
```
http://localhost:8281/mapcache/wmts/1.0.0/WMTSCapabilities.xml
```
