---
layout: default 
title: Some unix commands
---

# Some unix commands

### Run previous command 

Instead of having to write out `python3 prog.py` every time, you can do 

```
ctrl + p
```

to type the previous command! 

### Download entire website and all its files

```bash
wget -r --no-parent <site-url-here>
```

### Unzip gzipped tar

Useful for getting LaTeX source from Arxiv papers. 

```bash
tar -xvf <file-name-here>
```
