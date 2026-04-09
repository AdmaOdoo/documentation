.. _pos/invoices/invoices:

========
Invoices
========

Point of Sale allows for :ref:`generating <pos/invoices/generate>` invoices for
:ref:`registered customers <pos/use/customers>` upon payment, :ref:`retrieving
<pos/invoices/retrieve>` all past invoiced orders, and :ref:`self-scanning and downloading
<pos/invoices/qr-codes>` an invoice from a QR code or URL.

.. note::
   An invoice created in a POS creates an entry into the corresponding :ref:`accounting journal
   <cheat_sheet/journals>` :ref:`configured in the POS settings <pos/invoices/configuration>`.

.. _pos/invoices/configuration:

Configuration
=============

To define the default journals for a specific POS, go to :menuselection:`Point of Sale -->
Configuration --> Settings`, scroll down to the :guilabel:`Accounting` section, and select the
appropriate journals for :guilabel:`Orders` and :guilabel:`Invoices` under :guilabel:`Default
Journals`. To modify the selected default journal, click the :icon:`fa-arrow-right`
(:guilabel:`Internal link`) icon.

.. note::
   Specific journals can also be defined for each :doc:`payment method <../payment_methods>`.

.. seealso::
   :doc:`/applications/finance/accounting/get_started/journals`

.. _pos/invoices/generate:

Invoice generation
==================

To create and send an invoice to a customer from the :ref:`Orders overview <pos/use/orders>`, follow
these steps:

#. Click the :guilabel:`Active` dropdown menu and select :guilabel:`Paid`.
#. Select the relevant order and click :icon:`fa-file-pdf-o` :guilabel:`Invoice` above the numpad.
#. Click :guilabel:`Ok` in the popover, then select or :ref:`create a customer <pos/use/customers>`.

.. tip::
   To reprint the invoice, select the relevant order and click :icon:`fa-file-pdf-o`
   :guilabel:`Reprint Invoice` above the numpad.

.. note::
   To issue an invoice from the backend, go to :menuselection:`Point of Sale --> Orders --> Orders`,
   select the relevant order, add a customer in the :guilabel:`Customer` field, then click
   :guilabel:`Invoice`.

To create and send an invoice to a customer on the :ref:`Payment <pos/use/sell>` screen, follow
these steps:

#. Enable :icon:`fa-file-text-o` :guilabel:`Invoice`.
#. Click :icon:`fa-user` :guilabel:`Customer`, then select or :ref:`create a customer
   <pos/use/customers>`.
#. Select a :doc:`payment method <../payment_methods>` and click :guilabel:`Validate`.

The invoice is automatically issued and downloaded. To simultaneously send the receipt and the
invoice from the :ref:`Receipt <pos/configuration/receipts>` screen, click the
:icon:`fa-paper-plane` (:guilabel:`send`) button next to the customer's email address.

.. tip::
   Alternatively, :ref:`assign a customer to an order <pos/use/customers>` from the POS register
   to issue the invoice upon payment.

To generate a single global invoice for all orders linked to the same customer that are not yet
invoiced (i.e., invoices with an :guilabel:`Invoice Status` set to :guilabel:`To Invoice`), follow
these steps:

#. Go to :menuselection:`Point of Sale --> Orders --> Customers`.
#. Click the customer's :guilabel:`Name`.
#. Click the :icon:`fa-shopping-bag` (:guilabel:`PoS Orders`) smart button on the customer form.
#. Select the relevant orders, click :guilabel:`Create Invoices`, then :guilabel:`Create`.

.. tip::
   Alternatively, go to :menuselection:`Point of Sale --> Orders --> Orders`, select the relevant
   orders, click :guilabel:`Create Invoices`, then :guilabel:`Create`.

.. seealso::
   `Receipts and Invoices (video tutorial) <https://youtu.be/w_DKgHcIV0U?si=Gnf6untzAz2zvNku>`_

.. _pos/invoices/retrieve:

Invoice retrieval
=================

Retrieving invoices is useful for customer requests and accounting purposes, for example. To view,
download, reprint, or send past transactions, follow these steps:

#. Go to :menuselection:`Point of Sale --> Orders --> Orders`.
#. Click the relevant order in the list.
#. Click the :guilabel:`Invoice` smart button on the order form to access the invoice.
#. Click the following buttons to manage the invoice:

   - :guilabel:`Send`: Send or resend the invoice.
   - :guilabel:`Print`: Open the browser's print function or download the invoice.
   - :guilabel:`Preview`: Preview and download the invoice.
   - :guilabel:`Credit Note`: Issue a :ref:`credit note <accounting/credit_notes/issue-credit-note>`
     to a customer.
   - :guilabel:`Reset to Draft`: Reset the invoice to draft if changes are needed.

.. seealso::
   :doc:`/applications/finance/accounting/customer_invoices`

.. _pos/invoices/qr-codes:

Invoice generation via QR codes
===============================

To allow customers to request an invoice by scanning a QR code printed on their :ref:`receipt
<pos/configuration/receipts>`, follow these steps:

#. Go to :menuselection:`Point of Sale --> Configuration --> Settings`.
#. Scroll down to the :guilabel:`Bills & Receipts` section.
#. Enable the :guilabel:`Self-service invoicing` setting.
#. Set the :guilabel:`Print` field to :guilabel:`QR code`, :guilabel:`URL`, or :guilabel:`QR code +
   URL` to determine how customers can access their invoice (e.g., by scanning the QR code or by
   typing the URL in a browser).

Upon scanning the QR code or typing the URL in a browser, customers must fill in a form with the
information on the receipt (i.e., the :guilabel:`Ticket Number`, :guilabel:`Date`, and
:guilabel:`Unique code`), then click :guilabel:`Request Invoice`. Additionally, customers must enter
their billing information or sign in and click :guilabel:`Get my invoice`. The invoice is then
generated and available for download, and the order status in the :guilabel:`Orders` view is updated
to :guilabel:`Fully Invoiced`.
