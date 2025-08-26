# AI Ecosystem Extension Specification

- **Title:** AI ecosystem
- **Identifier:** <https://fiboa.github.io/ai-ecosystem-extension/v0.2.0/schema.yaml>
- **Property Name Prefix:** ml
- **Extension Maturity Classification:** Proposal
- **Owner**: @hannah-rae @subash-khanal @yanglexie @jacobsn @eddiechoi00

This document explains the AI Ecosystem Extension to the
[Field Boundaries for Agriculture (fiboa)](https://fiboa.org) and
[Vecorel](https://vecorel.org) specifications.

This extension adds support for properties useful for integrating field boundary data with the AI/ML ecosystem.

- Examples:
  - [GeoJSON](examples/geojson/)
  - [GeoParquet](examples/geoparquet/)
- [Schema](schema/schema.yaml)
- [Changelog](./CHANGELOG.md)

## Properties

| Property Name    | Type     | Description                                                  |
| ---------------- | -------- | ------------------------------------------------------------ |
| ml:boundary_type | string   | **REQUIRED**. Whether the boundary is for a field, ownership parcel, hedge, or other boundary |
| ml:creation_date | datetime | **REQUIRED**. Date the collection was created or published   |
| ml:verified_from | datetime | **REQUIRED**. The first date for which the boundary is verified to be present on ground (e.g. through ground-truth or remote sensing image verification) |
| ml:author        | string   | **REQUIRED**. Name of individual or organization who created this. |
| ml:admin2        | string   | A unique admin2 (county) name for the administrative region that contains the field. The feature contains the last part of the [HASC 2 codes](https://data.apps.fao.org/catalog/dataset/hasc-codes/resource/76ec426d-deac-4bc4-b558-3095bb89c805). |

### Additional Properties

Additionally, the following properties from from the
[core specification](https://github.com/fiboa/specification/blob/main/core/README.md#determination-properties)
are **REQUIRED**:

- category
- determination:method
- determination:datetime

Lastly, the following properties from from the
[Administrative Division extension](https://github.com/vecorel/administrative-division-extension/blob/main/core/README.md)
are **REQUIRED**:

- admin:country_code
- admin:subdivision_code

> [!NOTE]  
> Country Code, Subdivision Code and admin2 can be derived from [GADM boundaries](https://geodata.ucdavis.edu/gadm/).

## Contributing

See the [contributing guideline](CONTRIBUTING.md) for more details.
