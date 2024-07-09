---
title: Mixin for feature with GeoSPARQL geometry (Schema)

language_tabs:
  - json: JSON
  - jsonld: JSON-LD
  - turtle: RDF/Turtle

toc_footers:
  - Version 1.0
  - <a href='#'>Mixin for feature with GeoSPARQL geometry</a>
  - <a href='https://blocks.ogc.org/register.html'>Building Blocks register</a>

search: true

code_clipboard: true

meta:
  - name: Mixin for feature with GeoSPARQL geometry (Schema)
---


# Mixin for feature with GeoSPARQL geometry `ogc.geo.features.geosparqlGeometry`

This schema can be used as a mixin for feature objects to represent their geometry as a literal GeoSPARQL value instead of an RDF resource

<p class="status">
    <span data-rainbow-uri="http://www.opengis.net/def/status">Status</span>:
    <a href="http://www.opengis.net/def/status/stable" target="_blank" data-rainbow-uri>Stable</a>
</p>

<aside class="success">
This building block is <strong><a href="https://github.com/rob-metalinkage/bblocks/blob/master/tests/geo/features/geosparqlGeometry/" target="_blank">valid</a></strong>
</aside>

# Examples

## Sample feature with POINT GeoSPARQL geometry



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

<blockquote class="lang-specific json">
  <p class="example-links">
    <a target="_blank" href="https://rob-metalinkage.github.io/bblocks/tests/geo/features/geosparqlGeometry/example_1_1.json">Open in new window</a>
    <a target="_blank" href="https://avillar.github.io/TreedocViewer/?dataParser=json&amp;dataUrl=https%3A%2F%2Frob-metalinkage.github.io%2Fbblocks%2Ftests%2Fgeo%2Ffeatures%2FgeosparqlGeometry%2Fexample_1_1.json&amp;expand=2&amp;option=%7B%22showTable%22%3A+false%7D">View on JSON Viewer</a></p>
</blockquote>




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

<blockquote class="lang-specific jsonld">
  <p class="example-links">
    <a target="_blank" href="https://rob-metalinkage.github.io/bblocks/tests/geo/features/geosparqlGeometry/example_1_1.jsonld">Open in new window</a>
    <a target="_blank" href="https://json-ld.org/playground/#json-ld=https%3A%2F%2Frob-metalinkage.github.io%2Fbblocks%2Ftests%2Fgeo%2Ffeatures%2FgeosparqlGeometry%2Fexample_1_1.jsonld">View on JSON-LD Playground</a>
</blockquote>




```turtle
@prefix geo: <http://www.opengis.net/ont/geosparql#> .
@prefix rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#> .

[] geo:hasGeometry "{\"coordinates\":[174.7501603083,-36.9307359096],\"type\":\"Point\"}"^^rdf:JSON .


```

<blockquote class="lang-specific turtle">
  <p class="example-links">
    <a target="_blank" href="https://rob-metalinkage.github.io/bblocks/tests/geo/features/geosparqlGeometry/example_1_1.ttl">Open in new window</a>
</blockquote>



## Sample object using the "geometry" mixin



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

<blockquote class="lang-specific json">
  <p class="example-links">
    <a target="_blank" href="https://rob-metalinkage.github.io/bblocks/tests/geo/features/geosparqlGeometry/example_2_1.json">Open in new window</a>
    <a target="_blank" href="https://avillar.github.io/TreedocViewer/?dataParser=json&amp;dataUrl=https%3A%2F%2Frob-metalinkage.github.io%2Fbblocks%2Ftests%2Fgeo%2Ffeatures%2FgeosparqlGeometry%2Fexample_2_1.json&amp;expand=2&amp;option=%7B%22showTable%22%3A+false%7D">View on JSON Viewer</a></p>
</blockquote>




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

<blockquote class="lang-specific jsonld">
  <p class="example-links">
    <a target="_blank" href="https://rob-metalinkage.github.io/bblocks/tests/geo/features/geosparqlGeometry/example_2_1.jsonld">Open in new window</a>
    <a target="_blank" href="https://json-ld.org/playground/#json-ld=https%3A%2F%2Frob-metalinkage.github.io%2Fbblocks%2Ftests%2Fgeo%2Ffeatures%2FgeosparqlGeometry%2Fexample_2_1.jsonld">View on JSON-LD Playground</a>
</blockquote>




```turtle
@prefix geo: <http://www.opengis.net/ont/geosparql#> .
@prefix rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#> .

[] geo:hasGeometry "{\"coordinates\":[[[-3.911628540272403,43.651451755119155],[-4.151550411746342,43.431113348164445],[-4.007817057797524,43.198127563783316],[-3.5760153469796023,43.29143725429333],[-3.455852048155407,43.63987947818879],[-3.911628540272403,43.651451755119155]]],\"type\":\"Polygon\"}"^^rdf:JSON .


```

<blockquote class="lang-specific turtle">
  <p class="example-links">
    <a target="_blank" href="https://rob-metalinkage.github.io/bblocks/tests/geo/features/geosparqlGeometry/example_2_1.ttl">Open in new window</a>
</blockquote>



# JSON Schema

```yaml--schema
type: object
properties:
  geometry:
    $ref: https://rob-metalinkage.github.io/bblocks/annotated-schemas/geo/common/data_types/geojson/schema.yaml#/properties/geometry
    x-jsonld-id: http://www.opengis.net/ont/geosparql#hasGeometry
    x-jsonld-type: '@json'
x-jsonld-prefixes:
  geo: http://www.opengis.net/ont/geosparql#

```

> <a target="_blank" href="https://avillar.github.io/TreedocViewer/?dataParser=yaml&amp;dataUrl=https%3A%2F%2Frob-metalinkage.github.io%2Fbblocks%2Fannotated-schemas%2Fgeo%2Ffeatures%2FgeosparqlGeometry%2Fschema.yaml&amp;expand=2&amp;option=%7B%22showTable%22%3A+false%7D">View on YAML Viewer</a>

Links to the schema:

* YAML version: <a href="https://rob-metalinkage.github.io/bblocks/annotated-schemas/geo/features/geosparqlGeometry/schema.yaml" target="_blank">https://rob-metalinkage.github.io/bblocks/annotated-schemas/geo/features/geosparqlGeometry/schema.yaml</a>
* JSON version: <a href="https://rob-metalinkage.github.io/bblocks/annotated-schemas/geo/features/geosparqlGeometry/schema.json" target="_blank">https://rob-metalinkage.github.io/bblocks/annotated-schemas/geo/features/geosparqlGeometry/schema.json</a>


# JSON-LD Context

```json--ldContext
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

> <a target="_blank" href="https://json-ld.org/playground/#json-ld=https%3A%2F%2Frob-metalinkage.github.io%2Fbblocks%2Fannotated-schemas%2Fgeo%2Ffeatures%2FgeosparqlGeometry%2Fcontext.jsonld">View on JSON-LD Playground</a>

You can find the full JSON-LD context here:
<a href="https://rob-metalinkage.github.io/bblocks/annotated-schemas/geo/features/geosparqlGeometry/context.jsonld" target="_blank">https://rob-metalinkage.github.io/bblocks/annotated-schemas/geo/features/geosparqlGeometry/context.jsonld</a>

# Validation

## SHACL Shapes

The following sets of SHACL shapes are used for validating this building block:

* Mixin for feature with GeoSPARQL geometry <small><code>ogc.geo.features.geosparqlGeometry</code></small>
  * [https://rob-metalinkage.github.io/bblocks/registereditems/geo/features/geosparqlGeometry/rules.shacl](https://rob-metalinkage.github.io/bblocks/registereditems/geo/features/geosparqlGeometry/rules.shacl)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: <a href="https://github.com/rob-metalinkage/bblocks" target="_blank">https://github.com/rob-metalinkage/bblocks</a>
* Path:
<code><a href="https://github.com/rob-metalinkage/bblocks/blob/HEAD/registereditems/geo/features/geosparqlGeometry" target="_blank">registereditems/geo/features/geosparqlGeometry</a></code>

