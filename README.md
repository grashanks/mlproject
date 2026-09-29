# End-to-end Student Performance Prediction

[![Ask DeepWiki](https://devin.ai/assets/askdeepwiki.png)](https://deepwiki.com/grashanks/mlproject.git)

This repository contains an end-to-end machine learning project designed to predict student performance in math exams based on various demographic and academic factors. The project covers the entire machine learning lifecycle, from data ingestion and exploratory data analysis to model training and deployment as a web application.

## Project Overview

The primary goal is to predict a student's math score based on features such as gender, race/ethnicity, parental level of education, lunch type, and whether they completed a test preparation course. The project is structured as a modular and scalable application.

## Features

- **Data Ingestion**: Reads the source data, splits it into training and testing sets, and stores them as artifacts.
- **Data Transformation**: A preprocessing pipeline handles categorical and numerical features, applying One-Hot Encoding and Standard Scaling.
- **Model Training**: Evaluates multiple regression algorithms (including Linear Regression, Random Forest, Gradient Boosting, XGBoost, and CatBoost) to find the best-performing model.
- **Prediction Pipeline**: A streamlined pipeline to make predictions on new, unseen data.
- **Web Application**: A simple Flask application provides a user interface to input student details and receive a predicted math score.
- **Experimentation Notebooks**: Jupyter notebooks for exploratory data analysis (EDA) and initial model development.

## Project Structure

```
.
├── artifacts/              # Stores output files like datasets, models, preprocessors
├── notebook/               # Jupyter notebooks for EDA and experimentation
├── src/                    # Source code for the ML application
│   ├── components/         # Modules for different ML pipeline stages
│   │   ├── data_ingestion.py
│   │   ├── data_transformation.py
│   │   └── model_trainer.py
│   ├── pipeline/           # Pipelines for training and prediction
│   │   ├── predict_pipeline.py
│   │   └── train_pipeline.py
│   ├── exception.py        # Custom exception handling
│   ├── logger.py           # Logging configuration
│   └── utils.py            # Utility functions (e.g., save/load objects)
├── templates/              # HTML templates for the Flask web app
├── app.py                  # Main Flask application file
├── requirements.txt        # Project dependencies
└── setup.py                # Setup script for making the project a package
```

## How to Run

Follow these steps to set up and run the project locally.

### 1. Clone the Repository

```bash
git clone https://github.com/grashanks/mlproject.git
cd mlproject
```

### 2. Install Dependencies

It is recommended to use a virtual environment.

```bash
# Create a virtual environment (optional)
python -m venv venv
source venv/bin/activate  # On Windows, use `venv\Scripts\activate`

# Install the required packages
pip install -r requirements.txt
```

### 3. Run the Training Pipeline

This will perform data ingestion, transformation, and model training, saving the necessary artifacts (`model.pkl`, `preprocessor.pkl`).

```bash
python src/components/data_ingestion.py
```

### 4. Run the Web Application

Start the Flask server to use the prediction interface.

```bash
python app.py
```

Open your web browser and navigate to `http://127.0.0.1:5000`. You will be redirected to the prediction page where you can input student data to get a math score prediction.

## Technologies Used

- **Python**: The core programming language.
- **Pandas & NumPy**: For data manipulation and numerical operations.
- **Scikit-learn**: For data preprocessing and building machine learning models.
- **CatBoost & XGBoost**: For advanced gradient boosting models.
- **Flask**: For creating the web application.
- **Matplotlib & Seaborn**: For data visualization in the notebooks.
