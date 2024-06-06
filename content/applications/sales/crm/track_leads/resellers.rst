=========
Resellers
=========

Within Odoo's *CRM* app, leads can be forwarded to resellers (or partners). Leads can be manually
assigned, or automatically assigned based on the resellers designated *level*, and location.

Configuration
=============

To utilize the reseller features, the *Resellers* module first needs to be installed. Navigate to
the :menuselection:`Apps` application, and remove the :guilabel:`Apps` filter from the
:guilabel:`Search...` bar. Then search for `Resellers`.

.. image:: resellers/resellers-module.png
   :align: center
   :alt: The resellers module in Odoo.

After the module is installed, navigate to the :menuselection:`CRM app`. Under the
:menuselection:`Configuration` menu is a new section, titled :guilabel:`Resellers`.

Partner levels
==============

Partner *levels* are used to differentiate between various resellers. To view the partner levels,
navigate to :menuselection:`CRM app --> Configuration --> Partner Levels`.

Three levels are created by default in the *CRM* app:

- :guilabel:`Gold`
- :guilabel:`Silver`
- :guilabel:`Bronze`

New levels can be added, as needed, and the existing levels can be edited and renamed, if desired.

.. image:: resellers/partners-webpage.png
   :align: center
   :alt: An example of the partners webpage, displaying available partners by level and location.

Level weight
------------

Level weight is used to decide the probability a partner to be assigned a lead or opportunity. To
define a level weight, go to :menuselection:`(insert navigation instructions)` and click the desired
partner level. Then, in the :guilabel:`Level Weight` field, assign a numerical value, greater than
zero to it. If the weight is zero, no leads are assigned.

.. tip::
   Level weight can be assigned on an individual contact record. The weight assigned on the
   individual record overwrites the default weight assigned on the level configuration form.

.. _crm/partner-activations:

Partner activations
===================

Partner *activations* are used to identify the status of a partner. Activations are assigned on an
individual contact record, and can be used to group or filter the :guilabel:`Partnership Analysis`
report. To view the partner levels, navigate to :menuselection:`CRM app --> Configuration -->
Partner Activations`.

Three activation types are created by default in the *CRM* app:

- :guilabel:`Fully Operational`
- :guilabel:`Ramp-up`
- :guilabel:`First Contact`

New levels can be added, as needed, and the existing levels can be edited and renamed, if desired.
To change the active status of an activation, slide the toggle of the desired activation to the
*inactive* position.

.. figure:: resellers/activations-toggle.png
   :align: center
   :alt: The list of default partner activations in the CRM app.

   The list of default Partner Activations in the CRM app. The toggle for First Contact is in the
   inactive position, while the rest are active.

Partner assignments
===================

After partner levels and partner activations have been configured, individual partner records can be
configured.

To update an individual partner record, navigate to :menuselection:`CRM app --> Sales -->
Customers`, and click the Kanban card for the desired partner to open the customer record.

On the customer record, click the :guilabel:`Partner Assignment` tab.

Click the :guilabel:`Partner Level` field, and select an option from the drop-down menu to assign a
level. Select a :guilabel:`Partner Activation` type from the drop-down list, if desired. Then, click
the :guilabel:`Level Weight` field to assign a different level weight, if necessary.

Publish partners
================

With the Odoo *Website* app installed, a new webpage can be created to display a list of all active
partners from the *CRM* app. Navigate to :menuselection:`Website app --> Site --> Pages` and click
:guilabel:`New`. Hover over the :guilabel:`Blank Page` template, and click the :guilabel:`Use this
template` button to create a new page.

.. image:: resellers/blank-page-template.png
   :align: center
   :alt: The create new page pop-up in the Website app.

In the :guilabel:`New Page` pop-up window, enter a :guilabel:`Page Title`, e.g. `Partners`. Then
click :guilabel:`Create`. In the :guilabel:`Edit` toolbar on the far right of the page, click
:guilabel:`Save`.

Next, return to :menuselection:`CRM app --> Sales --> Customers`, and click the Kanban card for a
partner. From that partner's contact form, click the :guilabel:`Go to Website` smart button at the
top of the page to open that partner's webpage.

Next, click :guilabel:`Edit` at the top-right of the partner's webpage, and use the :doc:`building
blocks <../../../websites/website/web_design/building_blocks>` to add any additional design
elements, or information about the partner.

.. tip::
  A company summary is a useful addition to this page.

After making any necessary changes to the page, click :guilabel:`Save`. At the top of the page,
slide the :guilabel:`Unpublished` toggle to the active, :guilabel:`Published` position.

Repeat these steps for all partners.
