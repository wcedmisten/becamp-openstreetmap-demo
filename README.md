# Setup NextJS application

```
npx create-next-app@latest
```

# Download osm.pbf file

http://download.geofabrik.de/

```
wget http://download.geofabrik.de/north-america/us/virginia-latest.osm.pbf
```

# Install planetiler

```
wget https://github.com/onthegomap/planetiler/releases/latest/download/planetiler.jar
```

Create pmtiles file

```
java -Xmx4g -jar planetiler.jar --osm-path/virginia.osm.pbf --output virginia.pmtiles

java -Xmx4g -jar planetiler.jar --download --area us/virginia --output virginia.pmtiles
```

Run fileserver

```
npx http-server --cors=*
```


Misc file sources:

* fonts - https://github.com/openmaptiles/fonts
* sprite - https://openmaptiles.github.io/osm-bright-gl-style

Inspect PMTiles: https://pmtiles.io


Example:

https://github.com/protomaps/PMTiles/blob/main/js/examples/maplibre.html
