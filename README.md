# Discussion Material

## Collaboration with Git
* Create a personal token access and branch
  * [Git Tutorial (W3Schools)](https://www.w3schools.com/git/default.asp?remote=github)
  * [Collaborative Working using Git (Rakamin)](https://rakamin-lms.s3.ap-southeast-1.amazonaws.com/2llyq6ei3ootqroxqnv8yq55ilgb?response-content-disposition=inline%3B%20filename%3D%22Collaborative%20Working%20using%20Git.pdf%22%3B%20filename%2A%3DUTF-8%27%27Collaborative%2520Working%2520using%2520Git.pdf&response-content-type=application%2Fpdf&X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIATEHFT35YRRD7BK7S%2F20220703%2Fap-southeast-1%2Fs3%2Faws4_request&X-Amz-Date=20220703T093021Z&X-Amz-Expires=604800&X-Amz-SignedHeaders=host&X-Amz-Signature=efeb860e479b22839706dff0a41d7cd93f972e4bb01faa96f74c0d1e993b4562)

* Setting your account on Git Bash
  * [Configure GitHub account](https://support.atlassian.com/bitbucket-cloud/docs/configure-your-dvcs-username-for-commits/)
* Push the file into Github


## Build a virtual environment and a connection to Postgres database by using Git Bash and Jupyter
1. Create virtual environment in **Git Bash Terminal**
```
# activate conda | do not forget to activate conda everytime you open git bash
# notes: replace "miniconda3" with "anaconda3"
source ~/miniconda3/etc/profile.d/conda.sh 

# create env with python 3.9
conda create -n virtual_env_py39 python=3.9 -y
```

2. Install jupyter
```
# it will take a quite long time (around 5-10 minutes)
conda install -c conda-forge jupyterlab -y
```

3. Install the necessary libraries
```
# check the requirements.txt for the list of libraries
pip install -r requirements.txt
````

4. Open jupyter lab
```
# run this on **Git Bash Terminal**
jupyter lab --no-browser

# you will see the Output like this below
 To access the server, open this file in a browser:
        file:///C:/Users/Abrisyaf/AppData/Roaming/jupyter/runtime/jpserver-5076-open.html
    Or copy and paste one of these URLs:
        http://localhost:8888/lab?token=47437ae01f9a6c0f1753b402a5eec3ad846195f03b51ede2
     or http://127.0.0.1:8888/lab?token=47437ae01f9a6c0f1753b402a5eec3ad846195f03b51ede2

# copy and paste http://localhost:8888/lab?token=47437ae01f9a6c0f1753b402a5eec3ad846195f03b51ede2
```
5.  Build a connection to Postgres Database
```
# run this command below on **Jupyter Lab**
import pandas as pd
from sqlalchemy import create_engine

# create connection to psql
user_id = "...."
password = "......"
database_name = "....."
engine = create_engine(f"postgresql://{user_id}:{password}@localhost:5432/{database_name}")
engine.connect()

# test query if there is an existing database
def query_result(query, con=engine):
    return pd.read_sql(query, con=con)

query_result(
"""
    SELECT * 
    FROM iris
    LIMIT 5
"""
)
```

## Final Project Revision
* Revise the business simulation

