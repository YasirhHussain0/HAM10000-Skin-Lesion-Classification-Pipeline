# Skin Lesion Classification

A deep learning project for classifying skin lesions from medical images to support early detection and diagnosis.

The app lets a user upload an image through a web interface, and the model predicts the lesion type or condition along with a confidence score.

## What this project does

- Classifies skin lesions into different categories
- Detects suspicious or abnormal lesion patterns
- Uses a trained deep learning model for prediction
- Provides a user-friendly web interface for uploading images
- Exposes an API endpoint for predictions

## Technologies used

- Python
- PyTorch
- TorchVision
- Flask
- Pillow
- NumPy
- HTML/CSS/JavaScript

## Model and dataset

- Model: MobileNetV2 with transfer learning
- Dataset: Skin lesion image dataset
- Output classes: multiple lesion categories depending on training data

## Project structure

```text
skin-lesion-classification/
├── api.py
├── helpers.py
├── models.py
├── transforms.py
├── model_development.ipynb
├── test.ipynb
├── models/
│   ├── mobilenet_v2_model.pt
│   └── classes.pkl
├── templates/
│   └── index.html
├── README.md
└── requirements.txt
```

## How to run the project

### 1. Install dependencies

```bash
pip install torch torchvision flask pillow numpy
```

### 2. Start the app

```bash
python api.py
```

### 3. Open in browser

Go to:

```text
http://127.0.0.1:5000/
```

You will see a simple upload page where you can:

1. Select an image of a skin lesion
2. Click Analyze Lesion
3. View the prediction result

## How the web app works

- The user uploads a skin lesion image from the browser
- The Flask app receives the image
- The model processes the image and predicts the class
- The app returns:
  - lesion label
  - classification result
  - confidence score

## API endpoint

You can also call the model directly through the Flask API:

```bash
curl -X POST -F "file=@lesion_image.jpg" http://127.0.0.1:5000/predict
```

This returns a JSON result such as:

```json
{
  "label": "melanoma",
  "is_healthy": false,
  "probability": 0.98452
}
```

## Notes

This project is a practical application of computer vision and deep learning for medical image analysis. It can help clinicians or researchers quickly identify suspicious skin lesion patterns.

## Future improvements

- Add more lesion categories and datasets
- Improve accuracy with additional training data
- Add a better frontend design
- Deploy the app online
- Add image preprocessing and augmentation improvements

