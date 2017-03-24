Configuration
=============

rST Blog expects a YAML file with some configuration values.

Modules can expect their own configuration keys, but the core system knows
about these:

``canonical_url``
    The full root URL at which the site expects to be served. Something like
    ``https://example.com/``.
``template_path``
    The path, relative to the config file, where templates can be found.
    Defaults to ``_templates``.
``locale``
    The locale for the site. Defaults to ``en``.
``template_autoescape``
    Passes through to Jinja2 Environment ``autoescape``. Sets whether HTML/XML
    tags are escaped. Defaults to ``True``.
``static_folder``
    The path, relative to the config file, where static assets are stored.
    Defaults to ``static``.
``active_modules``
    A list of installed module names.
``output_folder``
    The path, relative to the *project root*, where the built site is emitted.
    Defaults to ``_build``.
``ignore_files``
    A list of glob patterns to ignore when building the site, or ``None`` if
    nothing should be ignored. Defaults to ``None``.
``programs``
    A dict of file extension to program name, for what compilation program
    should be used for what file types. Defaults to ``{'*.rst': 'rst'}``, and
    falls back to ``copy`` if it cannot find a matching program.


A given context (i.e. ``.rst`` file on disk) can override the template used to
render it with the ``template`` key in its YAML header.


Config vs. Context
------------------

Each page or blog post consists of a reST body and a YAML header. The post or
page Jinja2 template then renders in the context of the header and body.

The important thing to note here is that the config is available in the
context; both the global ``config.yml``, and any local ``config.yml`` in the
same directory as the page in question.
