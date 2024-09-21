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

![Screenshot 2024-09-21 191630](https://github.com/user-attachments/assets/315faebb-7a9b-495b-a11b-38a0992335e3)
![Screenshot 2024-09-21 191502](https://github.com/user-attachments/assets/38a94f1f-d062-40ae-8694-0c61b36bed16)
![Screenshot 2024-09-21 191446](https://github.com/user-attachments/assets/b290513e-0c81-4b33-bff6-de2367315e70)
![Screenshot 2024-09-21 191426](https://github.com/user-attachments/assets/f734a5c3-2cd9-4b22-ae28-768b2a116ac4)

