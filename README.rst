rstBlog
=======

Based on `Armin Ronacher's <https://github.com/mitsuhiko/rstblog>`_ static blog
generator.

To build the documentation::

    # In a virtual env:
    pip install pyyaml babel blinker docutils werkzeug jinja2 sphinx
    cd docs
    make html
    open _build/html/index.html
