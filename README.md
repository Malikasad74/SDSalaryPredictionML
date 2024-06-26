## Project Description: Software Developer Salary Prediction

The Software Developer Salary Prediction project utilizes machine learning techniques to predict the salaries of software developers based on various factors such as country, education level, and years of professional coding experience. This project aims to provide insights into how these variables influence salary expectations in the tech industry.

## README.md

# Software Developer Salary Prediction

## Project Overview

This project leverages machine learning algorithms to predict the salaries of software developers. By analyzing data from the Stack Overflow Developer Survey, the project aims to identify key factors influencing salary variations and provide accurate salary predictions based on these factors.

## Dataset

The dataset used for this project is the Stack Overflow Developer Survey data, which includes various features such as:
- Country
- Education Level
- Years of Professional Coding Experience
- Employment Status
- Salary

## Data Preprocessing

1. **Data Cleaning**: Handling missing values and filtering out irrelevant data.
2. **Feature Engineering**: Transforming categorical data into numerical formats.
3. **Normalization**: Standardizing numerical features for better model performance.

## Models Used

- **Linear Regression**
- **Decision Tree Regressor**
- **Random Forest Regressor**

## Evaluation Metrics

- **Root Mean Squared Error (RMSE)**
- **Mean Absolute Error (MAE)**

## Key Findings

- The Decision Tree Regressor provided the best performance with an RMSE of approximately $30,428.51.
- The models were trained and evaluated to understand the impact of different features on salary predictions.

## How to Use

1. **Clone the Repository**:
    ```bash
    git clone https://github.com/yourusername/software-developer-salary-prediction.git
    cd software-developer-salary-prediction
    ```

2. **Install Dependencies**:
    ```bash
    pip install -r requirements.txt
    ```

3. **Run the Model**:
    ```python
    python predict_salary.py
    ```

4. **Load the Model**:
    ```python
    import pickle

    with open('saved_steps.pkl', 'rb') as file:
        data = pickle.load(file)

    regressor_loaded = data["model"]
    le_country = data["le_country"]
    le_education = data["le_education"]
    ```

5. **Make Predictions**:
    ```python
    X = np.array([["United States", 'Master’s degree', 15]])
    X[:, 0] = le_country.transform(X[:,0])
    X[:, 1] = le_education.transform(X[:,1])
    X = X.astype(float)
    y_pred = regressor_loaded.predict(X)
    print(f"Predicted Salary: ${y_pred[0]:,.2f}")
    ```

## Conclusion

The Software Developer Salary Prediction project demonstrates the application of machine learning techniques to real-world data, providing valuable insights into salary determinants in the software development industry.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Acknowledgements

- Stack Overflow for the dataset.
- Scikit-Learn for the machine learning library.
- Matplotlib for data visualization.

For any questions or collaboration requests, please contact Asad Malik at asadmalik1011@gmail.com.
