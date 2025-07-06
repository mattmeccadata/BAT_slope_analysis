# Iceflow Pathfinder: Least-Cost Path Analysis in Antarctica using REMA Data

This project demonstrates the use of high-resolution Arctic DEM data (REMA) via the STAC API to compute least-cost paths over ice sheets in the British Antarctic Territory (BAT). The goal is to showcase a use of elevation-derived slope data in Antarctica. Other potential use cases include modeling potential ice flow paths or simulating optimal navigation routes across Antarctic terrain.

## Use Case

- **Core Example:** Compute the least-cost path between two points using slope data derived from REMA DEMs.
- **Broader Application:** Model potential ice flow paths and understand glaciological processes.

## Project Structure

```
BAT_slope_analysis/
├── data/ # Input datasets
│ └── bat_boundary/ # Antarctic boundary shapefiles
│   ├──── bat_boundary.shp
│   ├──── bat_boundary.shx
│   ├──── bat_boundary.dbf
│   ├──── bat_boundary.prj
│   ├──── bat_boundary.cpg
├── notebooks/ # Jupyter notebooks with analysis
│ └── least_cost_path.ipynb
├── outputs/ # Resulting rasters
│ ├──── least_cost_path.tif
│ ├──── cost_surface.tif
│ ├──── slope_degrees.tif
├── README.md # Project documentation
├── requirements.txt # Python dependencies
├── .gitignore # Git ignore rules
```


## How to Run

1. Clone the repo:
    ```bash
    git clone https://github.com/mattmeccadata/BAT_slope_analysis.git
    cd BAT_slope_analysis
    ```

2. Set up the environment:
    ```bash
    pip install -r requirements.txt
    ```

3. Open the notebook:
    ```bash
    jupyter lab
    ```

## Data

-REMA elevation data
    - **Source:** REMA DEM via [STAC API](https://stac.pgc.umn.edu/api/v1/); collection: rema-mosaics-v2.0-32m
    - **Derived:** Slope raster computed from DEM

-British Antarctic Territory (BAT) boundary
    - **Source:** Harris, U. (2009) Antarctic Territorial Claims GIS, Ver. 1,  <em>Australian Antarctic Data Centre</em> - <a href="https://data.aad.gov.au/metadata/gis108">https://data.aad.gov.au/metadata/gis108</a>, Accessed: 2025-06-24
    - **Region:** BAT (British Antarctic Territory)

## Dependencies

- `geopandas`
- `shapely`
- `pystac-client`
- `stackstac`
- `rioxarray`
- `numpy`
- `xarray`
- `matplotlib`
- `scipy`
- `rasterio`

See `requirements.txt` for the full list.

## Output Rasters

- `outputs/cost_surface.tif`
- `outputs/least_cost.tif`
- `outputs/slope_degrees.tif`

---

## License

This work is licensed under the Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International License. To view a copy of this license, visit

https://creativecommons.org/licenses/by-nc-sa/4.0/
