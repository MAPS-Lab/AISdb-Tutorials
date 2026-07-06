# AISdb Tutorials

AISdb Tutorials is a collection of runnable Jupyter notebooks with worked examples for the [AISdb](https://github.com/MAPS-Lab/AISdb) workflow, walking through the full pipeline from decoding raw AIS messages into a database through querying, cleaning, interpolation, calculations, visualization, and export. Each notebook runs against a bundled SQLite sample database, so no external data downloads are needed to follow along. The tutorials are developed and maintained by the [MAPS Lab](https://mapslab.tech/) at Dalhousie University, continuing work that began under the [MERIDIAN](https://meridian.cs.dal.ca) initiative.

## Prerequisites

The notebooks require the `aisdb` package and a Jupyter environment. Install both from PyPI.

```bash
pip install aisdb jupyter
```

## Notebooks

The numbered notebooks build on each other and are best read in order. Notebook 0 stands alone and tours the whole pipeline in one sitting.

| # | Notebook | What it teaches |
|---|----------|-----------------|
| 0 | [0-quick-start.ipynb](0-quick-start.ipynb) | End-to-end tour of the full AISdb pipeline against the sample database |
| 1 | [1-database-loading.ipynb](1-database-loading.ipynb) | Decoding raw AIS messages into a SQLite database (and the PostgreSQL equivalent) |
| 2 | [2-data-querying.ipynb](2-data-querying.ipynb) | Querying with `DBQuery` and building vessel tracks with `TrackGen` |
| 3 | [3-data-cleaning.ipynb](3-data-cleaning.ipynb) | Denoising shared MMSIs, corrupted positions, and impossible jumps with `denoising_encoder` |
| 4 | [4-data-visualization.ipynb](4-data-visualization.ipynb) | Mapping AIS tracks with AISdb's `web_interface` and common Python plotting packages |
| 5 | [5-track-interpolation.ipynb](5-track-interpolation.ipynb) | Filling gaps in vessel tracks with linear, great-circle, and spline interpolation |
| 6 | [6-calculations.ipynb](6-calculations.ipynb) | Great-circle distance, speed, and distance-from-shore calculations with `aisdb.gis` |
| 7 | [7-using-your-ais-data.ipynb](7-using-your-ais-data.ipynb) | Turning your own raw AIS files (here, a NOAA daily archive) into queryable tracks |
| 8 | [8-export-data-to-csv.ipynb](8-export-data-to-csv.ipynb) | Exporting decoded AIS tracks to CSV with `aisdb.write_csv` and a custom writer |
| 9 | [9-bathymetric-data.ipynb](9-bathymetric-data.ipynb) | Merging GEBCO bathymetry depth onto AIS tracks with `webdata.bathymetry.Gebco` |

## How to run

Clone this repository and launch Jupyter from the clone so the notebooks can find `example_data.db` next to them.

```bash
git clone git@github.com:MAPS-Lab/AISdb-Tutorials.git
cd AISdb-Tutorials
jupyter lab      # or: jupyter notebook
```

The notebooks also run on [Google Colab](https://colab.research.google.com/). Upload the notebook you want together with `example_data.db`, then add a `pip install aisdb` cell at the top before running.

## Sample data

`example_data.db` is a bundled SQLite sample database built with AISdb. It covers vessel traffic in the Gulf of Maine during January 2022 (roughly 54 vessels), small enough to query and plot instantly while still exercising every feature the notebooks demonstrate.

## Documentation

[Docs](https://aisviz.gitbook.io/documentation/) · [Tutorials](https://aisviz.gitbook.io/tutorials/)

## Related projects

- [AISdb](https://github.com/MAPS-Lab/AISdb), the core Python/Rust platform for storing, querying, and analyzing AIS data
- [AISdb-lite](https://github.com/MAPS-Lab/AISdb-lite), a lightweight AISdb variant built on PostGIS and TimescaleDB hypertables
- [NOAA-Integrator](https://github.com/MAPS-Lab/NOAA-Integrator), an acquisition pipeline from NOAA Marine Cadastre into AISdb-aligned databases

## License

This project is distributed under the terms of the GNU Affero General Public License v3.0 (AGPL-3.0). See [LICENSE](LICENSE) for details.
