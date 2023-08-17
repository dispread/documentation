============
Mercado Pago
============

`Mercado Pago <https://www.mercadopago.com/>`_ is an online payment provider covering several
countries, currencies and payment methods in Latin America.

Odoo is integrated with `Mercado Pago Checkout Pro
<https://www.mercadopago.com.ar/developers/en/docs/checkout-pro/landing/>`: The buyer is directed to
a Mercado Pago page where they complete the transaction securely and quickly.

.. _payment_providers/mercado_pago/configure_dashboard:

Configuration on Mercado Pago Dashboard
=======================================

#. Log into `Mercado Pago Dashboard <https://www.mercadopago.com.mx/developers/panel>`_ and go to
   your **Application** or *create* a new one.
#. Go to :menuselection:`Production Credentials` or :menuselection:`Credentials` if you are in a
   *Test* environment and copy your **Access Token**

.. image:: mercado_pago/mp-credentials.png
   :alt: Production and Testing credentials.

.. _payment_providers/mercado_pago/configure_odoo:

Configuration on Odoo
=====================

#. :ref:`Navigate to the payment provider Mercado Pago <payment_providers/add_new>` and change its
   state to :guilabel:`Enabled`.
#. In the :guilabel:`Credentials` tab, fill the :guilabel:`Access Token` with the value you saved at
   the step :ref:`payment_providers/mercado_pago/configure_dashboard`.

.. image:: mercado_pago/mercadopago-access-token.png
   :alt: Access Token configuration for Mercado Pago.

#. In the :guilabel:`Configuration` tab, select the payment journal from one of your existing type
   Bank journals.
#. Configure the rest of the options to your liking.

.. important::
   Mercado Pago functions correctly with the :guilabel:`Enabled` status activated for Production and
   Testing purposes. For this payment provider the *Test Mode* configuration in Odoo will result in
   an error message.

.. seealso::
   - :doc:`../payment_providers`
