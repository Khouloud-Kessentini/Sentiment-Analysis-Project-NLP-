# Sentiment-Analysis-Project-NLP

The main steps include:

1.   Data pre-processing

  *   Data loading and columns selection
  *   Convert reviews to lowercase and remove emojis, numbers and punctuation
  *   Remove stop words ("and", "in", "at", etc)

2.   One-Hot encoding of reviews (conversion of text reviews to boolean vectors)
3.   Splitting data into test and evaluation (cross-validation 80% - 20%)
4.   Neural network implementation
  * Architecture:
      *  Input layer size  = number of variables (columns) in the One-Hot matrix
      *  Hidden layer 1 size = 64
      *  Hidden layer 2 size = 128
      *  Output layer size = 2 (number of classes, or potential reviews; either 0 or 1)
5.   Adding dropout to prevent overfitting
6.   Testing model accuracy

```python
import pandas as pd
from sklearn.feature_extraction.text import CountVectorizer
import re
import nltk
nltk.download('stopwords')
nltk.download('punkt')
nltk.download('words')
from nltk.corpus import stopwords
from nltk.tokenize import word_tokenize
from nltk.corpus import words
from sklearn.preprocessing import LabelEncoder
from keras.models import Sequential
from keras.layers import Dense, Dropout
from keras.utils import to_categorical
from tensorflow.keras.optimizers import Adam
from sklearn.model_selection import train_test_split
```

# Text pre-processing
```python
df = pd.read_csv("/content/full-corpus.csv")
df
```
