## General Information

The intent of this repo is to use OpenAI for question Answering based on a sql database and few other retrieval based question answering tasks using langchain.  
The [movie-dialog-corpus from cornell](https://www.kaggle.com/datasets/Cornell-University/movie-dialog-corpus) is used in this repo and its pre-processing is done along with its conversion to a relational SQL database with addition of relational db constraints such as primary key, foreign key etc.  

1. Preprocessing was performed on initial corpus (movie-dialog-corpus directory) and the database is exported as a SQLite database in database directory. Notebook is available in notebooks directory for the preprocessing and conversion ([preprocess_and_convert_to_sqlite_db.ipynb](./notebooks/preprocess_and_convert_to_sqlite_db.ipynb)).

2. Question Answering is done using OpenAI's davinci model along with langchain, the approach is described in the notebook [question_answering_on_sql_database.ipynb](./notebooks/question_answering_on_sql_database.ipynb)   

### How to view database and tables via database explorer
SQLite database file moviesdb.db can be viewed by using a viewer for SQLite database such as https://sqlitebrowser.org/  

### How to view database in python
To view database in python, run the below code in same directory as database
```
import sqlite3
import pandas as pd
con = sqlite3.connect("moviesdb.db")
df = pd.read_sql_query("SELECT * from movie_titles", con)
```

ER Diagram of the database is below: -
![ER_Diagram](./img/ER_diagram.png)