Configuration
=============

rST Blog expects a YAML file with some configuration values. For example::

    active_modules: [
      foo,
      bar,
      baz
      ]
    programs:
      '*.rst': 'rst'
      '*.jpg': 'image'
      '*.jpeg': 'image'
      '*.png': 'image'
    canonical_url: http://example.com/
    template_path: ../templates
    asset_map_path: static/assets.json
    ignore_files: ['.*', '_*', 'config*.yml', 'Makefile', 'README', '*.conf', '*~']
    modules:
      blog:
        index_url: /blog/
        per_page: 10

The templates are rendered in a context that contains 

Config vs. Context
------------------

Each page or blog post consists of a reST body and a YAML header. The post or
page Jinja2 template then renders in the context of the header and body.

The important thing to note here is that the config is available in the
context; both the global ``config.yml``, and any local ``config.yml`` in the
same directory as the page in question.
