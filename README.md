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

![Screenshot 2024-09-21 191630](https://github.com/user-attachments/assets/70e7abc0-44f9-4313-898c-622bbafe65c8)
![Screenshot 2024-09-21 191502](https://github.com/user-attachments/assets/2cab463a-cbaa-4c2c-993b-09a2a3e1f523)
![Screenshot 2024-09-21 191446](https://github.com/user-attachments/assets/0f94f080-4ccb-4bad-bdd5-ac44ed8e31b9)
![Screenshot 2024-09-21 191426](https://github.com/user-attachments/assets/162d54e7-583e-47df-b575-c6477cd90a76)


