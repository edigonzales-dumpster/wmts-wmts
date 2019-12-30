[![Build Status](https://github.com/edigonzales/wmts-wmts/workflows/CI/CD/badge.svg)](https://github.com/edigonzales/wmts-wmts/workflows/CI/CD/badge.svg)

# wmts-wmts

## Building the image

```
docker build -t sogis/wmts-wmts:latest .
```

## Run
```
docker run -p 8282:8080 -v /tmp:/tiles --rm --name mapcache sogis/wmts-wmts
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
http://localhost:8282/mapcache/wmts/1.0.0/WMTSCapabilities.xml
```
