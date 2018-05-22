# Grid

Spatially Grid gives you access to a variety of datasets processed and updated daily by the Spatially platform.


## Population

```
GET https://api.spatially.com/grid/pop/point?lon=-71.05878365218564&lat=42.355270748343685&radius=150

Headers:
  Content-Type: application/json
  Authorization: Bearer ACCESS_TOKEN_GENERATED_FROM_API

Response:
{
    "result": {
        "residents": 174,
        "workers": 17000,
        "housing": 4600000,
        "housingMeanValue": 4332000,
        "housingMedianValue": 81,
        "housingSumValue": 44
    }
}
```

## Trade Area Population

```
POST https://api.spatially.com/grid/pop

Headers:
  Content-Type: application/json
  Authorization: Bearer ACCESS_TOKEN_GENERATED_FROM_API
  
 Request Body:
   {"featureCollection": { "features": [...] } }
   
 Response:
   {
      "residents":155717,
      "workers":114552,
      "housing":1270794000,
      "housingMeanValue":1215303000,
      "housingMedianValue":83819,
      "housingSumValue":93448
   }

## Activity

Activity is an hourly breakdown of all the stops observed at a location for any given radius allowing you to determine the most popular times of day people are observed within that radius.

```
GET https://api.spatially.com/grid/stops?wkt=POINT(-71.05878365218564 42.355270748343685)&radius=150

Headers:
  Content-Type: application/json
  Authorization: Bearer ACCESS_TOKEN_GENERATED_FROM_API

Response:
{
    "result": [
        {
            "hour": 0,
            "stops": 86
        },
        {
            "hour": 20,
            "stops": 591
        },
        {
            "hour": 10,
            "stops": 1330
        },
        {
            "hour": 1,
            "stops": 51
        },
        {
            "hour": 21,
            "stops": 356
        },
        {
            "hour": 11,
            "stops": 1630
        },
        {
            "hour": 2,
            "stops": 42
        },
        {
            "hour": 22,
            "stops": 265
        },
        {
            "hour": 12,
            "stops": 2390
        },
        {
            "hour": 3,
            "stops": 16
        },
        {
            "hour": 23,
            "stops": 145
        },
        {
            "hour": 13,
            "stops": 1962
        },
        {
            "hour": 4,
            "stops": 29
        },
        {
            "hour": 14,
            "stops": 1578
        },
        {
            "hour": 5,
            "stops": 240
        },
        {
            "hour": 15,
            "stops": 1423
        },
        {
            "hour": 16,
            "stops": 1550
        },
        {
            "hour": 6,
            "stops": 505
        },
        {
            "hour": 17,
            "stops": 1729
        },
        {
            "hour": 7,
            "stops": 1360
        },
        {
            "hour": 18,
            "stops": 1161
        },
        {
            "hour": 8,
            "stops": 2766
        },
        {
            "hour": 19,
            "stops": 720
        },
        {
            "hour": 9,
            "stops": 2031
        }
    ]
}
```

## Distance Sentivity

Distance Sensitivity is a measure of how far people typically travel to a location from their home address (0-1, 1-2, 2-5, 5-10, 10-15, 15-20, 20-25 miles).

```
GET https://api.spatially.com/grid/distance?lon=-71.05878365218564&lat=42.355270748343685&radius=150

Headers:
  Content-Type: application/json
  Authorization: Bearer ACCESS_TOKEN_GENERATED_FROM_API

Response:
{
    "result": {
        "d0": 2577,
        "d1": 1199,
        "d2": 4124,
        "d5": 5493,
        "d10": 2316,
        "d15": 1455,
        "d20": 1340,
        "d25": 5442
    }
}
```

## Highlights

```
GET https://api.spatially.com/grid/highlights?lon=-71.05878365218564&lat=42.355270748343685&radius=150

Headers:
  Content-Type: application/json
  Authorization: Bearer ACCESS_TOKEN_GENERATED_FROM_API

Response:
{
    "result": {
        "total": 6,
        "workerTypes": [
            {
                "type": "white",
                "count": 5
            },
            {
                "type": "service",
                "count": 1
            }
        ],
        "populationTypes": [
            {
                "type": "mixed",
                "count": 2
            },
            {
                "type": "worker",
                "count": 4
            }
        ],
        "demographics": {
            "totalResidents": 122,
            "totalRenters": 102,
            "totalOwners": 20,
            "maleOver25": 147,
            "maleWithBA": 56,
            "maleWithMaster": 15,
            "maleWithProfessional": 10,
            "maleWithPHD": 0,
            "femaleOver25": 127,
            "femaleWithBA": 18,
            "femaleWithMaster": 12,
            "femaleWithProfessional": 3,
            "femaleWithPHD": 3,
            "femaleUnder18": 8,
            "female18To24": 38,
            "female25To44": 38,
            "female45To64": 11,
            "female65AndUp": 33,
            "maleUnder18": 1,
            "male18To24": 11,
            "male25To44": 67,
            "male45To64": 13,
            "male65AndUp": 54,
            "femaleTotal": 127,
            "maleTotal": 147,
            "femaleHighschool": 32,
            "femaleSomeCollege": 3,
            "femaleSomeHighschool": 9,
            "maleHighschool": 37,
            "maleSomeCollege": 13,
            "maleSomeHighschool": 3,
            "educationOver25": 215,
            "totalHouseholds": 56,
            "femaleHouseholdWithChildren": 0,
            "femaleHouseholdNoChildren": 3,
            "marriedHouseholdWithChildren": 6,
            "marriedHouseholdNoChildren": 47,
            "maleHouseholdWithChildren": 0,
            "maleHouseholdNoChildren": 0,
            "NonFamilyHousehold": 65,
            "totalFamilyHouseholds": 121,
            "income200AndUp": 37,
            "income75To100": 3,
            "income100To125": 8,
            "income125To150": 4,
            "income150To200": 9,
            "income25AndBelow": 55,
            "income25To50": 3,
            "income50To75": 3,
            "incomeTotalHouseholds": 121,
            "insurance18AndUp": 274,
            "insurancePurchased": 26,
            "insuranceEmployer": 124,
            "insuranceMedicaid": 22,
            "insuranceMedicare": 39,
            "insuranceNone": 1,
            "insuranceOneType": 211,
            "insuranceTricare": 0,
            "insuranceTwoTypes": 62,
            "insuranceVA": 0,
            "tenureTotalUnits": 121,
            "tenureOwnerOccupied15To24": 4,
            "tenureOwnerOccupied25To34": 0,
            "tenureOwnerOccupied35To44": 2,
            "tenureOwnerOccupied45To54": 8,
            "tenureOwnerOccupied55To64": 0,
            "tenureOwnerOccupied65To74": 5,
            "tenureOwnerOccupied75To84": 0,
            "tenureOwnerOccupied85AndUp": 0,
            "tenureRenterOccupied15To24": 3,
            "tenureRenterOccupied25To34": 33,
            "tenureRenterOccupied35To44": 6,
            "tenureRenterOccupied45To54": 0,
            "tenureRenterOccupied55To64": 4,
            "tenureRenterOccupied65To74": 31,
            "tenureRenterOccupied75To84": 17,
            "tenureRenterOccupied85AndUp": 7
        }
    }
}
```
