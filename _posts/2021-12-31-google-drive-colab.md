---
layout: default
tags: miscellaneous
Title: Connect Google Colab to Google Drive 
---

# Connect Google Colab to Google Drive 

This allows you to access files (i.e. dataset files) from your Google Drive in Google Colab python. 

```python
from google.colab import drive
drive.mount('/content/drive')
```