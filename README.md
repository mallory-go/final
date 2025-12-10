Ultimate Fighting Championship Dataset Analysis 


Introduction 
The Ultimate Fighting Championship (UFC) is a world wide mixed martial arts (MMA) organization representing thousands of international fighters. The dataset was a publicly available dataset of all UFC fights from the mid-2010s, to December 7, 2024, scraped from ufcstats.com, an independent site that provides comprehensive fight statistics. The data is sourced from FightMetric, the system the official UFC website and broadcast uses for its own records (Ultimate UFC Dataset). The dataset contains three data files describing the event (location, title fight, winners, etc), fight (strikes landed, takedowns, etc), and fighters (biography details, overall performance of the fighter, fighter record, etc). The attributes for each fighter were inputted into the database as the most recent data on the fighter.

Purpose 
This analysis aimed to predict fight wins – with a particular focus on title fight wins – using machine learning algorithms. I predict that all models will not have accurate performance (AUROC > 0.7) due to the volatility of the sport and – historically – unobserved or unrecorded factors such as injuries, psychological issues, or even pure luck (as seen by “upsets” or unexpected outcomes) can impact or determine the winner of a fight. The Red corner is generally considered the “favorite” fighter, the fighter predicted to win the fight, and the Blue corner is assigned to the other fighter. The UFC organization has not disclosed how fighter odds or the ‘favorite’ fighter is determined (Exploring Patterns and Predictors in UFC Fight Outcomes). 

Target variable and Features 
The Ultimate Fighting Championship Dataset is a dataset created for fight analysis, with fighter attributes and fight outcomes. The target variable is ‘Winner’ or the fighter that won a particular fight. AUnlike other datasets, each row of this dataset represented one fight and only the statistics of the fighters at the time of the fight. ‘Winner’ is coded as ‘Red’ (‘1’ after preprocessing) for the fighter in the red corner – the UFC designated favorite – or Blue (‘0’ after preprocessing) for the fighter in the blue corner. There are 6528 datapoints and 235 feature columns in the original dataset. The feature columns consist of event or fight details (location, date, etc.) and fighter characteristics and history (win streak, stance, citizenship, etc). To collapse the amount of features, I calculated the difference between ‘Red’ and ‘Blue’ measurements. For example, reach_diff would be the reach (arm length) of the ‘Blue’ fighter subtracted from the ‘Red’ fighter. 









see "environment.yaml" as well 


name: data1030
channels:
  - conda-forge
  - defaults
dependencies:
  - _python_abi3_support=1.0
  - anyio=4.10.0
  - appnope=0.1.4
  - argon2-cffi=25.1.0
  - argon2-cffi-bindings=25.1.0
  - arrow=1.3.0
  - asttokens=3.0.0
  - async-lru=2.0.5
  - attrs=25.3.0
  - babel=2.17.0
  - beautifulsoup4=4.13.5
  - bleach=6.2.0
  - bleach-with-css=6.2.0
  - brotli=1.1.0
  - brotli-bin=1.1.0
  - brotli-python=1.1.0
  - bzip2=1.0.8
  - ca-certificates=2025.8.3
  - cached-property=1.5.2
  - cached_property=1.5.2
  - certifi=2025.8.3
  - cffi=1.17.1
  - charset-normalizer=3.4.3
  - cloudpickle=3.1.1
  - colorama=0.4.6
  - comm=0.2.3
  - contourpy=1.3.3
  - cpython=3.12.11
  - cycler=0.12.1
  - debugpy=1.8.16
  - decorator=5.2.1
  - defusedxml=0.7.1
  - exceptiongroup=1.3.0
  - executing=2.2.1
  - fonttools=4.59.2
  - fqdn=1.5.1
  - freetype=2.13.3
  - h11=0.16.0
  - h2=4.3.0
  - hpack=4.1.0
  - httpcore=1.0.9
  - httpx=0.28.1
  - hyperframe=6.1.0
  - icu=75.1
  - idna=3.10
  - importlib-metadata=8.7.0
  - ipykernel=6.30.1
  - ipython=9.5.0
  - ipython_pygments_lexers=1.1.1
  - ipywidgets=8.1.7
  - isoduration=20.11.0
  - jedi=0.19.2
  - jinja2=3.1.6
  - joblib=1.5.2
  - json5=0.12.1
  - jsonpointer=3.0.0
  - jsonschema=4.25.1
  - jsonschema-specifications=2025.4.1
  - jsonschema-with-format-nongpl=4.25.1
  - jupyter=1.1.1
  - jupyter-lsp=2.3.0
  - jupyter_client=8.6.3
  - jupyter_console=6.6.3
  - jupyter_core=5.8.1
  - jupyter_events=0.12.0
  - jupyter_server=2.17.0
  - jupyter_server_terminals=0.5.3
  - jupyterlab=4.4.7
  - jupyterlab_pygments=0.3.0
  - jupyterlab_server=2.27.3
  - jupyterlab_widgets=3.0.15
  - kiwisolver=1.4.9
  - krb5=1.21.3
  - lark=1.2.2
  - lcms2=2.17
  - lerc=4.0.0
  - libblas=3.9.0
  - libbrotlicommon=1.1.0
  - libbrotlidec=1.1.0
  - libbrotlienc=1.1.0
  - libcblas=3.9.0
  - libcxx=21.1.0
  - libdeflate=1.24
  - libedit=3.1.20250104
  - libexpat=2.7.1
  - libffi=3.4.6
  - libfreetype=2.13.3
  - libfreetype6=2.13.3
  - libgfortran=15.1.0
  - libgfortran5=15.1.0
  - libjpeg-turbo=3.1.0
  - liblapack=3.9.0
  - liblzma=5.8.1
  - libopenblas=0.3.30
  - libpng=1.6.50
  - libsodium=1.0.20
  - libsqlite=3.50.4
  - libtiff=4.7.0
  - libwebp-base=1.6.0
  - libxcb=1.17.0
  - libxgboost=3.0.0
  - libzlib=1.3.1
  - llvm-openmp=21.1.0
  - llvmlite=0.44.0
  - markupsafe=3.0.2
  - matplotlib=3.10.1
  - matplotlib-base=3.10.1
  - matplotlib-inline=0.1.7
  - mistune=3.1.4
  - munkres=1.1.4
  - nbclient=0.10.2
  - nbconvert-core=7.16.6
  - nbformat=5.10.4
  - ncurses=6.5
  - nest-asyncio=1.6.0
  - notebook=7.4.5
  - notebook-shim=0.2.4
  - numba=0.61.2
  - numpy=2.2.5
  - openjpeg=2.5.3
  - openssl=3.5.2
  - overrides=7.7.0
  - packaging=25.0
  - pandas=2.2.3
  - pandocfilters=1.5.0
  - parso=0.8.5
  - patsy=1.0.1
  - pexpect=4.9.0
  - pickleshare=0.7.5
  - pillow=11.3.0
  - pip=25.2
  - platformdirs=4.4.0
  - polars=1.27.1
  - prometheus_client=0.22.1
  - prompt-toolkit=3.0.52
  - prompt_toolkit=3.0.52
  - psutil=7.0.0
  - pthread-stubs=0.4
  - ptyprocess=0.7.0
  - pure_eval=0.2.3
  - py-xgboost=3.0.0
  - pycparser=2.22
  - pygments=2.19.2
  - pyobjc-core=11.1
  - pyobjc-framework-cocoa=11.1
  - pyparsing=3.2.3
  - pysocks=1.7.1
  - python=3.12.10
  - python-dateutil=2.9.0.post0
  - python-fastjsonschema=2.21.2
  - python-gil=3.12.11
  - python-json-logger=2.0.7
  - python-tzdata=2025.2
  - python_abi=3.12
  - pytz=2025.2
  - pyyaml=6.0.2
  - pyzmq=27.0.2
  - qhull=2020.2
  - readline=8.2
  - referencing=0.36.2
  - requests=2.32.5
  - rfc3339-validator=0.1.4
  - rfc3986-validator=0.1.1
  - rfc3987-syntax=1.1.0
  - rpds-py=0.27.1
  - scikit-learn=1.6.1
  - scipy=1.16.1
  - seaborn=0.13.2
  - seaborn-base=0.13.2
  - send2trash=1.8.3
  - setuptools=80.9.0
  - shap=0.47.2
  - six=1.17.0
  - slicer=0.0.8
  - sniffio=1.3.1
  - soupsieve=2.8
  - stack_data=0.6.3
  - statsmodels=0.14.5
  - terminado=0.18.1
  - threadpoolctl=3.6.0
  - tinycss2=1.4.0
  - tk=8.6.13
  - tomli=2.2.1
  - tornado=6.5.2
  - tqdm=4.67.1
  - traitlets=5.14.3
  - types-python-dateutil=2.9.0.20250822
  - typing-extensions=4.15.0
  - typing_extensions=4.15.0
  - typing_utils=0.1.0
  - tzdata=2025b
  - unicodedata2=16.0.0
  - uri-template=1.3.0
  - urllib3=2.5.0
  - wcwidth=0.2.13
  - webcolors=24.11.1
  - webencodings=0.5.1
  - websocket-client=1.8.0
  - wheel=0.45.1
  - widgetsnbextension=4.0.14
  - xorg-libxau=1.0.12
  - xorg-libxdmcp=1.1.5
  - yaml=0.2.5
  - zeromq=4.3.5
  - zipp=3.23.0
  - zstandard=0.24.0
  - zstd=1.5.7
  - pip:
      - dotenv==0.9.9
      - et-xmlfile==2.0.0
      - kaggle==1.7.4.5
      - kagglehub==0.3.13
      - lightgbm==4.6.0
      - miceforest==6.0.5
      - openpyxl==3.1.5
      - protobuf==6.32.1
      - pyarrow==22.0.0
      - python-dotenv==1.1.1
      - python-slugify==8.0.4
      - text-unidecode==1.3
prefix: /opt/anaconda3/envs/data1030
