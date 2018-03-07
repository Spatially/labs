# SpatiallyDB

For more information about SpatiallyDB, please visit [Spatially Labs](https://spatially.com/labs)

## Layers

### Create layer

_Request_

```json
POST https://api.spatially.com/spatialdb/layer

Headers:
  Content-Type: application/json
  Authorization: Bearer ACCESS_TOKEN_GENERATED_FROM_API

Body:
  {
    "name": "layer-name"
   }
```

_Response_

```json
{
  "id": "...",
  "name": "layer-name"
}
```

### Get layer

_Request_

```json
GET https://api.spatially.com/spatialdb/layer/{id}

Headers:
  Content-Type: application/json
  Authorization: Bearer ACCESS_TOKEN_GENERATED_FROM_API
```

_Response_

```json
{
  "id": "...",
  "name": "layer-name"
}
```

### Get layers

_Request_

```json
GET https://api.spatially.com/spatialdb/layers

Headers:
  Content-Type: application/json
  Authorization: Bearer ACCESS_TOKEN_GENERATED_FROM_API
```

_Response_

```json
[
  {
    "id": "...",
    "name": "layer-name"
  }
]
```

### Delete layer

_Request_

```json
DELETE https://api.spatially.com/spatialdb/layer/{id}

Headers:
  Content-Type: application/json
  Authorization: Bearer ACCESS_TOKEN_GENERATED_FROM_API
```

## Features

### Create feature

_Request_

```json
POST https://api.spatially.com/spatialdb/feature

Headers:
  Content-Type: application/json
  Authorization: Bearer ACCESS_TOKEN_GENERATED_FROM_API

Body:
  {
    "layer": "{id}",
    "feature": {
      // valid GeoJSON feature
      "type": "Feature",
      "properties": {
        "key": "value"
      },
      "geometry": {
        "type": "Point",
        "coordinates": [
          -76.2890625,
          39.639537564366684
        ]
      }
    }
   }
```

_Response_

```json
{
  "id": "..."
}
```

### Get feature

_Request_

```json
GET https://api.spatially.com/spatialdb/feature/{id}

Headers:
  Content-Type: application/json
  Authorization: Bearer ACCESS_TOKEN_GENERATED_FROM_API
```

_Response_

```json
{
  "type": "Feature",
  "properties": {
    "key": "value"
  },
  "geometry": {
    "type": "Point",
    "coordinates": [-76.2890625, 39.639537564366684]
  }
}
```

### Get features by layer

_Request_

```json
POST https://api.spatially.com/spatialdb/features

Headers:
  Content-Type: application/json
  Authorization: Bearer ACCESS_TOKEN_GENERATED_FROM_API

Body:
  {
    "layer": "{id}"
  }
```

_Response_

```json
[
  {
    "type": "Feature",
    "properties": {
      "key": "value"
    },
    "geometry": {
      "type": "Point",
      "coordinates": [-76.2890625, 39.639537564366684]
    }
  }
]
```

### Get features by layer & spatial constraint

_Request_

```json
POST https://api.spatially.com/spatialdb/features

Headers:
  Content-Type: application/json
  Authorization: Bearer ACCESS_TOKEN_GENERATED_FROM_API

Body:
  {
    "layer": "{id}"
    "spatialConstraint": {
      "wkt": "POLYGON (...)",
      "type": 0
    }
  }

  // Or if doing a buffer query
  {
    "layer": "{id}"
    "spatialConstraint": {
      "wkt": "POINT (...)",
      "radius": 100, // in meters
      "type": 0
    }
  }
```

_Response_

```json
[
  {
    "type": "Feature",
    "properties": {
      "key": "value"
    },
    "geometry": {
      "type": "Point",
      "coordinates": [-76.2890625, 39.639537564366684]
    }
  }
]
```

### Update feature

_Request_

```json
PUT https://api.spatially.com/spatialdb/feature/{id}

Headers:
  Content-Type: application/json
  Authorization: Bearer ACCESS_TOKEN_GENERATED_FROM_API

Body:
  {
    "properties": {
      "key2": "value2"
    }
  }
```

_Response_

```json
{
  "type": "Feature",
  "properties": {
    "key": "value",
    "key2": "value2"
  },
  "geometry": {
    "type": "Point",
    "coordinates": [-76.2890625, 39.639537564366684]
  }
}
```

### Delete feature

_Request_

```json
DELETE https://api.spatially.com/spatialdb/feature/{id}

Headers:
  Content-Type: application/json
  Authorization: Bearer ACCESS_TOKEN_GENERATED_FROM_API
```
