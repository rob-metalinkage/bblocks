
# GeoPose Basic-Quaternion (Schema)

`ogc.geo.geopose.basic.quaternion` *v0.1*

Basic GeoPose using quaternion to specify orientation

[*Status*](http://www.opengis.net/def/status): Under development

## Schema

```yaml
description: 'Basic-Quaternion: Basic GeoPose using quaternion to specify orientation'
definitions:
  Position:
    type: object
    properties:
      lat:
        type: number
        x-jsonld-id: http://www.w3.org/2003/01/geo/wgs84_pos#lat
      lon:
        type: number
        x-jsonld-id: http://www.w3.org/2003/01/geo/wgs84_pos#long
      h:
        type: number
        x-jsonld-id: http://example.com/geopose/h
    required:
    - lat
    - lon
    - h
  Quaternion:
    type: object
    properties:
      x:
        type: number
        x-jsonld-id: http://example.com/geopose/x
      y:
        type: number
        x-jsonld-id: http://example.com/geopose/y
      z:
        type: number
        x-jsonld-id: http://example.com/geopose/z
      w:
        type: number
        x-jsonld-id: http://example.com/geopose/w
    required:
    - x
    - y
    - z
    - w
type: object
properties:
  position:
    $ref: '#/definitions/Position'
    x-jsonld-id: http://example.com/geopose/position
  quaternion:
    $ref: '#/definitions/Quaternion'
    x-jsonld-id: http://example.com/geopose/quaternion
required:
- position
- quaternion
x-jsonld-prefixes:
  geopose: http://example.com/geopose/
  geo: http://www.w3.org/2003/01/geo/wgs84_pos#

```

Links to the schema:

* YAML version: [schema.yaml](https://rob-metalinkage.github.io/bblocks/annotated-schemas/geo/geopose/basic/quaternion/schema.json)
* JSON version: [schema.json](https://rob-metalinkage.github.io/bblocks/annotated-schemas/geo/geopose/basic/quaternion/schema.yaml)


# JSON-LD Context

```jsonld
{
  "@context": {
    "position": {
      "@context": {},
      "@id": "geopose:position"
    },
    "quaternion": {
      "@context": {},
      "@id": "geopose:quaternion"
    },
    "lat": "geo:lat",
    "lon": "geo:long",
    "h": "geopose:h",
    "x": "geopose:x",
    "y": "geopose:y",
    "z": "geopose:z",
    "w": "geopose:w",
    "geopose": "http://example.com/geopose/",
    "geo": "http://www.w3.org/2003/01/geo/wgs84_pos#",
    "@version": 1.1
  }
}
```

You can find the full JSON-LD context here:
[context.jsonld](https://rob-metalinkage.github.io/bblocks/annotated-schemas/geo/geopose/basic/quaternion/context.jsonld)

## Sources

* [OGC GeoPose 1.0 Data Exchange Draft Standard](https://docs.ogc.org/dis/21-056r10/21-056r10.html)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/rob-metalinkage/bblocks](https://github.com/rob-metalinkage/bblocks)
* Path: `registereditems/geo/geopose/basic/quaternion`

