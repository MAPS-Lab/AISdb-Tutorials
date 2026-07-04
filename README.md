# Tutorials

Hands-on Jupyter notebook companions to the [AISViz GitBook tutorials](https://aisviz.gitbook.io/tutorials/). Each notebook is a runnable walkthrough of one part of the [AISdb](https://github.com/MAPS-Lab/AISdb) workflow, from decoding raw AIS messages into a database through querying, cleaning, interpolation, calculations, visualization, and export. The notebooks run against a bundled sample database, so no external data downloads are needed to follow along.

## Notebooks

The numbered notebooks build on each other and are best read in order. The final walkthrough stands alone and tours the whole pipeline in one sitting.

| # | Notebook | Topic |
|---|----------|-------|
| 0 | [0-quick-start.ipynb](0-quick-start.ipynb) | Complete end-to-end walkthrough of the full AISdb pipeline |
| 1 | [1-database-loading.ipynb](1-database-loading.ipynb) | Decoding raw AIS messages into a SQLite database |
| 2 | [2-data-querying.ipynb](2-data-querying.ipynb) | Querying with `DBQuery` and building vessel tracks with `TrackGen` |
| 3 | [3-data-cleaning.ipynb](3-data-cleaning.ipynb) | Denoising shared MMSIs, corrupted positions, and impossible jumps |
| 4 | [4-data-visualization.ipynb](4-data-visualization.ipynb) | Mapping AIS tracks with AISdb and common Python plotting packages |
| 5 | [5-track-interpolation.ipynb](5-track-interpolation.ipynb) | Filling gaps in vessel tracks by interpolation |
| 6 | [6-calculations.ipynb](6-calculations.ipynb) | Great-circle distance and speed calculations with `aisdb.gis` |
| 7 | [7-using-your-ais-data.ipynb](7-using-your-ais-data.ipynb) | Turning your own raw AIS files into queryable tracks |
| 8 | [8-export-data-to-csv.ipynb](8-export-data-to-csv.ipynb) | Exporting decoded AIS tracks to CSV |
| 9 | [9-bathymetric-data.ipynb](9-bathymetric-data.ipynb) | Merging GEBCO bathymetry onto AIS tracks |

## Running the notebooks

Install AISdb and Jupyter, then launch from a clone of this repository so the notebooks can find the sample database next to them.

```bash
pip install aisdb jupyter
git clone git@github.com:MAPS-Lab/AISdb-Tutorials.git
cd Tutorials
jupyter lab
```

The notebooks also run on [Google Colab](https://colab.research.google.com/). Upload the notebook you want together with `example_data.db`, then add a `pip install aisdb` cell at the top before running.

## Sample data

`example_data.db` is a bundled SQLite sample database built with AISdb. It covers vessel traffic in the Gulf of Maine during January 2022 and contains roughly 54 vessels, which is small enough to query and plot instantly while still exercising every feature the notebooks demonstrate.

## Continuous integration

Continuous integration validates that every notebook parses as nbformat 4 and carries no committed outputs on every push and pull request.

## Documentation

[Docs](https://aisviz.gitbook.io/documentation/) · [Tutorials](https://aisviz.gitbook.io/tutorials/) · [API reference](https://aisviz.cs.dal.ca/AISdb/) · [Website](https://aisviz.cs.dal.ca/)

## Related projects

- [AISdb](https://github.com/MAPS-Lab/AISdb), the core Python/Rust platform for storing, querying, and analyzing AIS data
- [AISdb-lite](https://github.com/MAPS-Lab/AISdb-lite), a lightweight AISdb variant built on PostGIS and TimescaleDB hypertables
- [NOAA-Integrator](https://github.com/MAPS-Lab/NOAA-Integrator), an acquisition pipeline from NOAA Marine Cadastre into AISdb-aligned databases

## License

This project is licensed under the GNU Affero General Public License v3.0. See [LICENSE](LICENSE) for the full text.
