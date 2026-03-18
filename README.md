# EY_AI_-_Data_Challenge

Using a combination of satellite imagery, weather, and ground-level environmental datasets, challenge registrants will develop AI models to forecast water quality based on key parameters (alkalinity, salinity, phosphorous) for rivers in South Africa.

## Project Structure

- **`Benchmark/`**: Contains the original methodology and datasets of the data challenge for the hackathon. 
- **`index.ipynb`**: The main modeling notebook. It loads the customized datasets (`Comprehensive_Training_Dataset.csv` and `Comprehensive_Validation_Dataset.csv`) and uses XGBoost to train models predicting the target water quality parameters. Includes detailed feature evaluation and validation steps.
- **`data_transformation.ipynb`**: Documents the data extraction strategy using Google Earth Engine (GEE). It aims to solve the lack of depth in the benchmark data by extracting spectral bands (Landsat/MODIS), weather/climate variables (CHIRPS precipitation, ERA5 temperature/humidity), topography, soil composition, and surrounding population density. 
  *(Note: Due to performance and reliability issues within the notebook environment, the final data extraction was scripted directly on the GEE JavaScript Code Editor platform. This notebook serves to showcase the similar conceptual approach and logic used.)*
- **`xgboost.ipynb`**: Contains additional experimentation and modeling iterations using XGBoost.
- **Datasets & Visualizations**: The root directory contains the augmented datasets (`*.csv`) used for improved modeling, as well as generated visualizations (`*.png`) illustrating model predictions and feature importance.

## Methodology

### Data Extraction
The benchmark dataset was found to lack sufficient depth in driving features for accurate prediction. To address this, Google Earth Engine was utilized to engineer a comprehensive set of environmental factors. By adding satellite imagery data, climate metrics, and terrain information, the models were provided with significantly more context to make accurate forecasts.

### Modeling
The final approach utilizes XGBoost (in `index.ipynb`) to predict the three target variables: Dissolved Reactive Phosphorus, Electrical Conductance, and Total Alkalinity. Model performance was optimized through evaluating different feature configurations from the expanded environmental dataset.
