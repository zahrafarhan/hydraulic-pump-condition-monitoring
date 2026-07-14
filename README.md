**Hydraulic Pump Fault Detection Using Machine Learning, Personal Project**

Developed a Python machine learning project to classify hydraulic pump leakage using pressure, flow, temperature, vibration, and motor power sensor data. Built a data processing pipeline to extract statistical features from time series signals and compared Logistic Regression and Random Forest models. Achieved 99.77% test accuracy using Random Forest and evaluated performance using precision, recall, F1 score, confusion matrix, and feature importance analysis.

**Technologies:** Python, Pandas, NumPy, Scikit learn, Matplotlib, Google Colab, GitHub
# Hydraulic Pump Condition Monitoring

This project uses machine learning to detect hydraulic pump leakage from sensor data collected from a hydraulic test system.

The dataset contains pressure, flow, temperature, vibration, motor power, cooling efficiency, and system efficiency measurements. These signals are processed and used to classify the hydraulic pump condition.

## Project Goal

The goal of this project is to classify hydraulic pump leakage into three categories:

* No leakage
* Weak leakage
* Severe leakage

The project demonstrates how sensor data and machine learning can be used for condition monitoring and predictive maintenance.

## Dataset

The project uses the [Condition Monitoring of Hydraulic Systems dataset](https://www.kaggle.com/datasets/jjacostupa/condition-monitoring-of-hydraulic-systems) available on Kaggle.

Each operating cycle contains time series measurements collected from several sensors.

The sensors used in this project include:

* `PS1`, `PS2`, `PS3`: Pressure measurements
* `FS1`: Flow measurement
* `TS1`: Temperature measurement
* `VS1`: Vibration measurement
* `EPS1`: Motor power measurement
* `profile.txt`: Hydraulic component condition labels

The dataset is not included in this repository. It can be downloaded from Kaggle using the link above.

## Data Processing

The raw sensor files contain multiple measurements for each hydraulic operating cycle.

To prepare the signals for machine learning, statistical features were extracted from every cycle.

The extracted features include:

* Mean
* Standard deviation
* Minimum value
* Maximum value
* Signal range
* Root mean square value

These features summarise the behaviour of each sensor and reduce the size of the raw time series data.

The pump leakage condition stored in `profile.txt` was used as the target output.

## Machine Learning Models

Two classification models were trained and compared:

* Logistic Regression
* Random Forest Classifier

Logistic Regression was used as the baseline model.

Random Forest was used to capture nonlinear relationships between the sensor measurements and the pump leakage conditions.

## Model Results

The models were evaluated using a separate test dataset.

| Model               | Accuracy |
| ------------------- | -------: |
| Logistic Regression |   99.32% |
| Random Forest       |   99.77% |

The Random Forest classifier achieved the highest test accuracy of **99.77%**.

Logistic Regression also performed strongly, achieving an accuracy of **99.32%**.

The results suggest that the extracted statistical features contain useful information for distinguishing between the different pump leakage conditions.

## Model Evaluation

The models were evaluated using:

* Accuracy
* Precision
* Recall
* F1 score
* Classification report
* Confusion matrix

The confusion matrix was used to check how well the model classified each leakage category.

Because the model accuracy is very high, the input features and target labels were checked to make sure the target column was not included in the model inputs.

## Feature Importance

Feature importance from the Random Forest model was analysed to identify which sensor features contributed most strongly to the predictions.

This analysis helps answer questions such as:

* Which pressure measurements are most useful for detecting leakage?
* Does hydraulic flow provide useful fault information?
* Are vibration and motor power important for classification?
* Could the number of sensors be reduced without significantly lowering accuracy?

## Visualisations

The project includes the following visualisations:

* Pump leakage class distribution
* Pressure measurements for different pump conditions
* Flow measurements for different pump conditions
* Confusion matrix
* Model accuracy comparison
* Random Forest feature importance

## Project Structure

```text
hydraulic-pump-condition-monitoring/
│
├── hydraulic_condition_monitoring.ipynb
├── README.md
├── requirements.txt
└── results/
    ├── confusion_matrix.png
    ├── feature_importance.png
    └── model_comparison.png
```

The exact files may vary depending on which plots and outputs have been saved.

## Tools and Libraries

The project was developed using:

* Python
* Google Colab
* GitHub
* Pandas
* NumPy
* Matplotlib
* Scikit learn

## How to Run the Project

1. Download the [Condition Monitoring of Hydraulic Systems dataset](https://www.kaggle.com/datasets/jjacostupa/condition-monitoring-of-hydraulic-systems) from Kaggle.
2. Open the project notebook in Google Colab.
3. Upload the downloaded dataset ZIP file.
4. Extract the dataset into a folder called `hydraulic_data`.
5. Run each notebook cell in order.
6. Review the model accuracy, classification report, confusion matrix, and feature importance results.

## Project Workflow

The project follows these steps:

1. Upload and extract the hydraulic dataset.
2. Load the pressure, flow, temperature, vibration, and motor power signals.
3. Extract statistical features from each operating cycle.
4. Load the pump leakage condition labels.
5. Split the data into training and testing sets.
6. Train Logistic Regression and Random Forest models.
7. Compare the performance of both models.
8. Generate a classification report and confusion matrix.
9. Analyse feature importance.
10. Interpret the results from an engineering perspective.

## Limitations

The dataset was collected from a controlled hydraulic test rig.

Performance on a real industrial hydraulic system may be affected by:

* Different operating loads
* Sensor noise
* Pump design differences
* Temperature changes
* Component ageing
* Environmental conditions
* Different fault types

The high test accuracy should therefore not be assumed to represent performance on every real hydraulic system.

## Future Improvements

Possible future improvements include:

* Adding cross validation
* Comparing additional machine learning models
* Testing the model with fewer sensors
* Adding frequency domain features
* Analysing the complete time series signals
* Improving the visualisations
* Testing the model on real industrial data

## Conclusion

This project demonstrates how hydraulic sensor measurements can be processed and used for machine learning based condition monitoring.

Both models achieved strong classification performance. The Random Forest classifier produced the best result, with a test accuracy of **99.77%**.

The project combines data processing, sensor analysis, machine learning, model evaluation, and technical documentation.

