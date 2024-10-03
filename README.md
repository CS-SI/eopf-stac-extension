# eopf-stac-extension

- **Title:** Earth Observation Processing Framework
- **Identifier:** [<https://stac-extensions.github.io/eopf/v1.0.0/schema.json>](https://github.com/CS-SI/eopf-stac-extension/raw/refs/tags/v1.1.0/json-schema/schema.json)
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
| eopf:datastrip_id       | string                                                 | Datastrip identification (specific to Sentinel-2). Example: S2A_OPER_MSI_L2A_DS_2APS_20240308T143352_S20240308T101546_N05.10|
| eopf:datatake_id        | string                                                 | Datatake identification. Examples: for S1, datatake_id = 12032; for S2, datatake_id = GS2A_20231215T103431_044292_N05.10     |
| eopf:instrument_configuration_id    | integer                                     | The instrument configuration ID is specific to S1 SAR instrument and refers to the onboard configuration. Each version of it has a specific identifier called "Instrument Configuration ID" (ICID) corresponding to a specific number. For more information, cf. ["What is the instrument configuration ID (ICID) ?"](https://sar-mpc.eu/about/faq/) |
| eopf:instrument_mode     | string                                                 | Instrument_mode (specific to Sentinel-2). Supports all datatake_type values: INS-NOBS, INS-EOBS, INS-DASC, INS-ABSR, INS-VIC, INS-RAW, INS-TST, INS-NOBD, INS-ABSD, INS-DASD, INS-VICD |
| eopf:origin_datetime     | datetime                                               | Date time of the input data considered to create the item. Example: for PRIP, time of the availability of all CADU data on the CADIP/XBIP                             |

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
