
# Mixin for feature with GeoSPARQL geometry (Schema)

`ogc.geo.features.geosparqlGeometry` *v1.0*

This schema can be used as a mixin for feature objects to represent their geometry as a literal GeoSPARQL value instead of an RDF resource

[*Status*](http://www.opengis.net/def/status): Stable

## Examples

### Sample feature with POINT GeoSPARQL geometry
#### json
```json
{
  "id": "f1",
  "type": "Feature",
  "geometry": {
    "type": "Point",
    "coordinates": [
      174.7501603083,
      -36.9307359096
    ]
  },
  "properties": {
    "comment": "An attribute value"
  }
}

```

#### jsonld
```jsonld
{
  "id": "f1",
  "type": "Feature",
  "geometry": {
    "type": "Point",
    "coordinates": [
      174.7501603083,
      -36.9307359096
    ]
  },
  "properties": {
    "comment": "An attribute value"
  },
  "@context": "https://rob-metalinkage.github.io/bblocks/annotated-schemas/geo/features/geosparqlGeometry/context.jsonld"
}
```

#### ttl
```ttl
@prefix geo: <http://www.opengis.net/ont/geosparql#> .
@prefix rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#> .

[] geo:hasGeometry "{\"coordinates\":[174.7501603083,-36.9307359096],\"type\":\"Point\"}"^^rdf:JSON .


```


### Sample object using the "geometry" mixin
#### json
```json
{
  "type": "Hospital",
  "geometry": {
    "coordinates": [
      [
        [
          -3.911628540272403,
          43.651451755119155
        ],
        [
          -4.151550411746342,
          43.431113348164445
        ],
        [
          -4.007817057797524,
          43.198127563783316
        ],
        [
          -3.5760153469796023,
          43.29143725429333
        ],
        [
          -3.455852048155407,
          43.63987947818879
        ],
        [
          -3.911628540272403,
          43.651451755119155
        ]
      ]
    ],
    "type": "Polygon"
  }
}

```

#### jsonld
```jsonld
{
  "type": "Hospital",
  "geometry": {
    "coordinates": [
      [
        [
          -3.911628540272403,
          43.651451755119155
        ],
        [
          -4.151550411746342,
          43.431113348164445
        ],
        [
          -4.007817057797524,
          43.198127563783316
        ],
        [
          -3.5760153469796023,
          43.29143725429333
        ],
        [
          -3.455852048155407,
          43.63987947818879
        ],
        [
          -3.911628540272403,
          43.651451755119155
        ]
      ]
    ],
    "type": "Polygon"
  },
  "@context": "https://rob-metalinkage.github.io/bblocks/annotated-schemas/geo/features/geosparqlGeometry/context.jsonld"
}
```

#### ttl
```ttl
@prefix geo: <http://www.opengis.net/ont/geosparql#> .
@prefix rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#> .

[] geo:hasGeometry "{\"coordinates\":[[[-3.911628540272403,43.651451755119155],[-4.151550411746342,43.431113348164445],[-4.007817057797524,43.198127563783316],[-3.5760153469796023,43.29143725429333],[-3.455852048155407,43.63987947818879],[-3.911628540272403,43.651451755119155]]],\"type\":\"Polygon\"}"^^rdf:JSON .


```

## Schema

```yaml
type: object
properties:
  geometry:
    $ref: https://rob-metalinkage.github.io/bblocks/annotated-schemas/geo/common/data_types/geojson/schema.yaml#/properties/geometry
    x-jsonld-id: http://www.opengis.net/ont/geosparql#hasGeometry
    x-jsonld-type: '@json'
x-jsonld-prefixes:
  geo: http://www.opengis.net/ont/geosparql#

```

Links to the schema:

* YAML version: [schema.yaml](https://rob-metalinkage.github.io/bblocks/annotated-schemas/geo/features/geosparqlGeometry/schema.json)
* JSON version: [schema.json](https://rob-metalinkage.github.io/bblocks/annotated-schemas/geo/features/geosparqlGeometry/schema.yaml)


# JSON-LD Context

```jsonld
{
  "@context": {
    "geometry": {
      "@context": {
        "type": "@type",
        "coordinates": {
          "@container": "@list",
          "@id": "geojson:coordinates"
        },
        "bbox": {
          "@container": "@list",
          "@id": "geojson:bbox"
        }
      },
      "@id": "geo:hasGeometry",
      "@type": "@json"
    },
    "Feature": "geojson:Feature",
    "FeatureCollection": "geojson:FeatureCollection",
    "GeometryCollection": "geojson:GeometryCollection",
    "LineString": "geojson:LineString",
    "MultiLineString": "geojson:MultiLineString",
    "MultiPoint": "geojson:MultiPoint",
    "MultiPolygon": "geojson:MultiPolygon",
    "Point": "geojson:Point",
    "Polygon": "geojson:Polygon",
    "features": {
      "@container": "@set",
      "@id": "geojson:features"
    },
    "geojson": "https://purl.org/geojson/vocab#",
    "geo": "http://www.opengis.net/ont/geosparql#",
    "@version": 1.1
  }
}
```

You can find the full JSON-LD context here:
[context.jsonld](https://rob-metalinkage.github.io/bblocks/annotated-schemas/geo/features/geosparqlGeometry/context.jsonld)


# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/rob-metalinkage/bblocks](https://github.com/rob-metalinkage/bblocks)
* Path: `registereditems/geo/features/geosparqlGeometry`

