<img src="https://user-images.githubusercontent.com/16124573/62647088-ca41a280-b91d-11e9-9023-f06273eb09ce.png" width="400">

# voila-homepage
A simple homepage for serving notebooks with voila.

[`voila`] is amazing! This project present a single homepage for serving voila and other dashboards (via links).

## Installation

- make a directory where you want to serve your notebooks from, e.g., `~/my_notebooks`
- put your notebooks in that directory
- copy `homepage.ipynb` and `config.yml` to that directory
- cd to that directory
- start <kbd>`voila`</kbd>; you will see command line output like

```
17:43 $ voila
[Voila] Using /tmp to store connection files
[Voila] Storing connection files in /tmp/voila_r_kwka3j.
[Voila] Serving static files from /home/user/voila/voila/static.
[Voila] Voila is running at:
http://localhost:8868/
```

- point your browser to `http://localhost:8866/voila/render/homepage.ipynb` and **boom** ... you are greated with a dynamically created Vuetify display of your notebook directory!

## Configuration

You need to make sure that the `config.yml` file makes sense for you. It contains the
- voila server URL
- the name that is displayed on the dashbaord title bar
- the links on the right of the dashboard bar
- any additional sites you want to link to (e.g, if you have non-Jupyter notebook links that you want to mix into this screen).

## Notebook Metadata

The hompeage is built by creating Vuetify cards from the notebooks in your directory. If you don't put any special metadata into your notebooks, each cards will have a title equal to the notebook filename, and a description that says "A Jupyter Notebook." However, you can also add metadata to your notebooks using `scrapbook` for the **title** and **description**. Simply add a cell like this anywhere in your notebook:

```python
import scrapbook as sb

sb.glue('title', 'Dashboard A')
sb.glue('description', 'Lorem ipsum dolor sit amet, consectetur adipiscing elit.')
```

That's it. This metadata will be read and used to construct the card.
