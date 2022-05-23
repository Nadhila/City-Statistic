# City statistics

The goal of the project is to download and analyse OSM data for a given
administrative region (e.g. a city, a district, etc.).

As the input, you will get the OSM ID of the relation representing the
region (e.g. [2768922](https://www.openstreetmap.org/relation/2768922)
for Kraków). Then, your script should:

1.  Estimate the bounding box which contains the region's boundary using
    the [Overpass Turbo API](https://overpass-turbo.eu/), adding a
    margin of a certain width.

2.  Download the appropriate smallest OSM dump from
    [GeoFabrik](http://download.geofabrik.de/).

3.  Crop the dump accordingly and import into a PostGIS database (both
    using [Osmosis](https://wiki.openstreetmap.org/wiki/Osmosis)).

4.  Calculate the length of roads which fit within the boundary, grouped
    by [OSM highway
    type](https://wiki.openstreetmap.org/wiki/Key:highway).

5.  Present the statistics as a data structure or Pandas dataframe.
