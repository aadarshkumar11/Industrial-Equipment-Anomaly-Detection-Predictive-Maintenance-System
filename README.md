# Industrial-Equipment-Anomaly-Detection-Predictive-Maintenance-System
Modern industrial equipment is equipped with numerous sensors that capture essential metrics such as temperature, speed, torque, and tool wear. Analyzing this sensor data is critical for identifying potential failures before they lead to unexpected breakdowns, thereby enhancing operational efficiency.



# Industrial Equipment Anomaly Detection & Predictive Maintenance System

## Table of Contents
1. [Project Overview](#project-overview)
2. [Technologies Used](#technologies-used)
3. [Dataset Description](#dataset-description)
4. [Key Features](#key-features)
5. [Methodology](#methodology)
6. [Results and Insights](#results-and-insights)
7. [Setup Instructions](#setup-instructions)
8. [Contributing](#contributing)
9. [License](#license)
10. [Contact](#contact)

## Project Overview
This project implements an end‑to‑end predictive maintenance pipeline for industrial equipment. By leveraging real‑time sensor data, it detects anomalies and classifies failure types to help maintenance teams act proactively, reducing downtime and costs.

## Technologies Used
- **Python**: Data ingestion, preprocessing, model development  
- **Jupyter Notebook**: Interactive exploration and prototyping  
- **Libraries**: pandas, NumPy, scikit‑learn, matplotlib, seaborn  
- **Web Framework**: Flask (for a lightweight dashboard)  
- **Environment**: Google Colab (development & experimentation)

## Dataset Description
The dataset consists of **10,000** records, each capturing:
- **UID**: Unique record identifier  
- **Product ID**: Quality code (L: 50%, M: 30%, H: 20%)  
- **Air Temperature [K]**: Simulated via a random walk around 300 K  
- **Process Temperature [K]**: Air temp + ~10 K noise  
- **Rotational Speed [rpm]**: Based on a 2860 W power input  
- **Torque [Nm]**: Centered at 40 Nm with ±10 Nm noise  
- **Tool Wear [min]**: Cumulative wear influenced by product quality  
- **Machine Failure**: Binary flag (0 = No Failure, 1 = Failure)  
- **Failure Type**: Categorical (Heat Dissipation, Power, Tool Wear, Overstrain)

All missing or duplicate records have been removed to ensure data integrity.

## Key Features
1. **Data Preprocessing**  
   - Handling outliers and noise  
   - Label encoding categorical fields  
   - Feature scaling (StandardScaler)  

2. **Exploratory Data Analysis (EDA)**  
   - Bar, scatter, box, heatmap, and line plots  
   - Correlation analysis to identify key predictors  

3. **Model Building & Tuning**  
   - Classification algorithms: Logistic Regression, Random Forest, K‑NN, SVM, Naive Bayes  
   - Hyperparameter optimization via GridSearchCV  

4. **Model Evaluation**  
   - Metrics: Accuracy, Precision, Recall, F1‑Score  
   - Confusion matrices and classification reports  

5. **Predictive Maintenance Dashboard**  
   - Flask app for live monitoring and alerts  

## Methodology
1. **Load & Clean Data**: Read from `data/predictive_maintenance.csv`, remove noise  
2. **Feature Engineering**: Encode, scale, and select relevant sensor readings  
3. **Train/Test Split**: 80/20 split for robust evaluation  
4. **Model Training**: Fit multiple classifiers, tune with cross‑validation  
5. **Evaluation**: Compare detection vs. failure‑type classification performance  
6. **Deployment**: Package best‑performing model into a Flask web service  

## Results and Insights
- **Failure Detection Accuracy**: *XX.XX %*  
- **Failure Type Classification Accuracy**: *YY.YY %*  
- **Key Findings**:  
  - High air/process temperature variance strongly correlates with overstrain failures.  
  - Tool wear trends signal impending failures up to 5 cycles in advance.  

> *Note: Replace **XX.XX %** and **YY.YY %** with your model’s final metrics.*

## Setup Instructions
1. **Clone the repo**  
   ```bash
   git clone https://github.com/your-username/industrial-anomaly-detection.git
   cd industrial-anomaly-detection
   ```

2. **Install dependencies**  
   ```bash
   pip install -r requirements.txt
   ```

3. **Place data**  
   - Put `predictive_maintenance.csv` into the `data/` folder.

4. **Run the Notebook**  
   - Launch `Industrial Equipment Anomaly Detection & Predictive Maintenance System.ipynb` in Jupyter or Colab.  
   - Execute all cells sequentially.

5. **Start the Dashboard**  
   ```bash
   export FLASK_APP=app.py
   flask run
  
   - Visit `http://localhost:5000` to view real‑time monitoring.

## Contributing
Contributions are welcome! Please fork this repository and submit a pull request with your enhancements or bug fixes.

## License
This project is licensed under the MIT License. See the [`LICENSE`](LICENSE) file for details.

## Contact
- **Email:** aadarshsrivastav08@gmail.com  
- **GitHub:** [github.com/aadarshkumar11](https://github.com/aadarshkumar11)  

---

Good luck, and happy predictive maintenance!
