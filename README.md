# Twitter Sentiment Analysis

## Overview
This project aims to analyze and classify sentiments expressed in tweets as positive, neutral, or negative using a Long Short-Term Memory (LSTM) model. The dataset consists of various columns including tweet text, user information, and timestamps. The project involves extensive data preprocessing, exploratory data analysis, and building a machine learning model for sentiment classification.

## Table of Contents
- [Business Problem and Use Case Domain Understanding](#business-problem-and-use-case-domain-understanding)
- [Objective of the Project](#objective-of-the-project)
- [Data Collection](#data-collection)
- [Summary of the Data](#summary-of-the-data)
- [Exploratory Data Analysis](#exploratory-data-analysis)
- [Data Cleaning Steps](#data-cleaning-steps)
- [Data Manipulation Steps](#data-manipulation-steps)
- [Univariate Analysis Steps](#univariate-analysis-steps)
- [Bivariate Analysis Steps](#bivariate-analysis-steps)
- [Key Business Question](#key-business-question)
- [Conclusion (Key Findings Overall)](#conclusion-key-findings-overall)
- [Q&A](#qa)
- [Experience and Challenges](#experience-and-challenges)
- [Usage](#usage)
- [License](#license)

## Business Problem and Use Case Domain Understanding
- **Domain**: Social Media Sentiment Analysis
- **Business Problem**: Analyze and understand public sentiment towards various topics on Twitter by classifying tweets into positive, neutral, and negative sentiments.
- **Use Case**: Sentiment analysis helps businesses monitor customer opinions, track brand reputation, and make informed decisions based on public feedback.

## Objective of the Project
To build a robust machine learning model to classify tweets into positive, neutral, and negative sentiments. This involves preprocessing the data, building and tuning an LSTM model, and deriving insights from the analysis to help stakeholders understand public sentiment trends.

## Data Collection
While this project uses a pre-collected dataset, the typical approach to collecting Twitter data involves:
- Using APIs like Twitter API.
- Authenticating and connecting to the API.
- Defining query parameters to fetch relevant tweets.
- Storing the collected data in a structured format (e.g., CSV or DataFrame).

## Summary of the Data
- **Columns**: `target`, `ids`, `date`, `flag`, `user`, `text`
- **Target**: Sentiment labels (0 and 4) representing negative and positive sentiments.
- **Text**: Actual tweet content.
- **Date**: Timestamp of the tweet.
- **User**: User who posted the tweet.
- **Flag**: Non-informative column (constant value).

## Exploratory Data Analysis
### Data Cleaning Steps
1. **Column Renaming**: Renamed columns for better readability.
2. **Target Mapping**: Mapped target values: `0` to `negative`, `4` to `positive`.
3. **Date Parsing**: Parsed `date` column to extract `date_only`, `time`, and `year`.
4. **Dropped Irrelevant Columns**: Dropped the `flag` column.

### Data Manipulation Steps
1. **Tokenization**: Converted tweet text into sequences of tokens using Keras `Tokenizer`.
2. **Padding**: Padded sequences to a fixed length (300) for consistent input to the model.
3. **Label Encoding**: Encoded target labels into numerical values for model training.

### Univariate Analysis Steps
1. **Class Distribution**: Plotted the distribution of sentiment classes to check for balance.
2. **Tweet Frequency by Date**: Analyzed the number of tweets per day to identify peak activity periods.

### Bivariate Analysis Steps
1. **Sentiment by Date**: Examined sentiment trends over time to understand how sentiment varies by date.
2. **Sentiment by User**: Analyzed the distribution of sentiments by user to identify any significant patterns.

## Key Business Question
**How does public sentiment towards various topics on Twitter fluctuate over time, and what are the primary factors influencing these trends?**

## Conclusion (Key Findings Overall)
1. **Data Quality**: Cleaned and preprocessed data, including handling date-time formats and dropping irrelevant columns.
2. **Sentiment Distribution**: Identified potential class imbalance, with more tweets labeled as negative than positive.
3. **Peak Activity**: Found certain days with higher tweet activity, indicating potential events or news driving public engagement.
4. **Model Performance**: Built and tuned an LSTM model, achieving good accuracy in classifying tweet sentiments.
5. **Future Improvements**: Addressing class imbalance, exploring advanced embeddings, and using cross-validation could further improve model performance.

## Q&A
1. **What is the purpose of this sentiment analysis project?**
   - To classify tweets into sentiments to understand public opinion trends.
2. **How was the data collected?**
   - For this project, a pre-collected dataset was used. In practice, tools like Twitter API can be used for data collection.
3. **What preprocessing steps were taken?**
   - Data cleaning, tokenization, padding, and label encoding.
4. **What model was used for sentiment analysis?**
   - An LSTM model with hyperparameter tuning using Keras Tuner.
5. **What were the key findings?**
   - Discovered class imbalances and peak tweet days, built a performant LSTM model.

## Experience and Challenges
### Experience:
- Gained hands-on experience in data preprocessing, exploratory data analysis, and building machine learning models.
- Learned to use tools like Keras Tuner for hyperparameter optimization.

### Challenges:
- Handling imbalanced data which can affect model performance.
- Parsing complex date-time formats and extracting meaningful features.
- Ensuring consistent and accurate preprocessing steps to avoid errors in subsequent analysis.

## Usage
To replicate the analysis and model building steps, follow these instructions:

1. **Clone the repository**:
   ```sh
   git clone https://github.com/yourusername/twitter-sentiment-analysis.git
   cd twitter-sentiment-analysis
   ```

2. **Install dependencies**:
   ```sh
   pip install -r requirements.txt
   ```

3. **Run the Jupyter notebook**:
   ```sh
   jupyter notebook
   ```
   Open `sentiment_analysis.ipynb` to see the full workflow.

## License
This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

---

By following these steps and using the provided code, you can conduct your own sentiment analysis on Twitter data and build robust machine learning models to classify tweet sentiments.
