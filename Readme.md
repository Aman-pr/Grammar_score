# Grammar Scoring Engine

A machine learning model that analyzes spoken audio to predict grammar quality using acoustic features (MFCCs, Spectral Contrast, ZCR) and provides real-time feedback through an interactive web interface.


## Features

### Audio Analysis
- Extracts 20+ acoustic features including:
  - MFCCs (Mel-frequency cepstral coefficients)
  - Spectral Contrast
  - Zero Crossing Rate (ZCR)

### Machine Learning
- Random Forest Regressor trained on speech patterns

### Real-time Feedback
- Instant grammar score prediction (0.0–1.0 scale)

### Visual Analytics
- Interactive waveform display
- MFCC heatmap visualization
- Option to download full CSV report

### File Support
- Processes WAV and MP3 audio formats

## Tech Stack

### Core Technologies
- **Librosa** - Audio feature extraction
- **scikit-learn** - Machine Learning pipeline
- **Streamlit** - Web interface
- **NumPy / Pandas** - Data processing

### Supporting Libraries
- **Matplotlib** - Visualizations
- **Joblib** - Model persistence
- **LanguageTool-Python** - Grammar validation

## Dataset

- Based on Mozilla's Common Voice dataset (Kaggle version)
- Annotated with speaker metadata and text transcripts
- Curated subset: 25,403 voice recordings (`cv-invalid.csv`)
- Features include:
  - Audio files (MP3 format)
  - Text transcripts
  - Speaker metadata (age, gender, accent)
- Source: [Common Voice on Kaggle](https://www.kaggle.com/mozillaorg/common-voice)
- The full Common Voice dataset contains over 2.5 million recordings (see [official site](https://commonvoice.mozilla.org/))

## How to Run the Project

### 1. Clone the Repository
```bash
git clone https://github.com/your-username/grammar-scoring-engine.git
cd grammar-scoring-engine
```

### 2. Create a Virtual Environment (Recommended)
```bash
python -m venv venv
source venv/bin/activate    # On Linux/Mac
venv\Scripts\activate       # On Windows
```

### 3. Install Dependencies
```bash
pip install -r requirements.txt
```

### 4. Download Dataset (Optional)

If you want to retrain or test with your own data:
- Download Mozilla Common Voice dataset from [Kaggle](https://www.kaggle.com/mozillaorg/common-voice)
- Place the audio files and metadata CSV in the `data/` folder

### 5. Run the Web Application
```bash
streamlit run app.py
```

Once it starts, open the local URL shown in your terminal (usually `http://localhost:8501`).

## Directory Structure
```
grammar-scoring-engine/
│
├── app.py                    # Streamlit web interface
├── model/                    # Trained ML model (.joblib)
├── data/                     # Dataset and sample audio
├── features/                 # Extracted MFCCs and other features
├── requirements.txt          # Python dependencies
├── utils.py                  # Helper functions for audio & scoring
└── README.md                 # Project documentation
```

## Acknowledgments

- **Mozilla Common Voice Team** – for providing the speech dataset
- **Librosa Community** – for powerful audio processing tools
- **Streamlit** – for an intuitive, interactive web framework

---

**License:** MIT

**Contributions:** Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.
