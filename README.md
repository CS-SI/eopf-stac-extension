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
| eopf:resolutions         | object                                                 | Dictionary of ground resolutions |
| eopf:type                | string                                                 | Product type                     |
| eopf:timeline            | string                                                 | Processing timeline              |
| eopf:collection          | string                                                 | Product collection identifier    |
| eopf:processing_baseline | string                                                 | Processing baseline identifier   |
| eopf:data_take_id        | string                                                 | Unique acquisition identifier    |
| eopf:intrument_mode      | string                                                 | Instrument mode                  |
| eopf:instrument_swath    | string                                                 | Instrument swath                 |
| eopf:image_size          | \[[Image Size Object](#image-size-object)]             | Image sizes in pixels            |
| eopf:pixel_classification| \[[Pixel Quality Object](#pixel-classification-object)]| Pixel quality classification     |


### Additional Information

#### eopf:resolutions

`eopf:resolutions` provides a dictionary of image resolution per type of image in the product.
It is recommended to provide at least the best resolution in the product. 
 
#### eopf:image_size

`eopf:image_size` provides the sizes in rows and columns of each image in the product, as well as its position.
An Item is only allowed to use `eopf:image_size` in its Properties if it has at least one asset with a defined image size array.

#### eopf:pixel_classification

`eopf:pixel_classification` provides the amount of pixels with a quality classification, in counts and / or in percentage.
An Item is only allowed to use `eopf:pixel_classification` in its Properties if it has at least one asset with a defined pixel class array.


### Image Size Object

| Field Name          | Type   | Description |
| ------------------- | ------ | ----------- |
| name                | string | The name of the image (e.g. "B01", "band2", "red", "nadir"). |
| start_offset        | number | Position of element (0,*) wrt product start |
| track_offset        | number | Position of element (*,0) wrt sub-satellite track |
| rows                | number | Number of rows |
| columns             | number | Number of columns |

### Pixel Classification Object

| Field Name          | Type   | Description |
| ------------------- | ------ | ----------- |
| name                | string | The name of the pixel quality class |
| count               | number | Number of pixels affected by flag |
| percent             | number | Percentage of pixels affected by flag |


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
