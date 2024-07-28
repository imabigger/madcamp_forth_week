### README for Bitcoin Prediction Model

# Bitcoin Prediction Model

Welcome to the Bitcoin Prediction Model repository! This project utilizes advanced machine learning techniques to predict Bitcoin prices based on various indicators and news articles.

## Table of Contents

1. [Project Overview](#project-overview)
2. [Data Collection](#data-collection)
3. [Modeling](#modeling)
4. [Results](#results)
5. [Challenges](#challenges)
6. [Usage](#usage)
7. [Contributors](#contributors)

## Project Overview

This project aims to predict Bitcoin prices by leveraging financial indicators and news articles. We employed two sophisticated models, Bi-GRU (Bidirectional Gated Recurrent Unit) and Bi-LSTM (Bidirectional Long Short-Term Memory), to capture the complex patterns in time-series data.

## Data Collection

### Indicators
- **Financial Indicators**: We used Bitcoin market data including open, close, high, low, and volume.
- **Enhanced Features**: We included RSI, MACD, gold trading volume, interest rates, and the S&P 500 index, resulting in a total of 40 features.

### News Articles
- **Source**: We collected news articles by searching "Bitcoin" on Naver from September 30, 2017, to May 23, 2023.
- **Quantity**: Approximately 140,060 articles were crawled and embedded using a Transformer-based time-series prediction model.

## Modeling

### News Article Modeling
- **Model**: A transformer-based model using a pre-trained BERT model specialized for financial terminology.
- **Challenges**: The influence of individual news articles on Bitcoin prices is uncertain, and preprocessing of articles led to gaps in the data.

### Indicator Data Modeling
- **Preprocessing**: Data augmentation, scaling (MinMax), and removal of missing values.
- **Model**: An RNN-based time-series prediction model was used.

### Final Model
- **Architecture**: Bi-GRU and Bi-LSTM models were employed, with their predictions combined using a weighted average based on validation loss.

## Results

### Model Performance
- **Train Loss**:
  - Bi-GRU: 0.000175
  - Bi-LSTM: 0.000209
- **Validation Loss**:
  - Bi-GRU: 0.000021
  - Bi-LSTM: 0.000061

### Back-testing
- **Period**: 2023
- **Initial Seed**: 1,000,000,000 KRW (10 billion KRW)
- **Final Cash**:
  - Bi-GRU: 1,875,465,368 KRW (87.5% profit)
  - Bi-LSTM: 1,191,535,690 KRW (11.9% profit)
  - Final Model: 2,054,507,142 KRW (105% profit)

## Challenges

Despite achieving significant results, the project faced several challenges:
1. **Modeling Errors**: Various errors in the modeling process were encountered and addressed.
2. **News Impact**: Quantifying the impact of news articles on Bitcoin prices proved to be difficult.
3. **Temporal Consistency**: Ensuring consistent influence of news over different time periods was challenging.

## Usage

I will try this model in real korea bitcoin market.

## Contributors

- **박종민**
- **이시준 (mac520@naver.com)**

---

For any questions or further information, please refer to the [documentation](docs/documentation.md) or contact the contributors.

---

This README was generated based on the project presentation and documentation provided by the contributors. For more detailed insights into the modeling process and results, please refer to the [MadCamp Week 4 Presentation](MadCamp_Week4_ppt.pdf).
