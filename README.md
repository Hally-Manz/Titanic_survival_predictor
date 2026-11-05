# Titanic Survival Predictor 🚢

**A web-based Streamlit application that predicts Titanic passenger survival using a trained Random Forest machine learning model.** 

This interactive tool allows users to input custom passenger demographics—such as age, class, sex, and fare—and instantly outputs both the survival prediction and its associated probability.

🔗 **Live Demo:** [hally-titanic-predictor.streamlit.app](https://streamlit.app)

## 🚀 Features
* **Machine Learning Backend:** Uses a trained Random Forest model (`forest_model.joblib`) for predictions.
* **Cached Model Loading:** Optimizes performance by using Streamlit's `@st.cache_resource` to load the model only once.
* **Interactive UI:** Dynamic forms complete with text inputs, radio buttons, sliders, and structured columns.
* **Visual Status Feedback:** Clear, color-coded custom success or error notifications based on the result.

## 📁 Repository Structure
```text
├── models/
│   └── forest_model.joblib  # Trained Random Forest model
├── app.py                   # Streamlit application source code
└── README.md                # Project documentation
```

## 🛠️ Installation & Setup

Follow these steps to run the application locally:

### 1. Clone the Repository
```bash
git clone https://github.com
cd your-repo-name
```

### 2. Set Up a Virtual Environment (Recommended)
```bash
python -m venv venv
source venv/bin/activate  # On Windows use: venv\Scripts\activate
```

### 3. Install Dependencies
Make sure you have the required packages installed:
```bash
pip install streamlit pandas joblib scikit-learn
```

### 4. Run the App
Launch the Streamlit server from your terminal:
```bash
streamlit run app.py
```

## 📊 How It Works
1. **Inputs:** The user enters the passenger's Name, Passenger Class (1st, 2nd, or 3rd), Sex (Encoded as `0` for Male, `1` for Female), Age, Companion count (Siblings/Spouses/Parents/Children), and Fare paid.
2. **Data Pipeline:** The inputs are packed into a Pandas DataFrame to mirror the schema required by the model.
3. **Inference:** The cached Random Forest model calculates the prediction (`0` for deceased, `1` for survived) alongside the class probabilities.
4. **Display:** The UI reveals a personalized message with the precise percentage probability of the outcome.
