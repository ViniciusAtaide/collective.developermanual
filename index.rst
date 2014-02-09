Plone Developer Documentation
=======================================================

This document is a community maintained manual for `Plone <http://plone.org>`_ content management
system. The target audience of the documentation includes

* Integrators: installing Plone, add-ons and setting up the site

* Theme authors: changing Plone's visual appearance

* Developers: customizing Plone's content types and forms for a specific use case

* System administrators: hosting Plone on a server

This documentation does not have the end user (content editor)
documentation for Plone. For the editor documentation
please go to `plone.org documentation <http://plone.org/documentation>`_.


Table of Contents
=================

.. contents:: :local:

Tutorials
-------------------------------------------

If doing Plone development for the first time
these tutorials serve as a starting point.

* :doc:`Add-ons: how Plone add-ons are created <getstarted/index>`

* :doc:`Archetypes: Building content types on Plone with Archetypes content subsystem <reference_manuals/old/archetypes/index>`

* :doc:`Dexterity: Building TODO application on Plone with Dexterity content subsystem <reference_manuals/external/tutorials.todoapp/docs/index>`

* :doc:`Hello World: Creating z3c.form, Archetypes content type and Zope 3 Browser View <reference_manuals/active/helloworld/index>`

* :doc:`Theming: Creating Plone 4.3 themes with plone.app.theming <reference_manuals/external/plone.app.theming/userguide>`

* :doc:`Creating forms with PloneFormGen add-on without programming </reference_manuals/active/ploneformgen/getting_started>`

* :doc:`Installing Plone for production on Ubuntu </getstarted/ubuntu_production>`

Programming Plone
-------------------------------------------

.. toctree::
   :maxdepth: 1

   getstarted/index
   serving/index
   views/index
   content/index
   forms/index
   components/index
   persistency/index
   functionality/index
   searching_and_indexing/index
   i18n/index
   members/index
   security/index
   templates_css_and_javascripts/index
   sessions/index
   images/index
   functionality/syndication
   misc/index

Theme development
-------------------------------------------

.. toctree::
   :maxdepth: 1

   reference_manuals/external/plone.app.theming/userguide
   reference_manuals/external/diazo/index
   plone_theme_development/diazo_theme_recipes/index
   plone_theme_development/theme_product_with_diazo


For legacy purposes see :doc:`old Plone 3 theming manual </reference_manuals/old/plone_3_theming/index>`.

Installing and maintaining Plone sites
-------------------------------------------

.. toctree::
   :maxdepth: 1

   getstarted/installation
   getstarted/ubuntu_production
   reference_manuals/active/deployment/index
   hosting/index
   getstarted/older_installs


See the `Plone Upgrade Guide <http://plone.org/documentation/manual/upgrade-guide>`_
for detailed instructions on version upgrade procedures, including
changes required to update add-ons to work with newer versions of Plone.

Testing and tuning Plone
-------------------------------------------

.. toctree::
   :maxdepth: 1

   testing_and_debugging/index
   performance/index

Troubleshooting
-------------------

.. toctree::
   :maxdepth: 1

   troubleshooting/basic
   troubleshooting/exceptions
   troubleshooting/buildout
   troubleshooting/unicode
   troubleshooting/images
   troubleshooting/transactions

Manuals
--------------------

These manuals apply to the current best practices of Plone development.
They are in their own separate section due to the length of narrative explanation
or having the documentation source code hosted in an external package.

**Programming**

.. toctree::
    :maxdepth: 1

    reference_manuals/external/plone.api/index
    reference_manuals/external/plone.app.dexterity/index
    reference_manuals/active/schema-driven-forms/index
    reference_manuals/active/five-grok/index
    reference_manuals/external/Products.TinyMCE/index
    reference_manuals/external/tutorials.todoapp/docs/index
    reference_manuals/active/helloworld/index
    reference_manuals/active/ploneformgen/index
    reference_manuals/external/plone.app.robotframework/index
    reference_manuals/external/plone.app.multilingual/index

**Deployment**

.. toctree::
    :maxdepth: 1

    reference_manuals/active/deployment/index
    reference_manuals/external/ploneorg.admin/index

See :doc:`cross-documentation linking </reference_manuals/active/writing/crosslinking>` how to get your documentation here.

Old manuals
-----------------------

.. role:: itwillhurt
   :class: itwillhurt

:itwillhurt:`☠` Beyond this point lie the ancient dragons :itwillhurt:`☠`

.. warning ::

    The following sections of developer documentation are no longer under active maintenance.
    They are included here as reference for older technologies (Plone 2.x, Plone 3.x).
    Some of the practices described in these documents may still work, but are not recommended
    to be used in your active Plone development.

.. toctree::
    :maxdepth: 1

    reference_manuals/old/archetypes/index
    reference_manuals/old/plone_3_theming/index
    reference_manuals/old/archgenxml/index
    reference_manuals/old/buildout/index
    reference_manuals/old/forms/index
    reference_manuals/old/old-style-vs-new-style/index
    reference_manuals/old/portlets/index
    reference_manuals/old/pluggable_authentication_service/index.rst
    reference_manuals/old/testing/index
    reference_manuals/old/zope_secrets/index
    reference_manuals/old/formlib/index

:doc:`More information about the documentation deprecation process </reference_manuals/active/writing/nursinghome>`.

Documentation style guide
-----------------------------

Instructions and style guide to maintain this
and other Plone related developer documentation.

.. toctree::
    :maxdepth: 1

    reference_manuals/active/writing/index

Other
------------

.. toctree::
   :maxdepth: 1

   glossary
   moved_content




