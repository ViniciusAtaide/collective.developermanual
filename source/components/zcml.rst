======
 ZCML
======

.. admonition:: Description

    What Plone programmers should know about ZCML.

.. contents :: :local:

Introduction
=================

:term:`ZCML` stands for the *Zope Configuration Mark-up Language*.  It is an
XML-based language used to extend and plug into systems based on the Zope
Component Architecture (:term:`ZCA`).

It provides:

* conflict resolution (e.g. two plug-ins cannot overlap);
* extensible syntax based on namespaces.

Downsides of ZCML are:

* it is cumbersome to write by hand;
* lack of end-user documentation.

Plone uses ZCML to:

* register components with various places in the system, both core and
  add-ons.

.. note::

    Everything you can do in ZCML can also be done in Python code.

After developers found ZCML cumbersome, the
:doc:`Grok framework </components/grok>` was created. Grok makes it possible
use the ZCA without writing XML by enabling Python directives and function
decorators to be used instead.

More info:

* `ZCML reference <http://docs.zope.org/zope3/ZCML/@@staticmenu.html>`_ (does not include Plone specific directives)

* http://docs.zope.org/zopetoolkit/codingstyle/zcml-style.html

ZCML workflow
==============

Each Plone component (core, add-on) has a base ``configure.zcml`` in the
package root.  This :term:`ZCML` file can include additional nested
configuration files using the ``<include>`` directive.

* ZCML is always interpreted during Plone start-up.

* Your :doc:`unit test </testing_and_debugging/unit_testing>` may need to
  manually include ZCML.

* :doc:`Funny exception error messages occur if Plone is started in the
  production mode and ZCML was not properly read for all the packages
  </troubleshooting/exceptions>`

When Plone is started all ZCML files are read.

* New way: Python egg ``setup.py`` file contains a
  `autoinclude <http://plone.org/products/plone/roadmap/247>`_
  hint and is picked up automatically when all the packages are scanned.

* Old way: ZCML reference must be manually added to the ``zcml = section``
  in ``buildout.cfg``

If ZCML contains errors
:doc:`Plone does not start up in the foreground </troubleshooting/basic>`

Overrides
==========

Besides layer overrides, ZCML provides more hardcore
ways to override things in buildout.
These overrides can also override utilities etc. and overrides take effect
during ZCML parsing, not when site is run.

* Create ``overrides.zcml`` file in your egg to the same folder as ``configure.zcml``

* Syntax is 100% same as in ``configure.zcml``

* Restart Plone.

.. Note::

    Before Plone 3.3, ZCML directives could not be automatically picked up from
    eggs. To make Plone pick up the directions in ``overrides.zcml``, you'd
    have to add this line in ``buildout.cfg``::

      zcml =
          ...
          myegg-overrides

    Since Plone 3.3, the ``z3c.autoinclude`` plugin can do this
    (http://plone.org/products/plone/roadmap/247/).


Specify files and code from another package
===========================================

If you ever find yourself needing to use a template
from another package, you can do so with using the
configure tag which will then run the block of :term:`ZCML`
in the context of that package.

Here is an example of defining portlet manager to be
defined in another manager::

    <configure
        xmlns="http://namespaces.zope.org/zope"
        xmlns:browser="http://namespaces.zope.org/browser"
        i18n_domain="my.package">

        <!-- Moved viewlet registration -->
        <configure package="Products.ContentWellPortlets">
            <browser:viewlet
                name="contentwellportlets.portletsabovecontent"
                class="Products.ContentWellPortlets.browser.viewlets.PortletsAboveViewlet"
                manager="plone.app.layout.viewlets.interfaces.IBelowContentTitle"
                layer="Products.ContentWellPortlets.browser.interfaces.IContentWellPortlets"
                permission="zope2.View"
                template="browser/templates/portletsabovecontent.pt"
            />
        </configure>

    </configure>


Conditionally run :term:`ZCML`
===============================

You can conditionally run :term:`ZCML` if a certain package or feature is
installed.

First, include the namespace at the top of the :term:`ZCML` file::

    <configure
        xmlns="http://namespaces.zope.org/zope"
        xmlns:zcml="http://namespaces.zope.org/zcml"
        i18n_domain="my.package">
    ....

Examples
--------

conditionally run for package::

    <include zcml:condition="installed some.package" package=".package" />
    <include zcml:condition="not-installed some.package" package=".otherpackage" />

conditionally run for feature::

    <include zcml:condition="have plone-4" package=".package" />
    <include zcml:condition="not-have plone-4" package=".otherpackage" />


