# xyzservices

Source of XYZ tiles providers.

![Illustrative tiles. (C) OpenStreetMap, (C) OpenMapTIles, (C) Stadia Maps, (C) OpenTopoMap,  (C) Thunderforest, (C) JawgMaps, (C) Stamen Design, (C) Esri -- Source: Esri, i-cubed, USDA, USGS, AEX, GeoEye, Getmapping, Aerogrid, IGN, IGP, UPR-EGP, and the GIS User Community](_static/xyzmaps.jpg)

`xyzservices` is a lightweight library providing a repository of available XYZ services
offering raster basemap tiles. The repository is provided via Python API and as a
compressed JSON file.

XYZ tiles can be used as background for your maps to provide necessary spatial context.
`xyzservices` offer specifications of many tile services and provide an easy-to-use
tools to plug them into your work, no matter if interactive or static.

[![Tests](https://github.com/geopandas/xyzservices/actions/workflows/tests.yaml/badge.svg)](https://github.com/geopandas/xyzservices/actions/workflows/tests.yaml) [![codecov](https://codecov.io/gh/geopandas/xyzservices/branch/main/graph/badge.svg?token=PBSZQA48GY)](https://codecov.io/gh/geopandas/xyzservices)

## Quick Start

Using `xyzservices` is simple and in most cases does not involve more than a line of
code.

### Installation

You can install `xyzservices` from `conda` or `pip`:

```shell
conda install xyzservices -c conda-forge
```

```shell
pip install xyzservices
```

The package does not depend on any other apart from those built-in in Python.

### Providers API

The key part of `xyzservices` are providers:

```py
>>> import xyzservices.providers as xyz
```

`xyzservices.providers` or just `xyz` for short is a `Bunch` of providers, an enhanced
`dict`. If you are in Jupyter-like environment, `xyz` will offer collapsible inventory
of available XYZ tile sources. You can also explore it as a standard `dict` using
`xyz.keys()`. Once you have picked your provider, you get its details as a
`TileProvider` object with all the details you may need:

```py
>>> xyz.CartoDB.Positron.url
'https://{s}.basemaps.cartocdn.com/{variant}/{z}/{x}/{y}{r}.png'

>>> xyz.CartoDB.Positron.attribution
'(C) OpenStreetMap contributors (C) CARTO'
```

You can also check if the `TileProvider` needs API token and pass it to the object if
needed.

```py
>>> xyz.MapBox.requires_token()
True

>>> xyz.MapBox["accessToken"] = "my_personal_token"
>>> xyz.MapBox.requires_token()
False
```

### Providers JSON

After the installation, you will find the JSON used as a database of providers in
`share/xyzservices/providers.json` if you want to use it outside of a Python ecosystem.

## Contributors

`xyzservices` is developed by a community of enthusiastic volunteers and lives under
[`geopandas`](https://github.com/geopandas) GitHub organization. You can see a full list
of contributors [here](https://github.com/geopandas/xyzservices/graphs/contributors).

If you would like to contribute to the project, have a look at the list of
[open issues](https://github.com/geopandas/contextily/issues), particularly those labeled as
[good first issue](https://github.com/geopandas/xyzservices/issues?q=is%3Aopen+is%3Aissue+label%3A%22good+first+issue%22).

## License

BSD 3-Clause License


```{toctree}
---
maxdepth: 2
caption: Documentation
hidden: true
---
introduction
api
contributing
changelog
GitHub <https://github.com/geopandas/xyzservices>
```
