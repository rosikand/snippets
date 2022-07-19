---
layout: default
title: Python packaging 
---

# Python packaging 

## Creating a `pip`-able package 

Follow [this](https://packaging.python.org/en/latest/tutorials/packaging-projects/) great guide. 

## Updating a package 

- Delete old `dist/` by typing `rm -r dist`. 
- Re-build new `dist` by typing `python3 -m build`. 
- Upload new version by typing `twine upload dist/*`. Enter `__token__` as your username and then enter the token for the password. 
