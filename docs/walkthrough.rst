Walkthrough
===========

The absolute basics:

We start with the :class:`~rstblog.builder.Builder`. This class, and in
particular, the :meth:`~rstblog.builder.Builder.run` method, is the system's
entrypoint.

This method gets a collection of :class:`Contexts <rstblog.builder.Context>` by
walking the filesystem for content and config files. It then builds each
:class:`~rstblog.builder.Context` if it has changes.

Each :class:`~rstblog.builder.Context` has a ``program`` attribute, which knows
how to build it. In most cases, that program will always be
:class:`~rstblog.programs.RSTProgram`.

:class:`~rstblog.programs.RSTProgram` takes the yaml header and extracts it,
then takes the reST body and renders it to HTML, and then embeds that into a
template (with a sensible default template available).

That output file is then placed in the output directory.
