
# Bounding Box (Schema)

`ogc.geo.common.data_types.bounding_box` *v1.0.1*

The bounding box JSON object describes a simple spatial extent of a resource. For OGC API’s this could be a feature, a feature collection or a dataset, but it can be used in any JSON resource that wants to communicate its rough location. The extent is simple in that the bounding box does not describe the precise location and shape of the resource, but provides an axis-aligned approximation of the spatial extent that can be used as an initial test whether two resources are potentially intersecting each other.

[*Status*](http://www.opengis.net/def/status): Stable

## Description

A bounding box is provided as an array of four or six numbers, depending on whether the coordinate reference system includes a vertical axis (height or depth):

* Lower left corner, coordinate axis 1
* Lower left corner, coordinate axis 2
* Minimum value, coordinate axis 3 (optional)
* Upper right corner, coordinate axis 1
* Upper right corner, coordinate axis 2
* Maximum value, coordinate axis 3 (optional)

If the value consists of four numbers, the coordinate reference system is WGS 84 longitude/latitude (http://www.opengis.net/def/crs/OGC/1.3/CRS84) unless a different coordinate reference system is specified.

If the value consists of six numbers, the coordinate reference system is WGS 84 longitude/latitude/height (http://www.opengis.net/def/crs/OGC/0/CRS84h) unless a different coordinate reference system is specified.

How a different coordinate reference system is specified depends on the context in which the bounding box is used.

For WGS 84 longitude/latitude the values are in most cases the sequence of minimum longitude, minimum latitude, maximum longitude and maximum latitude. However, in cases where the box spans the antimeridian the first value (west-most box edge) is larger than the third value (east-most box edge).

If the vertical axis is included, the third and the sixth number are the bottom and the top of the 3-dimensional bounding box.

The text representation of a bounding box is based on the JSON representation and represents the array as comma-separated values.

## Examples

### Axis-aligned minimum bounding box of the 48 contiguous states of the United States of America (JSON)
#### json
```json
[-124.7844079, 24.7433195, -66.9513812, 49.3457868]
```

#### plaintext
```plaintext
-124.7844079,24.7433195,-66.9513812,49.3457868
```

## Schema

```yaml
type: array
oneOf:
- minItems: 4
  maxItems: 4
- minItems: 6
  maxItems: 6
items:
  type: number

```

Links to the schema:

* YAML version: [schema.yaml](https://rob-metalinkage.github.io/bblocks/annotated-schemas/geo/common/data_types/bounding_box/schema.json)
* JSON version: [schema.json](https://rob-metalinkage.github.io/bblocks/annotated-schemas/geo/common/data_types/bounding_box/schema.yaml)

## Sources

* [OGC API - Features, Part 1, 7.13.2: Feature Collections Response](http://www.opengis.net/doc/IS/ogcapi-features-1/1.0#_response_4)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/rob-metalinkage/bblocks](https://github.com/rob-metalinkage/bblocks)
* Path: `registereditems/geo/common/data_types/bounding_box`

