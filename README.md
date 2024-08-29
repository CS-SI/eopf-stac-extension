# eopf-stac-extension

- **Title:** Earth Observation Processing Framework
- **Identifier:** <https://stac-extensions.github.io/eopf/v1.0.0/schema.json>
- **Field Name Prefix:** eopf
- **Scope:** Item, Collection
- **Extension [Maturity Classification](https://github.com/radiantearth/stac-spec/tree/master/extensions/README.md#extension-maturity):** Proposal
- **Owner**: CS Group France
- **History:** Proposal in preparation

This document explains the fields of the EOPF extension to the
[SpatioTemporal Asset Catalog](https://github.com/radiantearth/stac-spec) (STAC) specification.

EOPF is the framework of Copernicus Sentinel data processors under development by ESA.
See [EOPF site](https://eopf.copernicus.eu/) for context.

It is strongly recommended to use the other STAC extensions eo, view, processing, sat and sci with the eopf extension.

## Item Properties or Asset Fields

| Field Name               | Type                                                   | Description                      |
| ------------------------ | ------------------------------------------------------ | -------------------------------- |
| eopf:data_strip_id       | string                                                 | Data strip identification        |
| eopf:data_take_id        | string                                                 | Data taken identification        |
| eopf:instrument_mode     | string                                                 | Instrument mode                  |
| eopf:instrument_configuration_id    | integer                                     | Instrument configuration         |
| eopf:origin_datetime     | datetime                                               | ???                              |

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
