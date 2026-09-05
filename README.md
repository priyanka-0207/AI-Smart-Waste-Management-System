# Smart Waste Management & Recycling System

**Status:** Completed

## Purpose

An AI waste-management system that classifies waste into 9 categories with a deep-learning image model, serves predictions through a Flask API, and maps each category to a recycling or biofuel pathway. Part of a larger team project spanning collection, classification, and recycling; this repository covers the machine-learning and backend work.

## Methods Used

* Transfer learning for image classification (MobileNetV2)
* Data augmentation and preprocessing
* Model serving via REST API
* Category-to-recycling/biofuel mapping

## Technologies

* Machine Learning: TensorFlow / Keras, scikit-learn
* Backend: Flask, Python
* Frontend: React, HTML, CSS, JavaScript
* Data processing: pandas, NumPy
* Model serialization: Pickle, H5

## Required Libraries

* tensorflow / keras
* scikit-learn
* flask
* pandas
* numpy
* (see `requirements.txt`)

## Project Description

### Overview

The system covers end-to-end waste collection, classification, and recycling:

1. **Smart waste collection** - optimizing collection routes based on demand.
2. **AI-powered segregation** - deep-learning image classification into 9 categories: Cardboard, Food Organics, Glass, Metal, Miscellaneous Trash, Paper, Plastic, Textile Trash, Vegetation.
3. **Recycling & biofuel generation** - processing classified waste into biogas, bioethanol, compost, bio-oil, syngas, and recyclable materials.
4. **Future scope** - integration with IoT sensors for real-time waste tracking.

### My contributions (ML & backend)

* Built and trained a CNN (MobileNetV2) for waste classification using transfer learning.
* Created the data-preprocessing pipeline: augmentation (rotation, flipping, zooming) and label encoding.
* Developed the training notebook for model training, evaluation, and tuning.
* Implemented Flask API endpoints for model serving and real-time predictions.
* Designed the categorical label-encoding system (`label_encoder.pkl`).
* Serialized and deployed the trained model for production use.

### Technical details

**Model architecture**

* Backbone: MobileNetV2 for efficient image classification.
* Approach: transfer learning from ImageNet pre-trained weights.
* Loss: categorical cross-entropy for multi-class classification.
* Optimizer: Adam with learning-rate scheduling.
* Augmentation: rotation, flipping, zooming, brightness adjustment.

**Classification pipeline**

1. Data collection - multi-category waste image dataset.
2. Preprocessing - normalization, resizing, augmentation.
3. Training - CNN with transfer learning on pre-trained weights.
4. Evaluation - accuracy, precision, recall, F1-score.
5. Deployment - model serialization for API serving.

**Biofuel generation mapping**

* Paper & Cardboard → biogas & bioethanol
* Plastic → bio-oil & syngas (via pyrolysis)
* Food waste → biogas & compost (via fermentation)
* Glass & Metal → direct recycling

### Key features

* Deep-learning-based waste classification into 9 categories
* Recycling recommendation per category
* Biofuel generation mapping
* Flask API for model serving
* React frontend for user interaction

## Repository Structure

```
.
├── client/                              # Frontend (React/HTML/CSS/JS)
├── server/                              # Backend (Flask)
├── .gitignore
├── LICENSE                              # MIT License
├── Model training and processing.ipynb  # ML training notebook
├── README.md
├── app.py                               # Main Flask application
├── label_encoder.pkl                    # Categorical label encoder
├── requirements.txt                     # Python dependencies
└── waste_cnn_model.h5                   # Trained CNN model
```

## To Use

### Clone the repository

```bash
git clone https://github.com/priyanka-0207/AI-Smart-Waste-Management-System.git
cd AI-Smart-Waste-Management-System
```

### Install dependencies

```bash
pip install -r requirements.txt
```

### Train the model (optional - a trained model is included)

```bash
python -m jupyter notebook "Model training and processing.ipynb"
```

### Start the Flask API

```bash
python app.py
```

### Launch the frontend

```bash
cd client
npm install
npm start
```

## Future Enhancements

* IoT integration - smart sensors for real-time bin monitoring
* Route optimization - AI-driven collection scheduling
* Expanded, more granular waste categories
* Mobile app - native iOS/Android
* Analytics dashboard - waste-management metrics

## License

Open-source under the MIT License. See the `LICENSE` file.

## Author

Priyanka Bhutada - Machine Learning & backend (waste-classification model, preprocessing pipeline, Flask API). Part of a team project.
