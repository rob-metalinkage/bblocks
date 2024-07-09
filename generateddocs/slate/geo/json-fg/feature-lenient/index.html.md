---
title: JSON-FG Feature - Lenient (Schema)

toc_footers:
  - Version 0.1
  - <a href='#'>JSON-FG Feature - Lenient</a>
  - <a href='https://blocks.ogc.org/register.html'>Building Blocks register</a>

search: true

code_clipboard: true

meta:
  - name: JSON-FG Feature - Lenient (Schema)
---


# JSON-FG Feature - Lenient `ogc.geo.json-fg.feature-lenient`

A OGC Features and Geometries JSON (JSON-FG) Feature that does not require the "time" and "place" properties.

<p class="status">
    <span data-rainbow-uri="http://www.opengis.net/def/status">Status</span>:
    <a href="http://www.opengis.net/def/status/stable" target="_blank" data-rainbow-uri>Stable</a>
</p>

<aside class="success">
This building block is <strong>valid</strong>
</aside>

# Description

OGC Features and Geometries JSON (JSON-FG) extends GeoJSON to support a limited set of additional capabilities that are
out-of-scope for GeoJSON, but that are essential or important for a variety of use cases involving feature data.

This Building Block extends the standard JSON-FG one by removing the requirement to provide values for the 
"time" and "place" properties.


# JSON Schema

```yaml--schema
allOf:
- $ref: https://rob-metalinkage.github.io/bblocks/annotated-schemas/geo/features/feature/schema.yaml
- type: object
  required:
  - type
  - geometry
  - properties
  properties:
    type:
      type: string
      enum:
      - Feature
      x-jsonld-id: '@type'
    id:
      oneOf:
      - type: number
      - type: string
      x-jsonld-id: '@id'
    featureType:
      $ref: https://beta.schemas.opengis.net/json-fg/featuretype.json
      x-jsonld-id: '@type'
    links:
      type: array
      items:
        allOf:
        - $ref: https://beta.schemas.opengis.net/json-fg/link.json
        - $ref: https://rob-metalinkage.github.io/bblocks/annotated-schemas/ogc-utils/json-link/schema.yaml
      x-jsonld-id: http://www.w3.org/2000/01/rdf-schema#seeAlso
    time:
      $ref: https://rob-metalinkage.github.io/bblocks/annotated-schemas/geo/json-fg/time/schema.yaml
      x-jsonld-id: http://purl.org/dc/terms/time
    coordRefSys:
      $ref: https://beta.schemas.opengis.net/json-fg/coordrefsys.json
      x-jsonld-id: http://www.opengis.net/def/glossary/term/CoordinateReferenceSystemCRS
    place:
      $ref: https://beta.schemas.opengis.net/json-fg/place.json
      x-jsonld-id: http://purl.org/dc/terms/spatial
    geometry:
      $ref: https://beta.schemas.opengis.net/json-fg/geometry.json
      x-jsonld-id: http://www.opengis.net/ont/geosparql#hasGeometry
      x-jsonld-type: '@json'
    properties:
      oneOf:
      - type: 'null'
      - type: object
      x-jsonld-id: '@nest'
x-jsonld-extra-terms:
  Feature: geojson:Feature
  FeatureCollection: geojson:FeatureCollection
  bbox:
    x-jsonld-container: '@list'
    x-jsonld-id: geojson:bbox
  features:
    x-jsonld-container: '@set'
    x-jsonld-id: geojson:features
  geometries:
    x-jsonld-id: geojson:geometry
    x-jsonld-container: '@list'
x-jsonld-prefixes:
  geo: http://www.opengis.net/ont/geosparql#
  rdfs: http://www.w3.org/2000/01/rdf-schema#
  dct: http://purl.org/dc/terms/
  owlTime: http://www.w3.org/2006/time#

```

> <a target="_blank" href="https://avillar.github.io/TreedocViewer/?dataParser=yaml&amp;dataUrl=https%3A%2F%2Frob-metalinkage.github.io%2Fbblocks%2Fannotated-schemas%2Fgeo%2Fjson-fg%2Ffeature-lenient%2Fschema.yaml&amp;expand=2&amp;option=%7B%22showTable%22%3A+false%7D">View on YAML Viewer</a>

Links to the schema:

* YAML version: <a href="https://rob-metalinkage.github.io/bblocks/annotated-schemas/geo/json-fg/feature-lenient/schema.yaml" target="_blank">https://rob-metalinkage.github.io/bblocks/annotated-schemas/geo/json-fg/feature-lenient/schema.yaml</a>
* JSON version: <a href="https://rob-metalinkage.github.io/bblocks/annotated-schemas/geo/json-fg/feature-lenient/schema.json" target="_blank">https://rob-metalinkage.github.io/bblocks/annotated-schemas/geo/json-fg/feature-lenient/schema.json</a>


# JSON-LD Context

```json--ldContext
{
  "@context": {
    "type": "@type",
    "id": "@id",
    "properties": "@nest",
    "geometry": {
      "@context": {
        "coordinates": {
          "@container": "@list",
          "@id": "geojson:coordinates"
        }
      },
      "@id": "geo:hasGeometry",
      "@type": "@json"
    },
    "bbox": {
      "@container": "@list",
      "@id": "geojson:bbox"
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
    "links": {
      "@context": {
        "href": {
          "@type": "@id",
          "@id": "oa:hasTarget"
        },
        "rel": {
          "@context": {
            "@base": "http://www.iana.org/assignments/relation/"
          },
          "@id": "http://www.iana.org/assignments/relation",
          "@type": "@id"
        },
        "type": "dct:type",
        "hreflang": "dct:language",
        "title": "rdfs:label",
        "length": "dct:extent"
      },
      "@id": "rdfs:seeAlso"
    },
    "featureType": "@type",
    "time": {
      "@context": {
        "date": {
          "@id": "owlTime:hasTime",
          "@type": "xsd:date"
        },
        "timestamp": {
          "@id": "owlTime:hasTime",
          "@type": "xsd:dateTime"
        },
        "interval": {
          "@id": "owlTime:hasTime",
          "@container": "@list"
        }
      },
      "@id": "dct:time"
    },
    "coordRefSys": "http://www.opengis.net/def/glossary/term/CoordinateReferenceSystemCRS",
    "place": "dct:spatial",
    "geometries": {
      "@id": "geojson:geometry",
      "@container": "@list"
    },
    "geojson": "https://purl.org/geojson/vocab#",
    "rdfs": "http://www.w3.org/2000/01/rdf-schema#",
    "oa": "http://www.w3.org/ns/oa#",
    "dct": "http://purl.org/dc/terms/",
    "geo": "http://www.opengis.net/ont/geosparql#",
    "owlTime": "http://www.w3.org/2006/time#",
    "xsd": "http://www.w3.org/2001/XMLSchema#",
    "@version": 1.1
  }
}
```

> <a target="_blank" href="https://json-ld.org/playground/#json-ld=https%3A%2F%2Frob-metalinkage.github.io%2Fbblocks%2Fannotated-schemas%2Fgeo%2Fjson-fg%2Ffeature-lenient%2Fcontext.jsonld">View on JSON-LD Playground</a>

You can find the full JSON-LD context here:
<a href="https://rob-metalinkage.github.io/bblocks/annotated-schemas/geo/json-fg/feature-lenient/context.jsonld" target="_blank">https://rob-metalinkage.github.io/bblocks/annotated-schemas/geo/json-fg/feature-lenient/context.jsonld</a>

# References

* [OGC Testbed-17: OGC Features and Geometries JSON Engineering Report](http://docs.ogc.org/per/21-017r1.html)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: <a href="https://github.com/rob-metalinkage/bblocks" target="_blank">https://github.com/rob-metalinkage/bblocks</a>
* Path:
<code><a href="https://github.com/rob-metalinkage/bblocks/blob/HEAD/registereditems/geo/json-fg/feature-lenient" target="_blank">registereditems/geo/json-fg/feature-lenient</a></code>

