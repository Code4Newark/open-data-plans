# open-data-plans

![City of Newark logo](http://www.ci.newark.nj.us/wp-content/uploads/2014/08/logo_CityNewark_600px.png)

The City of Newark open data portal has an some interesting datasets we might work with and create some kind of spatial/map visualization. The datasets range across infrastructure, government, demographics, business, education and public safety but here are some datasets I found more interesting.

- [Abandoned Properties](http://data.ci.newark.nj.us/dataset/abandoned-properties)
  - Contains latitute and longitude data.
  - Former owner's (individual/corporation) name.
- [Wards](http://data.ci.newark.nj.us/dataset/wards)
  - This is a shapefile that we can use to generate the actual map of Newark on a webpage.
- [Health Inspections](http://data.ci.newark.nj.us/dataset/health-inspections)
  - Contains latitute and longitude data.
  - Grade and date inspected.

There is also data on [NHA Project Housing](http://data.ci.newark.nj.us/dataset/nha-projects), the [Valentine's Day Property Sale](http://data.ci.newark.nj.us/dataset/valentine-s-day-property-sale), [Newark Census](http://data.ci.newark.nj.us/dataset/newark-census-block-group-polygon) and distribution of [Taxes Paid](http://data.ci.newark.nj.us/dataset/taxes-paid-2014), all interesting stuff with potentially even more interesting insights in an overlapping visualization.

This open data project could definetly bring some synergy to the voting app project that we are thinking of starting. Essentially, trying to inform voters with these visualizations before they go to the polls.

## Implementation

We can use [D3.js](https://github.com/mbostock/d3) and [Node.js](https://github.com/nodejs/node) to handle most if not all parts of this project, from rendering the map of Newark in-browser to parsing the raw datasets (usually in csv form).

A homogenous JavaScript stack will also be an opportunity to involve the beginning Saturday JavaScript learners.

Development roadmap
---
1. Render geoJSON map of Newark, NJ in the browser
2. ~~Parse datasets (e.g. abandon homes, health inspections, etc) for coordinate data~~
  - We actually don't need to parse if we use Newark's [CKAN-based API](http://data.ci.newark.nj.us/sl/api/1/util/snippet/api_info.html?resource_id=97626fdf-9d73-48da-8090-3c734a6d79d8&datastore_root_url=http%3A%2F%2Fdata.ci.newark.nj.us%2Fapi%2Faction). We can return a JSON version of the csv at the moment of the request (think live updating!).
3. Plot coordinate data on map. Give users option of specificing which data they want to see.
4. Do all this in an object-oriented fashion so that when Newark open data people release new datasets, adding them to our visualization is trivial.
