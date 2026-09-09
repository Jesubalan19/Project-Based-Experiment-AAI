<H3>NAME: Jesubalan A</H3>
<H3>REGISTER NO.: 212223240060</H3>
<H3>DATE: 08-08-2026</H3>

<H1 Align="center">Project Based Experiment</H1>

<H3>Objective:</H3>

### To perform sentiment analysis on a small Facebook text dataset using VADER and count the number of occurrences of the name "Tom" in the extracted text.

<H3>Program:</H3>

```python
import pandas as pd
import nltk
from nltk.sentiment.vader import SentimentIntensityAnalyzer

nltk.downloader.download('vader_lexicon')

file = "FacebookPosts.xlsx"

xl = pd.ExcelFile(file)
dfs = xl.parse(xl.sheet_names[0])
dfs = list(dfs['Timeline'])

sid = SentimentIntensityAnalyzer()

for data in dfs:
    ss = sid.polarity_scores(data)
    print(data)
