A Location in the OpenAQ Platform represents a spatial location of an air quality monitoring station. Locations are uniquely identified by the `location_id` field. A single location may measure and record multiple [parameters](/docs/parameters).


### Mobile


OpenAQ also supports mobile monitoring stations, which are stored slightly differently compared to stationary monitors. Coordinates of mobile monitors are stored at the measurements level so that each measurement will have a measurement value, a time when the value was captured and a latitude and longitude associated with it. For mobile locations a bounding box of coordinates in the form \[xmin, ymin, xmax, ymax], the `bounds` field provides the extent of all measurements of that location.


### Endpoints


* [/v2/locations](/reference/locations_get_v2_locations_get)
* [/v2/locations/{location\_id}](/reference/locations_get_v2_locations__location_id__get)
Updated about 1 month ago 



---

