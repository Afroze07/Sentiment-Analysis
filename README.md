Project: News Article Sentiment Analyzer
Overview
This project analyzes the sentiment of a news article using the newspaper3k library for web scraping and article parsing, TextBlob for sentiment analysis, and nltk for natural language processing tasks. It fetches an article from a specified URL, extracts its summary, and determines whether the sentiment of the summary is positive, negative, or neutral.


## Functionality

1. Article Extraction: Downloads and parses the content of a news article from a given URL using the newspaper3k library.

2. Summarization: Extracts the summary of the article.

3. Sentiment Analysis: Uses TextBlob to analyze the sentiment polarity of the article summary.

4. Sentiment Classification: Classifies the sentiment as positive, negative, or neutral based on the sentiment polarity score.
## Dependencies

--> newspaper3k

--> TextBlob

--> nltk
## Installation

Install my-project with npm

```bash
pip install newspaper3k
pip install textblob
pip install nltk

```
You may also need to download the 'punkt' resource from nltk:

``` 
import nltk
nltk.download('punkt')

```
## Usage/Examples

1. Import Libraries: Import the necessary libraries in your Python script.

2. Specify Article URL: Provide the URL of the news article you want to analyze.

3. Analyze Sentiment: Run the script. It will print the summary of the article and its sentiment (positive, negative, or neutral).



## Code Snippet
```
from textblob import TextBlob
import nltk
from newspaper import Article

# Get the article
url = 'https://timesofindia.indiatimes.com/videos/news/delhi-under-layer-of-haze-as-air-quality-continues-to-remain-very-poor/videoshow/95332189.cms'
article = Article(url)
article.download()
article.parse()
nltk.download('punkt') # Make sure you only download this once.
article.nlp()

# Get the summary of the article
text = article.summary

# Print the text
print(text)

# Create a TextBlob object
obj = TextBlob(text)
sentiment = obj.sentiment.polarity
print(sentiment)

if sentiment == 0:
    print('The text is neutral')
elif sentiment > 0:
    print('The text is positive')
else:
    print('The text is negative')

```
## Example Output

The script will output the summary of the news article, the sentiment polarity score, and the overall sentiment classification (positive, negative, or neutral).

Note: The output will vary depending on the content of the news article being analyzed. The example URL provided focuses on air quality in Delhi, so the sentiment is likely to be negative.
## Further Development

1. Implement error handling for invalid URLs or network issues.

2. Add functionality to analyze the sentiment of the entire article content instead of just the summary.

3. Incorporate a user interface (e.g., using Flask or Streamlit) for easier interaction.

4. Allow users to input URLs or article text directly.

5. Visualize sentiment trends over time by analyzing multiple articles on the same topic.

6. Add support for multiple languages.
## License

MIT License

Copyright (c) 2025 Afroze07

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.

