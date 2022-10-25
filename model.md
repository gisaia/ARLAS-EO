# ARLAS EO Data Model

## Field table

| Group  | Field name | Field description | Field type| Example|
| --------- | ------------- | -------------------- | ------- | ------ |
| __arlas__ & __stac__     |  __id__*           | Unique identifier    |  String | S2A_MSIL2A_20221017T105041 ... |
| __arlas__     |  __centroid__*     |  Product extend centroid |  Geometry (point) | POINT(43,26) |
| __arlas__ & __stac__ |  __geometry__*     |  Product's extend    |  Geometry (polygon) | POLYGON(( ... )) |
| __stac__ |  __bbox__*     |  Product's extend    |  float array | [-1.308142205840124, 42.335791505536065,   -0.4124765189393069, 43.33522398161831 ] |
| __arlas__  & __stac__ |  __datetime__*     |  Acquisition date    |  date | 2022-10-17T10:59:22Z |
| __arlas ea__     |  properties.__begin_datetime__     |  Acquisition begin date    |  date | 2022-10-17T10:59:22Z |
| __arlas ea__     |  properties.__end_datetime__     |  Acquisition end date    |  date | 2022-10-17T11:02:54Z |
| __arlas ea__  |  properties.__platform__     |  Platform name       |  string | sentinel-2a |
| __arlas ea__  |  properties.__constellation__|  Constellation name |  string | sentinel-2 |
| __arlas ea__  |  properties.__instrument__   |  Instrument name |  string | msi |
| __arlas ea__  |  properties.__sensor__   |  Sensor name |  string |  |
| __arlas ea__  |  properties.__gsd__          |  Ground Sample Distance : best band resolution |  float | 0.34 |
| __arlas ea__  |  properties.__sensor_type__          |  Sensor type |  string | MSS |
| __arlas ea__  |  properties.__data_type__          |  Data type |  string | OPTICAL |
| __arlas ea__   |  properties.__data_coverage__ |  Percentage of data |  float | 53.37 |
| __arlas ea__   |  properties.__snow_cover__ |  Estimate of snow cover |  float | 8 |
| __arlas ea__   |  properties.__water_cover__ |  Estimate of water cover |  float | 8 |
| __arlas ea__  |  properties.__locations__          |  Locations covers by the extend |  array of string | ["Baztan", "Caparroso", "Lantz"] |
| __arlas ea__  |  properties.__band_codes__ |  Band (variable) codes contained in the product |  array of string | ["B01", "B02", "B03"] |
| __arlas ea__  |  properties.__band_names__ |  Band (variable) names contained in the product |  array of string | ["coastal", "red", "blue"] |
| __arlas__ |  __create_datetime__     |  Creation date time    |  date | 2022-10-17T10:59:22Z |
| __arlas__ |  __update_datetime__     |  Update date time    |  date | 2022-10-17T10:59:22Z |
| __stac>eo__   |  properties.__cloud_cover__ |  Estimate of cloud cover |  float | 8 |
| __stac>view__ |  properties.__off_nadir__ | The angle from the sensor between nadir (straight down) and the scene center  |  float | 0 |
| __stac>view__ |  properties.__incidence_angle__ | Angle between the vertical (normal) to the intercepting surface and the line of sight back to the satellite at the scene center |  int | 0 |
| __stac>view__ |  properties.__azimuth__ |  Angle measured from the sub-satellite point (point on the ground below the platform) between the scene center and true north |  int | 0 |
| __stac>view__ |  properties.__sun_azimuth__ |  From the scene center point on the ground, this is the angle between truth north and the sun |  int | 0 |
| __stac>view__ |  properties.__sun_elevation__ |  The angle from the tangent of the scene center point to the sun |  int | 0 |
| __stac>proj__ |  properties.__epsg__ |  EPSG code of the datasource |  int | 32630 |
| __stac>storage__  | properties.__platform__  |  The cloud provider where data is stored |  string | Google Cloud Platform |
| __stac>storage__  | properties.__region__  |  The region where the data is stored | string  | europe-west1 |
| __stac>storage__  | properties.__requester_pays__  |  Does the data requester pay or is it data manager/cloud provider pays |  boolean | False |
| __stac>storage__  | properties.__tier__  |  The title for the tier type |  string | STANDARD |
| __stac__  | __assets__*  |  An dictionnary of assets, the key should preferably be the same as the `asset.role` value. If ambiguous, a sufix can be added |  Dictionnary of Assets | ... |

`*` mandatory fields at ingestion time

### Asset

The assets model is fully based on the [STAC Asset object](https://github.com/radiantearth/stac-spec/blob/master/item-spec/item-spec.md#asset-object). It has 5 fields:
- href
- title
- description
- type
- roles

The [standarized roles](https://github.com/radiantearth/stac-spec/blob/master/item-spec/item-spec.md#asset-role-types) are:
- thumbnail
- overview
- data
- metadata

also, we commonly use the following roles:
- cog
- zarr

### Extensions:
- [stac>storage](https://github.com/stac-extensions/storage)
- [stac>view](https://github.com/stac-extensions/view)
- [stac>eo](https://github.com/stac-extensions/eo)
- [stac>proj](https://github.com/stac-extensions/projection)

### Enums
__arlas ea>data_type__:
- RADAR
- OPTICAL
- SAR

__stac>storage>platform__:
- Alibaba
- AWS
- Azure
- Google Cloud Platform
- IBM
- Oracle

__stac>storage>tier__:
- STANDARD
- NEARLINE
- COLDLINE
- ARCHIVE


## Generated field table

The fields bellow are generated at ingestion time, based on the provided values.

| Group  | Field name | Field description | Field type| Example|
| --------- | ------------- | -------------------- | ------- | ------ |
| __arlas ea__  |  __has_overview__  | An overview is available  |  Boolean | False |
| __arlas ea__  |  __has_thumbnail__  | A thumbnail is available  |  Boolean | False |
| __arlas ea__  |  __has_metadata__  | A matadata file is available  |  Boolean | False |
| __arlas ea__  |  __has_data__  | The target data file is available  |  Boolean | False |
| __arlas ea__  |  __has_cog__  | A cog is available  |  Boolean | False |
| __arlas ea__  |  __has_zarr__  | A zarr is available  |  Boolean | False |
| __arlas ea__  |  __date_keywords__  | Natural langage description of the date  |  Array of string | ["autumn","2022","October"] |
| __arlas ea__  |  __day_of_week__  |  Day of week, monday to sunday [0-6] | int | 4 |
| __arlas ea__  |  __day_of_year__  |  Day within the year [0-365] | int | 67 |
| __arlas ea__  |  __hour_of_day__  |  Hour within the day [0-23] | int | 17 |
| __arlas ea__  |  __minute_of_day__  | Minute within the day [0-1439]  | int | 265 |
