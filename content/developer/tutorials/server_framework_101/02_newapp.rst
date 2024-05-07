.. todo: update title?

==============================
Chapter 2: Lay the foundations
==============================

.. todo introduction text

Install the app
===============

If you followed the :doc:`setup guide <../setup_guide>` carefully, you should now have a running
Odoo server with the `odoo/tutorials` repository in the `addons-path`, and be logged in as an
administrator.

**Let's install our real estate app!** In your browser, open Odoo and navigate to
:menuselection:`Apps`. Search for :guilabel:`Real Estate` and click :guilabel:`Activate`.

Nothing has changed? That's normal; the `real_estate` module we just installed is currently an empty
shell. It doesn't even have a menu entry. Currently, it only contains two files:

- An empty :file:`__init__.py` file to make Python treat the :file:`real_estate` directory as a
  package.
- The :file:`__manifest__.py` file that declares the :file:`real_estate` Python package as an Odoo
  module.

Those two files are the minimum requirements for a directory to be considered an Odoo module.

.. exercise::
   Search for each key of the :file:`real_estate/__manifest__.py` file in the :ref:`reference
   documentation <reference/module/manifest>` and understand the base metadata that defines the
   `real_estate` module.

.. seealso::
   `The manifest file of the Sales app <{GITHUB_PATH}/addons/sale/__manifest__.py>`_

Create the first model
======================

Now that our module is recognized by Odoo, it's time to build towards the business features. Data is
essential for any real-world application, and our real estate module won't be an exception.

To store data effectively, we need two things: a way to define the structure of that data, and a
system to store and manipulate it. Fortunately, the server framework of Odoo comes equipped with the
perfect tool: the :abbr:`ORM (Object Relational Mapper)` layer.

The ORM simplifies data access and manipulation by allowing you to define **models**. Models act as
blueprints for your data; they define the structure and organization of information within your
module. You can see them as templates that specify what kind of data your module will handle. For
example, real estate properties, owners, or tenants.

Each model is made of smaller components called **fields**. You can see them as the individual
characteristics that describe your data. Fields allow you to define the relevant data your
application needs to capture and manage. In the case of real estate properties, some example fields
could be the property name, the type (house, apartment, etc.), and the floor area.

In Odoo, models are represented by Python classes that inherit from the `odoo.models.Model` class
provided by the ORM, and they are identified by their `_name` attribute. Within these model classes,
fields are defined as class attributes. Each field is an instance of a class from the `odoo.fields`
package. For example, `Char`, `Float`, `Boolean`, each designed to handle different types of data.

When defining a field, developers can pass various arguments to finely control how data is handled
and presented in Odoo. For example, `string` defines the label for the field in the user interface,
and `required` makes filling the field in mandatory.

For the full list of fields and their attributes, see the :ref:`reference documentation
<reference/orm/fields>`.

.. example::
   Before we dive into creating our own models, let's take a look at a basic example of a model that
   represents products:

   .. code-block:: python

      from odoo import fields, models


      class Product(models.Model):
          _name = 'product'

          name = fields.Char(string="Name", required=True)
          description = fields.Text(string="Description")
          price = fields.Float(string="Sale Price", required=True)
          category = fields.selection(
              string="Category",
              selection=[
                  ('apparel', "Clothing")
                  ('electronics', "Electronics"),
                  ('home_decor', "Home Decor"),
              ],
              required=True,
              default='apparel',
          )

.. todo: add exercise to create the real.estate.property model
.. todo: show the impact on SQL: table, columns
.. todo: add introduction to actions, menus, views
.. todo: add exercise to create necessary records to browse Properties

----

.. todo: add incentive to move to the next chapter
