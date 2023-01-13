Goal: to try and isolate unwanted features in MATSim networks using graph measures.

Currently only imports MATSim XML and exports nothing besides visualisations. Mainly using [`pydeck`](https://pydeck.gl/) for interactive network visualisation and [`momepy`](https://github.com/pysal/momepy) to compute graph measures. 

+ Before using, create and activate a python 3.10.6 (or possibly later) virtual environment:
+ With conda: 

``` sh
conda create env -n graph-measures-env python=3.10.6
conda activate graph-measures-env
```

+ (**preferred**): With [pyenv](https://formulae.brew.sh/formula/pyenv#default) & the [pyenv-virtualenv](https://formulae.brew.sh/formula/pyenv-virtualenv#default) plugin:

``` sh
pyenv virtualenv 3.10.6 graph-measures-env
pyenv activate graph-measures-env
```

+ Install the requirements: 

``` sh
pip install requirements.txt
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
