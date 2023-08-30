==========
Pricelists
==========

The pricelist feature in Point of Sale allows you to adjust product prices based on predefined
criteria.

This feature can be employed for a designated duration, like a temporary sale on products within a
particular PoS category, for specific users, or as a reward when customers meet certain conditions,
such as a minimum purchase quantity or amount.

Configuration
=============

Start by **activating** the pricelist feature. To do so, reach the :ref:`general PoS app's settings
<configuration/settings>` and enable :guilabel:`Pricelists` in the :guilabel:`Pricing` section.

.. note::
   The feature can already be available in Point of Sale if it was previously enabled in the
   :doc:`Sales <../../sales/products_prices/prices/pricing>` or :ref:`Website
   <multi_website/pricelists>` apps.

Then, select the type of pricelist by checking :guilabel:`Multiple prices per product` or
:guilabel:`Advanced price rules (discounts, formulas)`, save, and click :guilabel:`Pricelists` to
create new ones or modify existing ones.

.. image:: pricelists/settings.png
   :alt: enabling the pricelists feature in the general PoS' settings.

.. note::
   Alternatively, you can go to :menuselection:`Point of Sales --> Products --> Pricelists` to reach
   the previous screen.

Create pricelists
=================

Click :guilabel:`Create` or select an existing pricelist. The pricelist setup form differs depending
on the chosen type of pricelist.

.. tabs::
   .. tab:: Multiple prices per product

      This type of pricelist requires selecting a product for which you can attribute one or
      multiple other prices. To do so,

      #. click :guilabel:`Add a line` and select a product;
      #. add conditions such as a specific quantity to reach for the price to change in the
         :guilabel:`Min. Quantity` column or a determined period during which the pricelist
         can be applied in the :guilabel:`Start Date` and :guilabel:`End Date` columns;
      #. filter the pricelist to be set on one specific variant of the selected product in the
         :guilabel:`Variants` column.

      .. image:: pricelists/multiple-prices.png
         :alt: setup form of a multiple prices pricelist.

      .. note::
         - Conditions and filters are optional. You can leave these columns empty to use a pricelist
           without conditions.
         - Pricelists can be selected if the conditions are unmet, but the computation will not be
           applied.

   .. tab:: Advanced price rules

      To set up this type of pricelist, click :guilabel:`Add a line` and select one of the three
      available computations on the pop-up window:

      - Select :guilabel:`Fixed Price` to attribute another price to the designated product(s).
      - Select :guilabel:`Discount` to attribute a discount to the designated product(s).
      - Select :guilabel:`Formula` to compute the prices according to a formula that combines
        multiple computations:

        - Define what the calculation is based on (the :guilabel:`Sales Price`, the
          :guilabel:`Cost`, or an :guilabel:`Other Pricelist`.)
        - Apply a :guilabel:`Discount` and/or add an :guilabel:`Extra Fee`.
        - Define a :guilabel:`Rounding Method` and specify the minimum amount of **margin**
          over the base price *(optional)*.

      Then, select the products you want to apply this computation to:

      - :guilabel:`All Products`
      - a :guilabel:`Product Category`
      - a specific :guilabel:`Product`
      - a specific :guilabel:`Product Variant`

      And add conditions such as a specific quantity to reach for the price to change in the
      :guilabel:`Min. Quantity` field or a specific period of time during which the pricelist can
      be applied in the :guilabel:`Validity` fields.

      .. image:: pricelists/price-rules.png
         :alt: setup form to configure an advanced pricelist

      .. note::
         Pricelists can be selected if the conditions are unmet, but the computation will not be
         applied.

Once pricelists are created, go to the :ref:`POS settings <configuration/settings>` and select
either one pricelist in the :guilabel:`Default Pricelist` field or tick the :guilabel:`Advanced
Pricelists` checkbox and fill in the :guilabel:`Available` field with all the desired pricelists.

.. note::
   All available pricelists must be in the same currency as the company or the **Sales Journal** set
   on the selected point of sale.

Use pricelists
==============

:ref:`Open a POS session <pos/session-start>`, click the **pricelists** button, and select the
desired pricelist from the list.

.. image:: pricelists/pricelist-button.png
   :alt: button to select a pricelist on the pos frontend

You can also set a pricelist to be selected automatically once a specific :ref:`customer is set
<pos/customers>`. To do so, go to the customer form and switch to the preferred pricelist on the
:guilabel:`Pricelist` field of the :guilabel:`Sales & Purchase` tab.

.. seealso::
   - :doc:`../../sales/products_prices/prices/pricing`
   - :ref:`multi_website/pricelists`
