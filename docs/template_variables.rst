Template Variables
==================

Here are some variables you may see in the Jinja2 templates, and their types.

- ``config``: A :class:`~rstblog.config.Config` instance. This will be
  populated at least with the base ``config.yml`` file.
- ``ctx``: A :class:`~rstblog.builder.Context` instance. This is populated from
  the YAML header of the page or post being compiled.
- ``rst``: A :class:`dict` with three keys:

  - ``title``: the plain text of the first H1 in the reST body of the page or
    post.
  - ``html_title``: the text of the first H1 in the reST body, wrapped in ``<h1
    class="title">``, as a `MarkupSafe`_ :class:`Markup` class.
  - ``fragment``: the rest of the reST body, after the first H1, as a
    MarkupSafe :class:`Markup`.


.. _MarkupSafe: https://www.palletsprojects.com/p/markupsafe/
