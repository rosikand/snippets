---
layout: default 
title: Flask "Hello, World!" example 
---

# Flask `"Hello, World!"` example 

Simple Python Flask app that displays the string `"Hello, World!"` in the browser. 

```python
from flask import Flask
app = Flask(__name__)

@app.route('/')
def hello_world():
    return 'Hello, World!'
```
Run locally: 

```python
export FLASK_APP=app.py
export FLASK_DEBUGGING=1
flask run 
```
