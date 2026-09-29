# Plant Disease Detector

A simple deep learning project that helps detect plant diseases from leaf images.

The app lets a user upload an image through a web interface, and the model predicts whether the leaf is healthy or diseased, along with the plant type and confidence score.

## What this project does

- Classifies plant leaves into different disease categories
- Detects whether a leaf is healthy or unhealthy
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
- Dataset: New Plant Diseases Dataset
- Output classes: 38 plant disease/health categories

## Project structure

```text
plant-disease-detector/
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
└── requirements.txt (if added later)
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

1. Select an image of a leaf
2. Click Analyze Leaf
3. View the prediction result

## How the web app works

- The user uploads a plant image from the browser
- The Flask app receives the image
- The model processes the image and predicts the class
- The app returns:
  - plant name
  - disease status
  - confidence score

## API endpoint

You can also call the model directly through the Flask API:

```bash
curl -X POST -F "file=@plant_image.jpg" http://127.0.0.1:5000/predict
```

This returns a JSON result such as:

```json
{
  "plant": "potato",
  "disease": "early blight",
  "is_healthy": false,
  "probability": 0.98452
}
```

## Notes

This project is a practical application of computer vision and deep learning for agriculture. It can help farmers or researchers quickly identify disease symptoms from leaf images.

## Future improvements

- Add more plant species and diseases
- Improve accuracy with additional training data
- Add a better frontend design
- Deploy the app online
- Add image preprocessing improvements

