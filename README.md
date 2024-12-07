# 🍠 Potato Disease Classification

This project is a deep learning-based application for classifying potato diseases using Convolutional Neural Networks (CNN). The model can classify images into three categories: **Early Blight**, **Late Blight**, and **Healthy**. The model achieves over **95% accuracy** in each classification case. The backend is built using **FastAPI**, and the application is tested with **Postman** for API requests.

## 🧠 Model Overview
The project employs a **CNN** (Convolutional Neural Network) architecture to classify potato leaf diseases based on images. The model was trained on a labeled dataset of potato leaf images and saved as a `.keras` file. 

### Libraries Used:
- **TensorFlow / Keras**: For building and training the deep learning model.
- **FastAPI**: To create an API for model inference.
- **Postman**: For testing API endpoints.
- **Pillow**: For image preprocessing.
- **Numpy**: For handling numerical data.

## 🎯 Key Features:
- **Model Accuracy**: The CNN model achieves more than **95% accuracy** for predicting potato leaf diseases.
- **FastAPI Backend**: The API serves model predictions, making it accessible for real-world usage.
- **Postman Testing**: Easily test the API using Postman by sending image files to the `/predict` endpoint.

---

## 📂 Project Structure

The repository contains the following files and folders:
├── api/ 

FastAPI backend folder
│ ├── main.py 
FastAPI server for predictions
│ └── requirements.txt 
Python dependencies for running FastAPI 
├── model/ 
Contains the trained model
│ └── 1.keras 
Saved model in Keras format
├── training.ipynb 
Jupyter notebook for training the CNN model 
├── README.md 
Project documentation 
└── .gitignore 
Files to ignore in the repository

### Detailed Breakdown:
- **`api/main.py`**: This is the FastAPI backend file responsible for receiving image inputs, preprocessing them, and returning the predicted class and confidence score. It loads the saved Keras model from the `model/1.keras` file.
- **`model/1.keras`**: The trained CNN model file in Keras format, used for predictions.
- **`training.ipynb`**: A Jupyter notebook that contains the model training process, dataset loading, preprocessing steps, and model evaluation.

---

## 🚀 How to Run the Project

### Prerequisites

Ensure you have the following tools installed:
- Python 3.8 or above
- FastAPI
- TensorFlow/Keras
- Postman (for API testing)
- uvicorn (for running the FastAPI app)

You can install the required dependencies by running:

```pip install -r api/requirements.txt```
Running the FastAPI Backend
Clone the repository:



```git clone https://github.com/yourusername/potato-disease-classification.git```
Navigate to the api/ folder:


Copy code
```cd api```
Start the FastAPI server:


Copy code
```uvicorn main:app --reload```
The API will be available at http://localhost:8000.

## 📬 API Endpoints
1. /ping [GET]
Description: A simple health check to ensure the API is running.
Response: "Hello, I am alive"
2. /predict [POST]
Description: This endpoint accepts an image file and returns the predicted disease class and confidence score.
Request:
Form-data: file (an image file)
Response (JSON):
json
Copy code
```
{
  "class": "Late Blight",
  "confidence": 0.98
}
```
## 🧪 Testing the API with Postman
Open Postman and create a new POST request.
Use the URL: http://localhost:8000/predict.
In the "Body" tab, select "form-data" and add the key file, then upload a potato leaf image.
Send the request, and you'll receive a prediction like:
json
Copy code
```
{
  "class": "Early Blight",
  "confidence": 0.97
}
```
## 📊 Model Training and Evaluation
The model was trained using a CNN architecture in TensorFlow/Keras on a labeled dataset of potato leaf images. The dataset was split into training and validation sets, and various data augmentation techniques were applied to improve generalization.

Key metrics:

Training Accuracy: Over 95%
Validation Accuracy: Over 95%
You can explore the full training process in the training.ipynb file.

## 🛠️ Future Improvements
Add more classes for other diseases.
Deploy the API on a cloud service (e.g., AWS, Heroku).
Improve the model to handle more edge cases and noise in images.
