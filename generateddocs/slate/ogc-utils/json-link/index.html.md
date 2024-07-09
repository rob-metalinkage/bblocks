---
title: JSON Link (Schema)

toc_footers:
  - Version 0.1
  - <a href='#'>JSON Link</a>
  - <a href='https://blocks.ogc.org/register.html'>Building Blocks register</a>

search: true

code_clipboard: true

meta:
  - name: JSON Link (Schema)
---


# JSON Link `ogc.ogc-utils.json-link`

Web linking is used to express relationships between resources. The JSON object representation of links described here is used consistently in OGC API’s.

<p class="status">
    <span data-rainbow-uri="http://www.opengis.net/def/status">Status</span>:
    <a href="http://www.opengis.net/def/status/stable" target="_blank" data-rainbow-uri>Stable</a>
</p>

<aside class="success">
This building block is <strong>valid</strong>
</aside>


# JSON Schema

```yaml--schema
$schema: https://json-schema.org/draft/2020-12/schema
description: JSON Link
type: object
required:
- href
- rel
properties:
  href:
    type: string
    format: uri-reference
    x-jsonld-type: '@id'
    x-jsonld-id: http://www.w3.org/ns/oa#hasTarget
  rel:
    type: string
    x-jsonld-id: http://www.iana.org/assignments/relation
    x-jsonld-type: '@id'
    x-jsonld-base: http://www.iana.org/assignments/relation/
  anchor:
    type: string
  type:
    type: string
    x-jsonld-id: http://purl.org/dc/terms/type
  hreflang:
    type: string
    x-jsonld-id: http://purl.org/dc/terms/language
  title:
    type: string
    x-jsonld-id: http://www.w3.org/2000/01/rdf-schema#label
  length:
    type: integer
    x-jsonld-id: http://purl.org/dc/terms/extent
x-jsonld-prefixes:
  oa: http://www.w3.org/ns/oa#
  rdfs: http://www.w3.org/2000/01/rdf-schema#
  dct: http://purl.org/dc/terms/

```

> <a target="_blank" href="https://avillar.github.io/TreedocViewer/?dataParser=yaml&amp;dataUrl=https%3A%2F%2Frob-metalinkage.github.io%2Fbblocks%2Fannotated-schemas%2Fogc-utils%2Fjson-link%2Fschema.yaml&amp;expand=2&amp;option=%7B%22showTable%22%3A+false%7D">View on YAML Viewer</a>

Links to the schema:

* YAML version: <a href="https://rob-metalinkage.github.io/bblocks/annotated-schemas/ogc-utils/json-link/schema.yaml" target="_blank">https://rob-metalinkage.github.io/bblocks/annotated-schemas/ogc-utils/json-link/schema.yaml</a>
* JSON version: <a href="https://rob-metalinkage.github.io/bblocks/annotated-schemas/ogc-utils/json-link/schema.json" target="_blank">https://rob-metalinkage.github.io/bblocks/annotated-schemas/ogc-utils/json-link/schema.json</a>


# JSON-LD Context

```json--ldContext
{
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
    "length": "dct:extent",
    "oa": "http://www.w3.org/ns/oa#",
    "rdfs": "http://www.w3.org/2000/01/rdf-schema#",
    "dct": "http://purl.org/dc/terms/",
    "@version": 1.1
  }
}
```

> <a target="_blank" href="https://json-ld.org/playground/#json-ld=https%3A%2F%2Frob-metalinkage.github.io%2Fbblocks%2Fannotated-schemas%2Fogc-utils%2Fjson-link%2Fcontext.jsonld">View on JSON-LD Playground</a>

You can find the full JSON-LD context here:
<a href="https://rob-metalinkage.github.io/bblocks/annotated-schemas/ogc-utils/json-link/context.jsonld" target="_blank">https://rob-metalinkage.github.io/bblocks/annotated-schemas/ogc-utils/json-link/context.jsonld</a>

# References

* [IETF RFC 8288 - Web Linking](https://www.rfc-editor.org/rfc/rfc8288.txt)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: <a href="https://github.com/rob-metalinkage/bblocks" target="_blank">https://github.com/rob-metalinkage/bblocks</a>
* Path:
<code><a href="https://github.com/rob-metalinkage/bblocks/blob/HEAD/registereditems/ogc-utils/json-link" target="_blank">registereditems/ogc-utils/json-link</a></code>

