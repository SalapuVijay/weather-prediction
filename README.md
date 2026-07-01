# ⛈️ Rainfall Prediction System (Weather Oracle)

An end-to-end Machine Learning and full-stack web application designed to predict the occurrence and intensity of rainfall tomorrow across 20 major USA cities. The system leverages a **Decision Tree Classifier (achieving 98% accuracy)**, a **Flask REST API** backend, and an **interactive HTML5 Canvas** frontend featuring real-time physics-based weather animations (rain, clouds, lightning, and stars). 🌪️🔮

---

## 🚀 Live Demo & Repository

- 💻 **Frontend Web App**: [https://weather-24-7.onrender.com](https://weather-24-7.onrender.com) *(Static hosting)*
- 📦 **GitHub Repository**: [SalapuVijay/weather-prediction](https://github.com/SalapuVijay/weather-prediction.git)

---

## ✨ Features

- 🤖 **Predictive Machine Learning Model**: A Decision Tree Classifier trained on a 70,000+ row meteorological dataset, analyzing features like `humidity`, `wind_speed`, `precipitation`, and `location` to classify if it will rain tomorrow.
- 📡 **Flask REST API Backend**: Receives atmospheric parameters, applies fitted features scaling (`scaler_all_locations.pkl`), runs predictions using the serialized model, and returns the classification confidence.
- 🌤️ **Layered Canvas Animations**:
  - Twinkling stars particle system for storm/night states.
  - Fluffy drifting cloud animations with dynamic wind speeds.
  - Directional rain particle physics simulation governed by rainfall severity.
  - Procedural lightning bolts and full-screen screen flashes triggered under high probability (storm mode).
- 🧮 **Atmospheric Form Inputs**: Input fields for Humidity (%), Wind Speed (km/h), Precipitation (mm), and a select dropdown of 20 major USA cities (New York, Los Angeles, Chicago, etc.).

---

## 🛠️ Tech Stack & Technologies

### 📊 Data Science & Backend
- **Core Language**: Python 🐍
- **Machine Learning**: `scikit-learn`, `joblib`, `scipy` 🧮
- **Data Wrangling**: `pandas`, `numpy` 📊
- **Notebook Environment**: Jupyter Notebook (`.ipynb`)
- **API Server**: Flask & Flask-CORS (Port `5000`) 🚀

### 🎨 Frontend
- **Structure**: HTML5 📝
- **Styling**: CSS3 & Bootstrap 5 (imported via CDN) 🎨
- **Logic & Visuals**: Vanilla JavaScript (Canvas API, RequestAnimationFrame, custom particle physics loops) ⚡

---

## 🗂️ Project Structure

```
├── Rainfall-web/              # Interactive UI Web App
│   ├── index.html            # Main markup and canvas layers setup
│   ├── styles.css            # Styles, overlays, time-based gradients, and keyframes
│   └── script.js             # Canvas drawing cycles, physics loops, and fetch API calls
│
├── rainfall_eda_plots2/       # Data Science and Flask Backend
│   ├── app.py                # Flask API server (/predict)
│   ├── SummerProject2file.ipynb # Data exploration, model training, tuning, and evaluation
│   ├── final_decision_tree_model_all_locations.pkl # Trained serialized Decision Tree
│   ├── scaler_all_locations.pkl                    # Fitted features normalization scaler
│   ├── usa_rain_prediction_dataset_2024_2025.csv   # Raw meteorological dataset (70k+ rows)
│   └── *.png                 # Visual plots (correlation heatmaps, distributions, importance)
│
└── README.md
```

---

## ⚙️ How to Setup & Run Locally

### 1. Set Up the Backend API

1. Navigate to the backend folder:
   ```bash
   cd rainfall_eda_plots2
   ```
2. Install the Python dependencies:
   ```bash
   pip install flask flask-cors joblib numpy pandas scikit-learn
   ```
3. Start the Flask application:
   ```bash
   python app.py
   ```
   *The server will start running locally at `http://localhost:5000`.*

### 2. Set Up the Frontend Interface

1. Navigate to the frontend directory:
   ```bash
   cd ../Rainfall-web
   ```
2. Open **`index.html`** in any modern web browser.
3. Fill out the form values, hit submit, and watch the weather canvas animations morph dynamically from calm skies to rain or storm depending on the ML model's prediction!
