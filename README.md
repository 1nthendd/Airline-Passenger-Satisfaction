# Airline Passenger Satisfaction Prediction

An ML project focused on analyzing airline passenger data and predicting customer satisfaction with their flight.

## Dataset

The project uses the **Airline Passenger Satisfaction** dataset from Kaggle.

| Split | Number of Rows |
|---|---:|
| Train | 103,904 |
| Test | 25,976 |

The dataset contains passenger demographics, travel information, flight distances, delays, and ratings of various airline services, including Wi-Fi, food, seat comfort, and onboard service.

## Work Performed

1. Loaded and inspected the training and test datasets.
2. Cleaned the data by removing unnecessary columns (`Unnamed: 0`, `id`) and handling missing values in `Arrival Delay in Minutes`.
3. Performed EDA using Matplotlib and Seaborn to explore feature distributions, correlations, and relationships with passenger satisfaction.
4. Encoded categorical features using `LabelEncoder`.
5. Trained and compared four classification models:
   - Decision Tree
   - Random Forest
   - K-Nearest Neighbors (KNN)
   - Logistic Regression
6. Repeated the model comparison using a reduced set of eight features, excluding service ratings.

## Results

### All Features

| Model | Accuracy | F1-score |
|---|---:|---:|
| Random Forest | **0.9631** | **0.9675** |
| Decision Tree | 0.9460 | 0.9522 |
| Logistic Regression | 0.8710 | 0.8868 |
| KNN | 0.7458 | 0.7911 |

The best performance was achieved by **Random Forest**, with 96.31% accuracy and a 96.75% F1-score.

### Reduced Feature Set

The second experiment used only eight features: `Gender`, `Age`, `Customer Type`, `Type of Travel`, `Class`, `Flight Distance`, `Departure Delay in Minutes`, and `Arrival Delay in Minutes`.

| Model | Accuracy |
|---|---:|
| Decision Tree | **0.7991** |
| Logistic Regression | 0.7771 |
| Random Forest | 0.7639 |
| KNN | 0.6666 |

The results suggest that service ratings provide significant predictive information in this experiment.

## Technologies Used

- Python
- Pandas, NumPy
- Matplotlib, Seaborn
- Scikit-learn
- Jupyter Notebook

## How to Run

1. Clone the repository.
2. Install the dependencies:

   ```bash
   pip install numpy pandas matplotlib seaborn scikit-learn jupyter
   ```

3. Download the [Airline Passenger Satisfaction dataset](https://www.kaggle.com/datasets/teejmahal20/airline-passenger-satisfaction).
4. Open `airline-passenger-satisfaction.ipynb` in Jupyter Notebook or Kaggle.
5. If running locally, update `TRAIN_PATH` and `TEST_PATH` in the notebook to match your CSV file locations.

## Notes

This is a baseline ML project. Potential improvements include consistent preprocessing between training and test sets, feature scaling for KNN and Logistic Regression, and additional evaluation metrics such as Precision, Recall, and Confusion Matrix.
