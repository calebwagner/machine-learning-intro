# Machine Learning Intro

This repo is me documenting my work with some basic machine learning with Python.

If you want to check it out yourself download [Anaconda](https://www.anaconda.com/products/distribution).

You can open up a terminal window and type `jupyter notebook` which will start the notebook server. If you get an error `zsh: command not found: jupyter` you'll need to do some additional configurations. [Here](https://superuser.com/questions/1493257/cannot-open-jupyter-notebook-in-the-new-zsh-shell-in-macos) is a link that might help you with this configuration, however, this isn't a necessary step. You can just open the Anaconda Navigator app and launch Jupyter. You'll then see the Jupyter Dashboard appear.

Next, create a new notebook for python. Click `Desktop` (or anything place you want to place this project) then click `New` and `Python 3` in the dropdown.

Now import a data set. I used one from [Kaggle](https://www.kaggle.com/). Download any data set of your choice.

Go back to your Jupyter notebook and import your data set ...
```python
import pandas
data = pandas.read_csv('your data set here')
data
```
Click `Run` to see the data.

I chose some music data and tested if there was a correlation between gender and music genres.
```python
import pandas as pd
from sklearn.tree import DecisionTreeClassifier
from sklearn.model_selection import train_test_split
from sklearn.metrics import accuracy_score

df = pd.read_csv('music.csv')
X = df.drop(columns=['genre'])
y = df['genre']
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2)

model = DecisionTreeClassifier()
model.fit(X_train, y_train)
predictions = model.predict([ [21, 1], [22, 0] ])
predictions = model.predict(X_test)

score = accuracy_score(y_test, predictions)
score
```

🚨🚨 more documentation coming ... 🚨🚨
