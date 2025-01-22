# Predictive Analysis for UK Road Accident Data (2020)

## Overview
This project conducts a comprehensive analysis of the **UK road accident data for the year 2020**. The primary goal is to provide actionable insights for policy-making to reduce the number of accidents and their severity. Using statistical and machine learning techniques, this project identifies patterns, determines key contributing factors, and builds predictive models to classify accidents based on severity.

## Dataset
The analysis utilizes four key tables extracted from the database:
- **Accident**: Contains accident-related information.
- **Vehicle**: Details about the vehicles involved.
- **Casualty**: Information about the casualties.
- **LSOA**: Geospatial data about accident locations.

The data was preprocessed, cleaned, and integrated into a unified format for analysis.

## Features
- **Outlier Analysis**: Detected and treated outliers using Grubb’s test.
- **Accident Analysis by Time and Day**:
  - Peak accident times: 8 AM to 8 PM, with a spike at 5 PM.
  - Fridays recorded the highest number of accidents, Sundays the least.
- **Motorcycle and Pedestrian Analysis**:
  - Motorbike accidents peaked during rush hours, with engine capacity influencing accident patterns.
  - Pedestrian accidents were most common between 3 PM and 5 PM on weekdays.
- **Clustering**:
  - K-Means clustering identified accident hotspots in **Kingston upon Hull**.
  - Visualized clusters on a map using the `folium` package.
- **Association Rule Mining**: Leveraged the Apriori algorithm to uncover significant patterns contributing to accident severity.

## Predictive Modeling
### Models Implemented:
1. **Decision Tree Classifier**:
   - Accuracy: 74.03%
   - Strengths: Balanced precision and recall.
   - Weaknesses: Risk of overfitting.
2. **K-Neighbors Classifier**:
   - Accuracy: 66.05%
   - Strengths: Slightly better at identifying fatal cases.
   - Weaknesses: Lower precision.
3. **Random Forest Classifier**:
   - Accuracy: 83.37%
   - Strengths: High accuracy and recall for fatalities.
   - Weaknesses: Complexity.
4. **Gaussian Naive Bayes Classifier**:
   - Accuracy: 54.47%
   - Strengths: High recall for fatalities.
   - Weaknesses: Low precision.
5. **Stacked Ensemble Model**:
   - Combined predictions of all models using Logistic Regression.
   - Improved overall stability and robustness.

## Installation
1. Clone the repository:
   ```bash
   git clone https://github.com/your-username/uk-road-accident-analysis.git
   cd uk-road-accident-analysis
   ```
2. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```
3. Set up the database and extract data:
   - Execute SQL queries to extract data from the provided schema.
   - Load the data into the `data/` directory.

## Usage
1. **Data Preprocessing**:
   ```bash
   python preprocess.py
   ```
2. **Run Analysis**:
   ```bash
   python analyze.py
   ```
3. **Train Models**:
   ```bash
   python train_models.py
   ```
4. **Visualize Results**:
   ```bash
   python visualize_clusters.py
   ```

## Results
- **Accident Trends**:
  - Peak times: 8 AM to 8 PM, especially at 5 PM.
  - Fridays had the most accidents, Sundays the least.
- **Predictive Modeling**:
  - Random Forest Classifier emerged as the best individual model.
  - Stacked ensemble showed improved stability and predictive performance.
- **Clustering**:
  - Identified three key accident clusters in Kingston upon Hull.

## Applications
- **Policy Recommendations**:
  - Increase traffic regulation during peak hours.
  - Implement awareness campaigns for motorbike safety.
  - Improve pedestrian infrastructure near schools.
- **Proactive Safety Measures**:
  - Use predictive models to forecast potential accident hotspots.

## Future Work
- Enhance clustering analysis with additional geospatial features.
- Explore more advanced ensemble techniques.
- Incorporate real-time data for dynamic modeling.

## License
This project is licensed under the MIT License. See the LICENSE file for details.
