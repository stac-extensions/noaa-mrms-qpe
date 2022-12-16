# NOAA MRMS QPE Extension Specification

- **Title:** NOAA MRMS QPE
- **Identifier:** <https://stac-extensions.github.io/noaa-mrms-qpe/v1.0.0/schema.json>
- **Field Name Prefix:** noaa_mrms_qpe
- **Scope:** Item, Collection
- **Extension [Maturity Classification](https://github.com/radiantearth/stac-spec/tree/master/extensions/README.md#extension-maturity):** Pilot
- **Owner**: @m-mohr

This document explains the NOAA MRMS QPE Extension to the
[SpatioTemporal Asset Catalog](https://github.com/radiantearth/stac-spec) (STAC) specification.

- Examples:
  - [Item example](examples/item.json): Shows the basic usage of the extension in a STAC Item
  - [Collection example](examples/collection.json): Shows the basic usage of the extension in a STAC Collection
- [JSON Schema](json-schema/schema.json)
- [Changelog](./CHANGELOG.md)

## Fields

The fields in the table below can be used in these parts of STAC documents:
- [ ] Catalogs
- [x] Collections
- [x] Item Properties (incl. Summaries in Collections)
- [x] Assets (for both Collections and Items, incl. Item Asset Definitions in Collections)
- [ ] Links

| Field Name           | Type    | Description |
| -------------------- | ------- | ----------- |
| noaa_mrms_qpe:pass   | integer | **REQUIRED**. The pass number: `1` = less latency, but less gauges; `2` = more latency, but more gauges. |
| noaa_mrms_qpe:period | integer | **REQUIRED**. The number of hours of the accumulations. One of: `1`, `3`, `6`, `12`, `24`, `48`, `72` |
| noaa_mrms_qpe:region | string  | **REQUIRED**. The region of the data. One of: `CONUS` (Continental US), `HAWAII`, `GUAM`, `ALASKA`, `CARIB` (Caribbean Islands) |

## Contributing

All contributions are subject to the
[STAC Specification Code of Conduct](https://github.com/radiantearth/stac-spec/blob/master/CODE_OF_CONDUCT.md).
For contributions, please follow the
[STAC specification contributing guide](https://github.com/radiantearth/stac-spec/blob/master/CONTRIBUTING.md) Instructions
for running tests are copied here for convenience.

### Running tests

The same checks that run as checks on PR's are part of the repository and can be run locally to verify that changes are valid. 
To run tests locally, you'll need `npm`, which is a standard part of any [node.js installation](https://nodejs.org/en/download/).

First you'll need to install everything with npm once. Just navigate to the root of this repository and on 
your command line run:
```bash
npm install
```

Then to check markdown formatting and test the examples against the JSON schema, you can run:
```bash
npm test
```

This will spit out the same texts that you see online, and you can then go and fix your markdown or examples.

If the tests reveal formatting problems with the examples, you can fix them with:
```bash
npm run format-examples
```
