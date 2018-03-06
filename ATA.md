# ATA (Active Trade Area)

For more information about ATA, please visit [Spatially](https://spatially.com)

## Generate an ATA

_Request_

```json
POST https://api.spatially.com/ads/science/ata

Headers:
  Content-Type: application/json
  Authorization: Bearer ACCESS_TOKEN_GENERATED_FROM_API

Body:
  {
    "pointWKT": "POINT(-71.064156780428 42.35862883483673)",
    "timeOfDay": "AllDay",
    "locationType": ["Home"]
   }
```

_Response_

```json
{
  "version": 2,
  "buffer": 100,
  "featureCollection": {
    "type": "FeatureCollection",
    "features": [ ... ]
  }
}
```

### Parameters

#### pointWKT

This parameter is a Well-Known-Text (WKT) point of the location you wish to generate an Active Trade Area on.

#### timeOfDay

This parameter dictates what time of day you want the observations to be taken from. By default it is `AllDAy`, other possible values are:

* Morning
* MidDay
* Evening
* Night

#### locationType

This parameter defines what type of locations you wish to generate the Active Trade Area from. By default it is `Home` locations. Other possible values are:

* Work
* HomeAndWork
