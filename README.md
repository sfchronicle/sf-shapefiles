# San Francisco shape files
This repo includes San Francisco shape files that The San Francisco Chronicle data team often uses. The following geographic areas are included:
* Census tracts (1960-2020): A census tract is a small Census-designated area with about 1,200 to 8,000 residents. Census tract boundaries change once every 10 years (with the Decennial Census). The `SF census tracts` folder includes shape files for each decade from 1960 to 2020. The Chronicle often analyzes population data by census tract to understand demographic changes that happen within the city, on a smaller scale. We recently analyzed [changes in S.F.'s Asian population](https://www.sfchronicle.com/projects/2022/san-francisco-asian-population/) in the last six decades by census tract.
* Neighborhoods: San Francisco has many neighborhood boundaries. We include shape files for four: [Department of Elections neighborhoods](https://sfelections.sfgov.org/sites/default/files/Documents/Maps/NeighborhoodPctMap2019.pdf), Planning Department's [analysis neighborhoods](https://data.sfgov.org/Geographic-Locations-and-Boundaries/Analysis-Neighborhoods/p5b7-5n3h), Planning Department's [notification neighborhoods](https://sfplanning.org/resource/neighborhood-group-organizations) and [SF311's neighborhoods](https://sf.connect.socrata.com/#!/dashboard?places=&restrictedPlaces=&categories=285:1-29&start_date=2021-11-24&end_date=2022-07-01&lat=37.7474&lng=-122.43920000000003&zoom=12&shapeIds=&shapeGroupId=6qbp-sg9q&mapType=Map&listViewTab=overview&overlayLayers=Neighborhoods&search_field=&search_value=&autoUpdate=false&heatFilters=&statusFilter=&choroplethField=count&searchType=&include_restricted_places=false). We typically use the election department's set of neighborhoods for elections-related analyses and the analysis neighborhoods for most other use cases. If you're curious why there are so many neighborhood boundaries, read our [story](https://www.sfchronicle.com/projects/2022/san-francisco-neighborhoods/) exploring how the city uses each boundary set.

All shape files are shoreline-clipped (i.e. they exclude bodies of water).

## How to use these shape files
A lot of city data is grouped by neighborhood or Census-designated areas, but in order to visualize the data on a map, you need to merge it with the corresponding shape file. With the help of a GIS application (we use [Mapshaper](https://mapshaper.org/)), you can merge your dataset with the shape file, matching the two on the tract ID or neighborhood name (make sure they use the same values in both datasets!)

## Folder + file structure
* `SF census tracts`
  * `sf-tracts-1960-clipped.geojson` - Census tracts from 1960. `GISJOIN2` has the full [GEOID](https://www.census.gov/programs-surveys/geography/guidance/geo-identifiers.html) for the tract.
  * `sf-tracts-1970-clipped.geojson` - Census tracts from 1970. `GISJOIN2` has the full [GEOID](https://www.census.gov/programs-surveys/geography/guidance/geo-identifiers.html) for the tract.
  * `sf-tracts-1980-clipped.geojson` - Census tracts from 1980. `GISJOIN2` has the full [GEOID](https://www.census.gov/programs-surveys/geography/guidance/geo-identifiers.html) for the tract.
  * `sf-tracts-1990-clipped.geojson` - Census tracts from 1990. `GISJOIN2` has the full [GEOID](https://www.census.gov/programs-surveys/geography/guidance/geo-identifiers.html) for the tract.
  * `sf-tracts-2000-clipped.geojson` - Census tracts from 2000. `TRACTCE00` is the census tract code.
  * `sf-tracts-2010-clipped.geojson` - Census tracts from 2010. `tractce10` is the census tract code.
  * `sf-tracts-2020-clipped.geojson` - Census tracts from 2020. `TRACTCE20` is the census tract code.
* `SF neighborhoods`
  * `sf-neighborhoods-311.json` - 311 neighborhoods
  * `sf-neighborhoods-analysis.json` - analysis neighborhoods
  * `sf-neighborhoods-elections.json` - Election Department's neighborhoods
  * `sf-neighborhoods-notifications.json` - notification neighborhoods

## Sources
These shape files are sourced from the U.S. Census Bureau, University of Minnesota’s Population Center (IPUMS NHGIS) and San Francisco agencies.
