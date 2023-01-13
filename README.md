+ Before using, install dependencies: 

``` sh
pip install matsim-tools pandas shapely numpy pydeck geopandas networkx momepy matplotlib jupyter jupyterlab
```

+ Then enable `pydeck` widgets:
   + If using jupyter notebook:

``` sh
jupyter nbextension install --sys-prefix --symlink --overwrite --py pydeck
jupyter nbextension enable --sys-prefix --py pydeck
```

   + If using jupyter lab:

``` sh
jupyter labextension install @jupyter-widgets/jupyterlab-manager
DECKGL_SEMVER=`python -c "import pydeck; print(pydeck.frontend_semver.DECKGL_SEMVER)"`
jupyter labextension install @deck.gl/jupyter-widget@$DECKGL_SEMVER
```

+ You'll also need a mapbox API key, which you can get by creating a [free mapbox account](https://www.mapbox.com/) and setting the key like this inside the python notbook, before running, in the first cell:

``` python
os.environ['MAPBOX_API_KEY'] = 'replace this string with a string containing your key'
```

You should now be ready to rock.
