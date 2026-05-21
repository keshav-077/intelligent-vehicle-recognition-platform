# OCR Text Recognition System

This is a web application for detecting license plates and extracting text using Optical Character Recognition (OCR) technology. The application is built using Python, OpenCV, Tensorflow, YOLOv5, Pytesseract, and InceptionResNetV2.

## Running the Web App

There are two versions of this web app - one using Streamlit and another using Flask framework.

The Flask app runs both InceptionResNetV2 and YOLOv5 models, while the Streamlit app currently only runs the YOLOv5 model.

### Setup Instructions

1. Install the required dependencies
    ```
    pip install -r requirements.txt
    ```

2. To run the Streamlit app, navigate to the root directory and run:
    ```
    streamlit run app.py
    ```
    Access the application at http://localhost:8501

3. To run the Flask app, navigate to the app folder and run:
    ```
    python main.py
    ```
    Access the application at http://localhost:5000

4. Upload an image and select the desired model for object detection and text extraction.

## Project Details

### Dataset
The dataset contains 462 images of cars with license plates. The images were annotated using LabelImg and Pascal VOC format. The annotations were converted to CSV format and then to YOLOv5 format for training.

### InceptionResNetV2 Model
The InceptionResNetV2 model was trained for 200 epochs using transfer learning. A pre-trained Inception-ResNet V2 model was used as the base, with custom classification layers added on top. The model was compiled with mean squared error loss and Adam optimizer. The best model was saved based on validation loss.

### YOLOv5 Model
The YOLOv5 model was trained for 100 epochs using pre-trained weights. The model was trained on GPU and the best weights were saved. The model was also exported to ONNX format for deployment.

## Features

- Upload images for license plate detection
- Choose between InceptionResNetV2 and YOLOv5 models
- Extract text from detected license plates using OCR
- View original and processed images side by side
- Display cropped license plate regions with extracted text

## Technologies Used

- Python
- OpenCV
- TensorFlow
- PyTesseract
- Flask
- Streamlit
- YOLOv5
- InceptionResNetV2
