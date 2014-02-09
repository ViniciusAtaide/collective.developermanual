================================================
Models, forms, fields and widgets
================================================

Plone includes several alternative form mechanisms:

For content-oriented forms:

* :doc:`Dexterity </getstarted/dexterity>` for Plone 4.1+

* :doc:`Archetypes </reference_manuals/old/archetypes/index>` is used for content types in Plone 3.x

For convenience forms built and maintained through-the-web and where the results are stored in CSV sheet or emailed:

* :doc:`PloneFormGen </reference_manuals/active/ploneformgen/index>`

For application and utility forms where custom logic is added by writing Python code:

* z3c.form for Plone 4.x

* zope.formlib is used for stock forms in Plone 3.x

This documentation applies only for form libraries.

You need to identify which form library you are dealing with and read the form library specific
documentation.

Zope 3 schema (zope.schema package) is database-neutral and framework-neutral way to describe Python data models.

Modelling data
----------------

.. toctree::
    :maxdepth: 1

    schemas
    vocabularies

Forms, fields and widgets
------------------------------

.. toctree::
    :maxdepth: 1

    manual
    z3c.form
    files
    wysiwyg

Creating forms through-the-web without programming
----------------------------------------------------

.. toctree::
    :maxdepth: 1

    ploneformgen
