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


### SCP 

Secure copy protocol (scp) provides a way to transfer files between two unix computers (and works with SSH too!) 

**File**:

[Source](https://kb.iu.edu/d/agye#:~:text=In%20Unix%2C%20you%20can%20use,password%20or%20passphrase%20for%20authentication.). 

```bash
scp [options] username1@source_host:directory1/filename1 username2@destination_host:directory2/filename2
```

**Directory**: 
just add the `-r` flag: 


**Example**: 

```bash
scp -r sunetid@myth.stanford.edu:WWW .
```
