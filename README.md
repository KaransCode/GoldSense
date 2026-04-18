# GoldSense: AI-Powered Gold Price Prediction 📈

GoldSense is an advanced Streamlit dashboard designed to track, forecast, and analyze gold market trends. Built for precision and modern usability, it seamlessly merges historical market data, real-time fetching capabilities, deep learning (LSTM) price forecasting, and natural language processing (NLP) to perform live news sentiment analysis.

## 🌟 Key Features

*   **Real-Time Data Extraction**: Pulls live gold spot prices and current USD-to-INR exchange rates transparently utilizing Yahoo Finance (`yfinance`) APIs.
*   **Deep Learning Price Forecasting**: Uses a pre-trained robust LSTM (Long Short-Term Memory) neural network to analyze historical trajectory and project future price action.
*   **Financial News Sentiment**: Leverages Hugging Face's `ProsusAI/finbert` to calculate live "Fear vs. Greed" market sentiment scores based on recent headlines and news.
*   **AI Trading Signals**: Programmatically generates automated Buy/Hold/Sell indicators by analyzing short-term technical crossovers and deviations.
*   **Dynamic Localization**: Instantly switch between 1 Gram and 10 Gram price calculations, toggle between 24K and 22K purities, and view data accurately converted to either USD or INR.
*   **Interactive Visualizations**: Clean, responsive UI with highly customizable Plotly data visualizations.

---

## 🛠️ Technology Stack

*   **Frontend UI:** Streamlit
*   **Data Processing:** Pandas, NumPy
*   **Machine Learning (Forecasting):** TensorFlow (Keras), scikit-learn
*   **NLP & Sentiment Analysis:** PyTorch, Transformers (Hugging Face)
*   **Data Retrieval:** `yfinance`, Requests
*   **Visualizations:** Plotly, Matplotlib, Seaborn

---

## 📂 Project Structure

```text
GoldSense/
│
├── app.py                      # Core Streamlit application
├── requirements.txt            # Dependency configuration (Optimized for deployment)
├── goldsense_processed.csv     # Cleaned historic dataset
│
├── model/                      # Machine Learning Assets
│   ├── lstm_model.keras        # Trained LSTM weights and architecture
│   └── scaler.pkl              # MinMax scaler object
│
└── utils/                      # Modular Python handlers
    ├── data_loader.py          # Yahoo Finance & Live FX data retrieval
    ├── predictor.py            # AI Inference & scaling 
    ├── sentiment.py            # FinBERT NLP sentiment logic
    ├── metrics.py              # Statistical metric calculations
    └── signals.py              # Buy/Sell algorithmic indicators
```

---

## 🚀 Local Installation & Usage

1. **Clone the project**
   ```bash
   git clone https://github.com/your-username/GoldSense-AI.git
   cd GoldSense-AI
   ```

2. **Create a Virtual Environment**
   ```bash
   python -m venv venv
   # Windows:
   venv\Scripts\activate
   # macOS/Linux:
   source venv/bin/activate
   ```

3. **Install Dependencies**  
   _Note: The requirements file specifically uses `tensorflow-cpu` and CPU architectures to allow for fast, lightweight deployment on free cloud servers._
   ```bash
   pip install -r requirements.txt
   ```

4. **Run the Dashboard**
   ```bash
   streamlit run app.py
   ```
   The interactive dashboard will automatically open in your default browser at `http://localhost:8501`.

---

## ☁️ Deployment

GoldSense can be deployed instantly using **Streamlit Community Cloud**:
1. Push this repository to GitHub.
2. Sign in to [share.streamlit.io](https://share.streamlit.io).
3. Connect your GitHub, select the repository, and set the entrypoint to `app.py`.
4. Streamlit will install the CPU-optimized requirements and host your AI dashboard for free.
