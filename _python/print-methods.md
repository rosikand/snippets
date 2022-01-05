---
layout: default
title: Print methods of object/class 
---

# Print methods of object/class 

1. Create an instance of a class (e.g. `my_obj`). 
2. Use the `dir` method: 
```python
print(dir(my_obj))
```

Note that this will print out all of the dunder methods as well. To filter those out, use (this snippet was taken from [here](https://www.askpython.com/python/examples/find-all-methods-of-class)): 
```python
method_list = [method for method in dir(MyClass) if method.startswith('__') is False]
print(method_list)
```

Alternatively, use the `inspect` package: 

```python
import inspect 

 # Store methods in a list 
method_list = inspect.getmembers(ClasName, predicate=inspect.ismethod)
 
print(method_list)
```

See more [here](https://www.askpython.com/python/examples/find-all-methods-of-class). 


