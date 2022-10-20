# ARLAS EO Data Model

## Field table

| Group  | Field name | Field description | Field type| Example|
| --------- | ------------- | -------------------- | ------- | ------ |
| __arlas__ & __stac__     |  __id__*           | Unique identifier    |  String |  |
| __arlas__     |  __centroid__*     |  Product extend centroid |  Geometry (point) |  |
| __arlas__ & __stac__ |  __geometry__*     |  Product's extend    |  Geometry (polygon) |  |
| __stac__ |  __bbox__*     |  Product's extend    |  Geometry (polygon) |  |
| __arlas__     |  __datetime__*     |  Acquisition date    |  date |  |
| __arlas ea__  |  properties.__platform__     |  Platform name       |  string | sentinel-2a |
| __arlas ea__  |  properties.__constellation__|  Constellation namle |  string | sentinel-2 |
| __arlas ea__  |  properties.__instrument__   |  Instrument name |  string | msi |
| __arlas ea__  |  properties.__gsd__          |  Ground Sample Distance : best band resolution |  float | 0.34 |
| __arlas ea__   |  __data_coverage__ |  Percentage of data |  float | 53.37 |
| __stac>view__ |  properties.__off_nadir__ | The angle from the sensor between nadir (straight down) and the scene center  |  int | 0 |
| __stac>view__ |  properties.__incidence_angle__ | Angle between the vertical (normal) to the intercepting surface and the line of sight back to the satellite at the scene center |  int | 0 |
| __stac>view__ |  properties.__azimuth__ |  Angle measured from the sub-satellite point (point on the ground below the platform) between the scene center and true north |  int | 0 |
| __stac>view__ |  properties.__sun_azimuth__ |  From the scene center point on the ground, this is the angle between truth north and the sun |  int | 0 |
| __stac>view__ |  properties.__sun_elevation__ |  The angle from the tangent of the scene center point to the sun |  int | 0 |
| __stac>eo__   |  properties.__cloud_cover__ |  Estimate of cloud cover |  int | 8 |
| __stac>proj__ |  properties.__epsg__ |  EPSG code of the datasource |  int | 32630 |
| __stac>storage__  | properties.__platform__  |  The cloud provider where data is stored |  string | Google Cloud Platform |
| __stac>storage__  | properties.__region__  |  The region where the data is stored | string  | europe-west1 |
| __stac>storage__  | properties.__requester_pays__  |  Is the data requester pays or is it data manager/cloud provider pays |  boolean | False |
| __stac>storage__  | properties.__tier__  |  The title for the tier type |  string |  |

Extensions:
- [stac>storage](https://github.com/stac-extensions/storage)
- [stac>view](https://github.com/stac-extensions/view)
- [stac>eo](https://github.com/stac-extensions/eo)
- [stac>proj](https://github.com/stac-extensions/proj)

## Enums
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
