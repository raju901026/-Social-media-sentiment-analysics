# -Social-media-sentiment-analysics


import pandas as pd
from textblob import TextBlob

# Path to your CSV file
csv_path = r"C:\power bi\social media sentiment\Tweets.csv"

# Load the dataset
df = pd.read_csv(csv_path)

# Function to get the sentiment
def get_sentiment(text):
    analysis = TextBlob(text)
    if analysis.sentiment.polarity > 0:
        return 'Positive'
    elif analysis.sentiment.polarity == 0:
        return 'Neutral'
    else:
        return 'Negative'

# Drop rows with missing 'text' values
df = df.dropna(subset=['text'])

# Apply the function to the text column
df['sentiment'] = df['text'].apply(get_sentiment)

# Save the results to a new CSV file
output_path = r'C:\power bi\social media sentiment\sentiment_analysis_results.csv'
df.to_csv(output_path, index=False)

![Screenshot 2024-09-21 191630](https://github.com/user-attachments/assets/8e171737-52b7-44af-8478-cbd25cd6f8a7)
![Screenshot 2024-09-21 191446](https://github.com/user-attachments/assets/147d964a-c9b2-4a9e-8c1e-1ecc8b199391)
![Screenshot 2024-09-21 191426](https://github.com/user-attachments/assets/a346b519-f1cd-4982-9774-20b03e12a6d3)


