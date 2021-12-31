---
layout: default 
title: Flask "Hello, World!" example 
tags: python
---

Simple Python Flask app that displays the string `"Hello, World!"` in the browser. 

```python
from flask import Flask
app = Flask(__name__)

@app.route('/')
def hello_world():
    return 'Hello, World!'
```
