# Catalog holding collection definitions for [gtif-uk-ireland-france](https://gtif-uk-ireland-france.org/)

This repository allows generation of STAC catalogs based on the configuration JSON files provided in the repository.
The configuration options are described in the [Wiki](https://github.com/eodash/eodash_catalog/wiki).

The generation of the catalog runs automatically through github actions when pushing/merging to main branch. The final STAC catalog is pushed to `GitHub Pages` via `gh-pages` branch.

Deployment branches just with the changed collections in Pull Requests are generated automatically too.

The generated STAC catalogs are deployed through github pages.

A preview of the catalogs can be seen using the [Stac Browser](https://radiantearth.github.io/stac-browser/#/)

Here are preloaded preview links for the catalog available through gh-pages:
* [Deployed catalog via STAC Browser](https://radiantearth.github.io/stac-browser/#/external/gtif-ukif.github.io/gtif-ukif-catalog/gtif-ukif/catalog.json)

## Development

In order to run the catalog generation locally, install the [eodash_catalog tool](https://github.com/eodash/eodash_catalog) and run the generation locally via 

```bash
pip install eodash_catalog
eodash_catalog
```
Optionally you can generate only a subset of collections using the command line arguments:

```bash
eodash_catalog <collection1_file_name> <collection2_file_name>
```

The catalogs are saved in the `build` folder. If you want to test the generated catalog locally (either in the Stac Browser or with the eodash client) we recommend using npm [http-server](https://www.npmjs.com/package/http-server), especially to avoid possible CORS issues you can run it for example with following command:
`npx http-server -p 8000 --cors` 
when located in the build folder. 
