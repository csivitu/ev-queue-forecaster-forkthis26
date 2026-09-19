# ev charging grid forecaster

Hello there. this repository is part of our forkthis challenge. we are dealing with time series forecasting for electric vehicle charging hubs using municipal grid telemetry. 

our main goal here is to train a machine learning model (specifically a gradient boosting regressor) that can accurately predict the average charging wait duration based on a 12 hour rolling window of grid load, vehicular traffic, and our custom engineered temporal patterns.

the current notebook pipeline i set up for you contains some intentional, subtle data engineering flaws. these include temporal data leakage, indexing errors, and sequence breaking. your job is to locate these bugs, resolve them, and build out the requested time based features to create a robust forecaster.

### dataset description

the dataset consists of a single municipal telemetry file. you will need to upload this when running the notebook.
* **ev_charging_station_usage_grid_load.csv** – contains hourly time-series data designed to model ev demand and grid impact.
  * **target variable:** `avg_charging_duration_minutes`
  * **continuous features:** `grid_load_mw`, `vehicles_charged`, `energy_dispensed_kwh`, `renewable_energy_used_percent`
  * **categorical features:** `station_type`, `peak_load_risk`, `city_zone`

dataset link : [https://drive.google.com/file/d/1omnwPCLssixBI2G0kjrFRZrmjUGBAWbA/view?usp=sharing]

### installation and execution

follow these bash commands exactly to get your local environment running.

step 1. clone the repository and navigate into the project directory
```bash
git clone https://github.com/kausikragavs/EVQueueForecaster-
cd EVQueueForecaster
```

step 2. create a virtual environment (highly advised so you do not break your global packages)
```bash
python -m venv venv
```

step 3. activate the virtual environment
on windows:
```bash
cd venv/Scripts
./Activate.ps1
```
on macos and linux:
```bash
cd venv/bin
source ./activate
```

step 4. install project dependencies from the requirements file
```bash
pip install -r requirements.txt
```

once your environment is active, launch jupyter notebook, open the `.ipynb` file, and start debugging the cells.
