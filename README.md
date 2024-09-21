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

print("Sentiment analysis completed and results saved!")![Screenshot 2024-09-21 191630](https://github.com/user-attachments/assets/960c091a-6837-4cbc-a6ba-0a12e3aaf6a4)
![Screenshot 2024-09-21 191502](https://github.com/user-attachments/assets/3d6abaef-95e0-4cff-87b7-f0af5a4f2230)
![Screenshot 2024-09-21 191446](https://github.com/user-attachments/assets/bcd98df6-8508-48bd-a4c9-71156e74598b)
![Screenshot 2024-09-21 191426](https://github.com/user-attachments/assets/65bee24f-c3c5-4afd-aef0-10b1b8c1df51)
