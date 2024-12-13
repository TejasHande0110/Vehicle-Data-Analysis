# Vehicle Dataset Analysis

## 1. Data Loading and Cleaning
The dataset contained approximately 18,500 entries and 141 columns. The column `uniqueid` was used as the vehicle identifier. and data was collected from 2 March 2024 to 20 April 2024.

### Data Cleaning Steps:
1. **Removed Empty Columns:** Created a separate dataframe excluding entirely empty columns to preserve the original data.
3. **Date Format:** Time-stamp was in unix-format so converted it into "dd-mm-yyyy" format.
2. **Handled Missing Values:** Used KNNImputer to fill in missing values.
3. **Outlier Removal:** Bound outliers to the 25th and 75th percentiles.
3. **Duplicate:** There were no duplicated in the data.

## 2. Exploratory Data Analysis
### Observations and Findings

#### High Correlations:
- **Engine Load and Engine Torque Percent:** High correlation indicating they are closely related to engine performance.
- **RPM and Vehicle Speed:** Moderate to strong positive correlation, as higher RPM usually means higher speed.
- **Fuel Consumption with Engine Load or Torque:** Strong positive correlation, as fuel consumption increases with engine load and torque.

#### Negative Correlations:
- **Fuel Economy with Engine Load or RPM:** Higher engine load and RPM negatively affect fuel economy.
- **Accelerator Pedal Position and Fuel Economy:** Harder pedal press decreases fuel economy.

#### Zero or Undefined Correlations:
- **Engine Oil Temp, Engine Fuel Temp, and Vibration Status:** May have no significant correlation with other variables due to constant values.

#### Low or No Correlations:
- **Latitude and Longitude vs. Performance Metrics:** GPS coordinates may not show strong correlations with performance-related data.

### Analysis Visualizations:
1. **Correlation Matrix:** Generated to understand relationships between variables.
2. **Heatmap:** Plotted to visually represent the correlation matrix.
3. **Scatter Plots:** Used to validate findings from the correlation matrix.
4. **Box Plots:** Identified outliers in the data.

## 3. Feature Engineering
### New Features Created:
1. **Distance:** Calculated from latitude and longitude readings.
2. **Low AdBlue Level:** Indicator of AdBlue levels.
3. **Over-Speeding:** Instances of speeding beyond a set threshold.
4. **Low Fuel Level:** Indicator of low fuel levels.

## 4. Deriving Insights and Generating Report

### Vehicle Statistics
- **Sample Report**
- **Vehicle ID:** it_220403501
- **Distance Travelled:** 170,095.48 km
- **Fuel Consumed:** 3,123.5 liters
- **Run-Time:** 316.25 hrs
- **Average Distance Travelled Per Unit:** 54.46 km
- **Average AdBlue Level:** 78.36
- **Average Coolant Temperature:** 85.47
- **Average Speed:** 33.36 units
- **Number of time Vehicle is Parked**: 1627

### Warnings
- **Over-Speeding Instances:** 318 times
- **Low Fuel Levels:** 2,106 times
- **Low AdBlue Levels:** 148 times
