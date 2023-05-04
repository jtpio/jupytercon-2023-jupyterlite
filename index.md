---
marp: true
paginate: true
style: |
  .columns {
    display: grid;
    grid-template-columns: repeat(2, minmax(0, 1fr));
    gap: 1rem;
  }
---

<style>
section::after {
  content: attr(data-marpit-pagination) '/' attr(data-marpit-pagination-total);
}
img[alt~="center"] {
  display: block;
  margin: 0 auto;
}
iframe {
  border: none;
}
</style>

![bg fit right:33%](https://raw.githubusercontent.com/jupyterlite/jupyterlite/main/docs/_static/icon.svg)

## :bulb: Create interactive Jupyter websites with JupyterLite

### :orange_circle: JupyterCon 2023

#### :date: 2023-05-10

#### :bust_in_silhouette: Jeremy Tuloup

- https://github.com/jtpio
- https://twitter.com/jtpio
- https://fosstodon.org/@jtp

---

# About

## 🧑‍🚀 Technical Director at QuantStack

## 🟠 Core Jupyter Developer

<div class="columns">
<div>

![center h:256px](https://quantstack.net/img/logo.svg)

</div>
<div>

![center h:256px](https://jupyter.org/assets/homepage/main-logo.svg)

</div>
</div>

---

# What is JupyterLite?

![bg fit right:33%](https://raw.githubusercontent.com/jupyterlite/jupyterlite/main/docs/_static/icon.svg)

> JupyterLite is a JupyterLab distribution that runs entirely in the web browser, backed by in-browser language kernels.

---

# Lightweight Jupyter Frontend running in the browser

![center w:512](https://raw.githubusercontent.com/jupyterlite/jupyterlite/main/docs/_static/badge-launch.svg)

- ✅ no Python server
- ✅ no command line
- ✅ no need to install Python and other packages on the user machine
- ✅ can be hosted as a static website

---

# Boots in seconds

![center h:600px](https://user-images.githubusercontent.com/591645/120649478-18258400-c47d-11eb-80e5-185e52ff2702.gif)

---

# The `jupyter-lite` CLI is a **Static Site Generator** (SSG)

```shell
# install the CLI
pip install jupyterlite-core

# build the website
jupyter lite build
```

---

# It generates static assets that can be served easily

```
├── api
│   └── translations
│       ├── all.json
│       └── en.json
├── bootstrap.js
├── build
│   ├── 9507.1e6cc5d.js
│   ├── 9602.62bf0f1.js
│   ├── 9621.e2e8b5d.js
│   ├── ...
│   ├── repl
│   │   ├── bundle.js
│   ├── retro
│   │   ├── bundle.js
│   ├── schemas
│   │   ├── all.json
│   │   ├── @jupyterlab
│   │   │   ├── application-extension
│   │   │   │   ├── commands.json
│   │   │   │   ├── context-menu.json
│   │   │   │   ├── shell.json
│   │   │   │   └── sidebar.json
│   ├── themes
│   │   └── @jupyterlab
│   │       ├── theme-dark-extension
│   │       │   ├── index.css
│   │       │   └── index.js
│   │       └── theme-light-extension
│   │           ├── index.css
│   │           └── index.js
├── config-utils.js
├── extensions
│       └── xeus-python-kernel
│           └── static
│               ├── numpy-1.24.2-py310h6d2fff6_0.0.data
│               ├── numpy-1.24.2-py310h6d2fff6_0.0.js
│               ├── python-3.10.2-h_hash_26_cpython.0.data
│               ├── python-3.10.2-h_hash_26_cpython.0.js
│               ├── python_data.js
│               ├── remoteEntry.35b4eac217ec6bf078a4.js
├── lab
│   ├── favicon.ico
│   ├── index.html
│   ├── jupyter-lite.ipynb
│   ├── jupyter-lite.json
│   ├── package.json
│   ├── tree
│   │   └── index.html
│   └── workspaces
│       └── index.html
...
```

---

# Easy to deploy

- Documentation: https://jupyterlite.readthedocs.io/en/latest/deploying.html
- Served via well-cacheable, static HTTP(S) on most static web hosts

<div class="columns">
<div>

![center width:256](https://user-images.githubusercontent.com/591645/120675034-00f29080-c495-11eb-928c-26bb94e8eb68.png)
![center width:256](https://user-images.githubusercontent.com/591645/120676545-6dba5a80-c496-11eb-9b2b-604e92c3429b.png)
![center width:256](https://user-images.githubusercontent.com/591645/120675516-6f375300-c495-11eb-819c-d6f1fb3cb0f1.png)

</div>
<div>

![center width:256](https://user-images.githubusercontent.com/591645/120676313-2df37300-c496-11eb-8639-25e2fc606850.png)
![center width:256](https://user-images.githubusercontent.com/591645/236239105-d00f05df-ee79-4062-a0a8-f0f0118bbe1d.png)
![center h:128](https://upload.wikimedia.org/wikipedia/commons/thumb/b/bc/Amazon-S3-Logo.svg/428px-Amazon-S3-Logo.svg.png)

</div>
</div>

---

![bg fit right height:400px](https://user-images.githubusercontent.com/591645/162748538-e44fea00-f727-4055-b795-8f5fc5c6b133.png)

# Standing on the shoulders of giants

-  Built from the ground-up using JupyterLab components and extensions
- The frontend communicates to the in-browser kernels via the Jupyter Protocol

---

#  Wasm powered Jupyter running in the browser 💡

- https://developer.mozilla.org/en-US/docs/WebAssembly

![center h:400px](https://user-images.githubusercontent.com/591645/162831191-16956085-783a-435e-b810-0d25da1379b3.png)

---

# Interactive Computing in the browser

- Python kernels:
  - Pyodide
  - Xeus Python
- Visualizations:
   - matplotlib
   - ipywidgets
   - plotly
   - and more...

---

# Embed a live Python console on your website 🚀

![center h:300px](https://user-images.githubusercontent.com/591645/162619390-ecab994a-3f39-4e26-af78-ca2569aee9b2.png)

Embed with:

```html
<iframe
  src="https://jupyterlite.github.io/demo/repl/index.html?kernel=python&toolbar=1"
  width="100%"
  height="500px"
>
</iframe>
```

---

# Or even the full JupyterLab UI

<iframe
  src="http://jtpio.github.io/jupytercon-2023-jupyterlite/lab/index.html?path=demo.ipynb"
  width="100%"
  height="100%"
>
</iframe>

---

# numpy.org

![center](https://user-images.githubusercontent.com/591645/162569443-40e841ad-f42d-44eb-966f-c1c810c1ab10.png)

---

# sympy.org

![center h:500px](https://user-images.githubusercontent.com/591645/167361691-da1252e7-17f4-4bbf-8eee-ba3bfaff8c2e.png)

---

# jupyterlite-sphinx

![center h:500px](https://user-images.githubusercontent.com/591645/162838828-d6407725-15d9-4640-8aa6-c8c8979a9a3f.png)

---

# Deploy your own on GitHub Pages :rocket:

Quickstart: https://github.com/jupyterlite/xeus-python-demo

![center height:400px](https://raw.githubusercontent.com/jupyterlite/xeus-python-demo/main/deploy.gif)

---

# Adding notebooks, files and static assets

Create a `notebooks` folder and add a notebook and a CSV file:

```bash
ls notebooks

demo.ipynb iris.csv
```

Build with the `--contents` flag:

```bash
jupyter lite build --contents notebooks
```

---

<video
  controls autoplay
  width="100%"
  height="600px"
  src="https://user-images.githubusercontent.com/591645/236281330-8c1c21a3-aec2-4af4-9280-fa65fc330f24.mp4" >
</video>

---

# Adding extensions to the user interface

In `build-environment.yml`:

```yaml
name: build-env
channels:
  - conda-forge
dependencies:
  # custom themes
  - jupyterlab-night
  # extra language pack
  - jupyterlab-language-pack-fr-FR
```

---

<video
  controls autoplay
  width="100%"
  height="600px"
  src="https://user-images.githubusercontent.com/591645/236281342-fb299b8d-c9fc-4777-836a-b2e4e9d0ca46.mp4">
</video>

---

# Adding packages to the Python runtime

With the Xeus Python kernel, edit `environment.yml`:

```yaml
name: xeus-python-kernel
channels:
  - https://repo.mamba.pm/emscripten-forge
  - https://repo.mamba.pm/conda-forge
dependencies:
  - ipycanvas
  - numpy
  - pandas
  - # add more dependencies here
```

---

<video
  controls autoplay
  width="100%"
  height="600px"
  src="https://user-images.githubusercontent.com/591645/236281346-a942464d-4527-454e-9470-d35a2bcb96d3.mp4">
</video>

---

# How-To Guides

- Documentation: https://jupyterlite.readthedocs.io/en/latest/
- Configuration files, extensions, storage, kernels...

![center h:500px](https://user-images.githubusercontent.com/591645/236241822-ba520432-8818-46cd-b64c-6c85900406fa.png)

---

# Deploy static web applications with Voici

![center](https://raw.githubusercontent.com/voila-dashboards/voila/main/docs/source/voila-logo.svg)

---


# Before

```shell
jupyter lite build --contents notebooks
```

# After

```bash
# build with the Voici CLI
voici build --contents notebooks

# to keep the JupyterLab and Notebook interfaces available
voici build --contents notebooks --apps lab --app retro
```

---

<video
  controls autoplay
  width="100%"
  height="600px"
  src="https://user-images.githubusercontent.com/591645/236285012-1c9afa23-8da4-45ea-9b0b-10c5cd2087f0.mp4">
</video>

---

# Strengths

- Easy to deploy (static files)
- Interactive computing in the browser accessible to more people
- Simpler for users (no need to install Python and other packages locally)
- Educational use cases
- Reproducibility time capsule

---

# Limitations

- Suited for lighter workloads
- Not all packages are available (or ever will be)
- Subset of Python running in the browser
- Initial asset download can be big (~30MB), then cached by the browser

---

# What's next?

- Update JupyterLite to JupyterLab 4 and Notebook 7
- Improvements to the Emscripten Forge toolchain and packages
- Improvements to the Xeus Python kernel:
  - Install packages at runtime
  - Install packages from PyPI
  - Lazy loading

---

# JupyterCon 2023

<div class="columns">

<div>

![h:512px](https://user-images.githubusercontent.com/591645/236242363-606b809a-1998-4f0b-a569-79677e417629.png)

</div>

<div>

![image](https://user-images.githubusercontent.com/591645/236242865-c96bd19f-cfd0-48fb-b849-4fd8c7e82362.png)

</div>
</div>

---

# Thanks!

![bg fit right:33%](https://raw.githubusercontent.com/jupyterlite/jupyterlite/main/docs/_static/icon.svg)

Thanks to all the contributors of JupyterLite, Pyodide, Emscripten Forge, and the Jupyter Community!

- Repository: https://github.com/jtpio/jupytercon-2023-jupyterlite
- Live version: https://jtpio.github.io/jupytercon-2023-jupyterlite/files/index.html
