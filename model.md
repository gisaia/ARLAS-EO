# ARLAS EO Data Model


| Group  | Field name | Field description | Field type| Example|
| --------- | ------------- | -------------------- | ------- | ------ |
| arlas     |  id           | Unique identifier    |  String |  |
| arlas     |  centroid     |  Product extend centroid |  Geometry (point) |  |
| arlas     |  extend       |  Product's extend    |  Geometry (polygon) |  |
| arlas     |  datetime     |  Acquisition date    |  date |  |
| arlas ea  |  platform     |  Platform name       |  string | sentinel-2a |
| arlas ea  |  constellation|  Constellation namle |  string | sentinel-2 |
| arlas ea  |  instruments  |   |  string | msi |
| arlas ea  |  gsd          |  Ground Sample Distance |  int | 10 |
| arlas ea  |  off_nadir |   |   |  |
| arlas ea  |   |   |   |  |
| arlas ea  |   |   |   |  |
| arlas ea  |   |   |   |  |



        "view:off_nadir": 0,
        "proj:epsg": 32630,
        "sentinel:utm_zone": 30,
        "sentinel:latitude_band": "T",
        "sentinel:grid_square": "XN",
        "sentinel:sequence": "0",
        "sentinel:product_id": "S2A_MSIL2A_20221017T105041_N0400_R051_T30TXN_20221017T170159",
        "sentinel:data_coverage": 53.37,
        "eo:cloud_cover": 13.33,
        "sentinel:valid_cloud_cover": true,
        "sentinel:processing_baseline": "04.00",
        "created": "2022-10-17T19:36:53.571Z",
        "updated": "2022-10-17T19:36:53.571Z"
