# Visualization Examples 

12/31/2017: We are working on a website, http://makingdatavisual.github.io, which contains executable examples of the Chapter 5 & 6 figures. Check it out!

[Dominik Mortiz](https://www.domoritz.de/) and [Kanit Wongsuphasawat](https://kanitw.github.io/) were instrumental in creating these figures; our thanks to them. All specs are executable in [Vega and Vega-Lite](http://vega.github.io) -- a fileame ```.vg.json``` indicates a Vega file, while ```.vl.json``` indicates Vega-Lite

The [data](data) subdirectory contains original CSV or JSON formats of the data source files; the readme in that folder describes where the files come from.

If you download this entire directory and run a local webserver, the index.html should correctly render the visualizations correctly. 

```node http-server```
or
```python -m SimpleHTTPServer```