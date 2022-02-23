---
layout: default
title: Use LaTeX in Jekyll
---

# Use LaTeX in Jekyll 

Simply paste 

```html
<script src="https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS-MML_HTMLorMML" type="text/javascript"></script>
```

in the `.html` file in the `_layouts` folder of the layout you are using for the designated post. Note: you must wrap the LaTeX code in `$$` instead of `$` in the markdown source. If you want to bypass this requirement, insert the following snippet _above_ the mathjax import: 

```html
<script type="text/x-mathjax-config">
  MathJax.Hub.Config({
    tex2jax: {
      inlineMath: [ ['$','$'], ["\\(","\\)"] ],
      processEscapes: true
    }
  });
</script>
```

Source: [http://www.iangoodfellow.com/blog/jekyll/markdown/tex/2016/11/07/latex-in-markdown.html](http://www.iangoodfellow.com/blog/jekyll/markdown/tex/2016/11/07/latex-in-markdown.html) and [https://tex.stackexchange.com/questions/27633/mathjax-inline-mode-not-rendering/27656](https://tex.stackexchange.com/questions/27633/mathjax-inline-mode-not-rendering/27656)
