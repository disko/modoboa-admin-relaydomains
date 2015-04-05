.. modoboa-admin-relaydomains documentation master file, created by
   sphinx-quickstart on Sun Apr  5 14:11:51 2015.
   You can adapt this file completely to your liking, but it should at least
   contain the root `toctree` directive.

Welcome to modoboa-admin-relaydomains's documentation!
======================================================

This extension adds the support for relay domains using postfix. You
can use it when the MTA managed by Modoboa is not the final
destination of one or several domains.

If activated, two new objects will be available from the *Domains*
listing page: *relay domain* and *relay domain alias*.

The extension is compatible with the *amavis* and *limits*
ones. Resellers will be able to create both new objects.

Contents:

.. toctree::
   :maxdepth: 2

   setup
