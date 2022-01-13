---
layout: default 
title: Make file executable  
---

# Make file executable 

Say you have the script `script.py` that you run frequently. Instead of having to type `python3 script.py` everytime, you can make the script file executable. 

For Python scripts: 
1. First, `cd` into the directory of the script. 
2. Add your Python install location as a shebang to the top of `script.py` (e.g. `#!/usr/bin/python3`). Your Python install location might be somewhere else however. To find its location, type `which python`. 
3. Then, type `chmod 755 script.py`. 

You can now run the script via `./script.py`. You can remove the `.py` extension now. 

This is generalizable to non-Python files as well. 
