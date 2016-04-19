## 18 April 2016

* Address parsing now works without spaces after commas. This was our bad. Feel free to leave those spaces out as long as you provide commas to delimit admin parts.
* Further streamlining of labels. You can expect the labels to a have more consistent and minimal feel. If the results are coming from New York, expect boroughs such as Manhattan, Brooklyn, Queens, etc. to be part of the label. You're welcome New Yorkers! :heart:
* Fixed a bug where specifying `layers=macrocounty` would fail due to a typo in the API code. You can see how easy it is to mistype `macrocounty` and not notice that `macrocountry` is incorrect. #onlyhuman


## 08 April 2016

This release marks the official integration of the Mapzen `Who's on First` data set into Mapzen Search. This data is replacing `Quattroshapes` across the entire service. Any forward usage or references to `Quattroshapes` will be replaced with `WhosOnFirst`. This substitution allows us to fix long-standing encoding issues in administrative hierarchy place-names. We've also added a bounding box for individual features in the results, not only the all-encompassing bounding box at the top level of the geojson results. Also, the all-encompassing bounding box will extend to include the bounding boxes of all the features in the results, not only their centroids. 
Another major improvement that many have been waiting for is the addition of more filters for the `/autocomplete` endpoint. Users can now ask `/autocomplete` to filter by `layers` and `sources`, as documented [here](https://mapzen.com/documentation/search/autocomplete/#available-autocomplete-parameters).
See the detailed list of changes below for more specifics.

* Switched from `Quattroshapes` to `WhosOnFirst` as the canonical source for administrative hierarchies and corresponding geometries.
* No longer importing `Quattroshapes` data since `WhosOnFirst` contains all those records and more. Going forward, any use of `quattroshapes` or `qs` in queries will resolve to `whosonfirst` or `wof` automatically.
* New `bbox` property has been added to individual results, for which geometry was available in the original source. This does not affect POI and address data.
* Drastic improvements have been made to the label generation logic.
* `id` and `gid` format has changed to make the ids more unique.
* New id format resolves previously outstanding bugs related to `geonames` ids being invalid for lookup via the `/place` endpoint.
* Additional place-types have been introduced, such as `macroregion`, `macrocounty`, and `borough`.
* `gid` values have been added for each parent in the admin hierarchies of results.
* `/autocomplete` now allows filtering by `sources` and `layers`.
* Fixed a bug that allowed `/autocomplete` to accept the `size` parameter. The default and only size of `/autocomplete` results is now `10`, as originally intended.

