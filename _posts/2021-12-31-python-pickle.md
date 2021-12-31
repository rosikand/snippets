---
layout: default
tags: python
title: Pickling in Python
---

# Pickling in Python  

## Pickling (serializing) 
```python
import pickle
out_file = open("path/file-name.pkl", "wb")
pickle.dump(object_to_pickle, out_file)
out_file.close()
```

## Un-pickling (unserializing) 

```python
import pickle
in_file = open('path/file-name.pkl', 'rb')
loaded_object = pickle.load(in_file) 
```
