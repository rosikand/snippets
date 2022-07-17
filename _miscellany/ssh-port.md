---
layout: default 
title: SSH port forwarding   
---

# SSH port forwarding 

If you want to open up a jupyter notebook in a remote cloud computing instance, you can log in using ssh with the port-forwarding option enabled. For example, I'd type

```python
ssh -L 8888:localhost:8888 sunetid@myth.stanford.edu
```

to open up a nb on the Stanford Myth computer cluster. Then, type `jupyter notebook` in the remote computer instance to launch the nb server. Open this link in your local browser. Done! 

The same concept applies to things like AWS EC2 and Google GCP. 
