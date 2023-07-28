=========================
Engineering change orders
=========================

.. |BOM| replace:: :abbr:`BoM (Bill of Materials)`
.. |BOMs| replace:: :abbr:`BoMs (Bills of Materials)`
.. |ECO| replace:: :abbr:`ECO (Engineering Change Order)`
.. |ECOs| replace:: :abbr:`ECOs (Engineering Change Orders)`

.. _plm/eco:

Utilize *Engineering Change Orders* (*ECOs*) to track and implement changes to products, and
:ref:`bills of materials <manufacturing/management/bill-configuration>`.

View and create :abbr:`ECOs (engineering change orders)` within each *ECO type*, a project pipeline
in Gantt view with stages, ensuring progress tracking for collaborators and stakeholders.

Engineering change orders can be created:

#. :ref:`directly in the ECO type <plm/eco/create-eco>`
#. by an operator in the :ref:`tablet view <plm/eco/tablet-view>` of an operation
#. automatically from feedback submitted to the :ref:`ECO type's email alias <plm/eco/eco-type>`.

.. _plm/eco/create-eco:

Create new ECO
==============

To create a new |ECO|, begin by navigating to the :menuselection:`PLM app`, and select the ECO type
card that will be used to track the progress of the change. On the :guilabel:`Engineering Change
Orders` page, click on the :guilabel:`New` button in the top-left corner.

.. note::
   Learn how to create new :ref:`ECO types <plm/eco/eco-type>` to categorize and organize change
   orders. Doing so ensures employees only view the |ECOs| related to their responsibilities,
   whether it involves new product introductions, targeted product line updates, or regulatory
   compliance fulfillment)

On the |ECO| form, type in a short :guilabel:`Description` of the change, and select the
:guilabel:`Product` from the drop-down field. In the :guilabel:`Apply on` field, select either the
:guilabel:`Bill of Materials` or :guilabel:`Product Only` radio selection options.

Optionally, set a particular deadline for the completion of the change with an :guilabel:`Effective`
date, or add :guilabel:`Tags` for categorization.

Finally, click :guilabel:`Start Revision` after filling out the form to begin implementing the
changes. Clicking the button unveils the stages of the ECO type, the :guilabel:`Documents` smart
button, the :guilabel:`Revision` smart button, and the new |BOM| version number.

.. note::
   The :guilabel:`Revision` smart button is available only when the :guilabel:`Bill of Materials`
   radio button is selected in the :guilabel:`Apply on` field and the :guilabel:`Smart Revision` is
   activated.

.. image:: engineering_change_orders/eco-form.png
   :align: center
   :alt: Active ECO with overview of stages in the top right, and *Revision* smart button.

Change components
-----------------

To modify the components in a |BOM|, click the :guilabel:`Revision` smart button on an active |ECO|
to access the new version of the |BOM|. Odoo distinguishes the non-production version of the |BOM|
from the current version, by flagging the test |BOM| with a large :guilabel:`Archived` tag.

On the new |BOM|, switch to the :guilabel:`Components` tab. Modify the components list by changing
the :guilabel:`Quantity` of existing components, add new components using the :guilabel:`Add a line`
button, and remove components with the :guilabel:`🗑️ (trash)` icon.

.. _plm/eco/example-keyboard:

.. example::
   In version two of the |BOM| for a keyboard, the component quantities are reduced, and an
   additional component, `Stabilizers`, is added.

   .. image:: engineering_change_orders/version-2-BOM.png
      :align: center
      :alt: Make changes to components by going to the new BoM with the *Revision* smart button.

Once the changes are complete, navigate back to the |ECO| itself, by clicking `ECO00X` in the
breadcrumbs in the top-left corner. On the |ECO| form, a new :guilabel:`BoM Changes` tab displays
the differences between the current |BOM| and the new version.

This ensures changes and tests are encapsulated in the revised |BOM| and do not affect the |BOM|
currently used in production. That is, until the :ref:`changes are applied <plm/eco/apply-changes>`.

.. example::
   View the summary of the differences between the current and revised keyboard |BOMs| in the
   :guilabel:`BoM Changes` tab of the |ECO|.

   .. image:: engineering_change_orders/BoM-changes.png
      :align: center
      :alt: View summary of component changes in the *BoM Changes* tab.

Change operations
=================

To modify the operations in a |BOM|, click the :guilabel:`Revision` smart button on an active |ECO|
to access the archived, new version of the |BOM|.

In the new |BOM| version, switch to the :guilabel:`Operation Changes` tab, and make changes to the
operations, by selecting each operation line item, and opening the corresponding :guilabel:`Open:
Operations` pop-up window.

Make changes to any of the fields in the pop-up window, and click :guilabel:`Save` once completed.

Create new operations by clicking the :guilabel:`Add a line` button, and remove new operations by
clicking the :guilabel:`Archive` button.

.. note::
   The :guilabel:`Operations` tab is *not* available by default. To enable it, navigate to
   :menuselection:`Manufacturing app --> Configuration --> Settings`, and check the :guilabel:`Work
   Orders` box.

Once the changes are complete, navigate back to the |ECO| itself, by clicking `ECO00X` in the
breadcrumbs in the top-left corner.

On the |ECO| form, a new :guilabel:`Operation Changes` tab displays the differences between the
current production |BOM| and the new version. Modifications to the |BOM| in an |ECO| will *not*
affect the |BOM| used in production. That is, until the :ref:`changes are applied
<plm/eco/apply-changes>`.

.. _plm/eco/apply-changes:

Apply changes
=============

After verifying the changes, move the |ECO| to a :ref:`verification stage <plm/eco/stage-config>`.
Once the approvers accept the changes, the :guilabel:`Apply Changes` button becomes available. Click
this button, and the |ECO| is automatically closed, and the changes are applied.

To ensure the changes are live, navigate to the :guilabel:`Revision` smart button.

The |BOM| will have the large red :guilabel:`Archived` tag removed. Additionally, navigate to the
product form, switch to the :guilabel:`Miscellaneous` tab, and the :guilabel:`Version` field will be
updated to match the version number shown on the :guilabel:`Revision` smart button of the latest
|ECO|.

.. example::
   After applying the changes of the |ECO| for the :ref:`keyboard <plm/eco/example-keyboard>`, view
   the version of the current keyboard |BOM| in the :guilabel:`Miscellaneous` tab. Here, the
   :guilabel:`Version` number has been updated to `2`, matching the `V2` that appears in the
   :guilabel:`Revision` smart button of the |ECO|.

   .. image:: engineering_change_orders/BOM-version.png
      :align: center
      :alt: View current *BOM* version in the Miscellaneous tab.

.. _plm/eco/tablet-view:

Create ECO from tablet view
===========================

|ECOs| created in *tablet view* are intended for operators to directly suggest clearer operation
instructions. To create an |ECO|, navigate to the :guilabel:`Work Orders` tab on an ongoing
manufacturing order. Then, click the :guilabel:`tablet icon` for the desired work order to open the
tablet view of the operation.

.. image:: engineering_change_orders/tablet-icon.png
   :align: center
   :alt: Find the tablet icon for each operation, second from the far right.

Next, add an instructional step, by clicking the :guilabel:`☰ (three horizontal lines)` icon in the
tablet view of an operation. Then, click the :guilabel:`Add a step` button.

.. image:: engineering_change_orders/additional-options-menu.png
   :align: center
   :alt: Navigate to the "Add a Step" pop-up by clicking the three horizontal lines icon in tablet
         view.

In the :guilabel:`Title` field, enter a short step description. Next, in the
:guilabel:`Instructions` text field, type the instructions of the step in greater detail.
Optionally, add an image to the :guilabel:`Document` field. Once completed, finish by clicking the
:guilabel:`Propose Change` button.

.. example::
   To propose an additional check for broken components, enter the details in the :guilabel:`Add a
   Step` pop-up window. Doing so creates an instructional quality control point that will be
   reviewed in the following section.

   .. image:: engineering_change_orders/add-a-step.png
      :align: center
      :alt: Fill out the *Add a Step* form to suggest an additional quality control point.

View ECO
--------

To review the proposed changes, go to the `BOM Changes` ECO type from :menuselection:`PLM app -->
Overview`, and click on the card to view the contained |ECOs|. Click on the newly created |ECO| in
the `New` stage, and view a summary of the proposed changes in the :guilabel:`Operation Changes`
tab. To implement the changes, click the :guilabel:`Revision` smart button.

.. example::
   An |ECO| adding another check for broken components is created in the `BOM Changes` ECO type
   found in :menuselection:`PLM app --> Overview`. By default, |ECOs| created from tablet view are
   named with the manufacturing order number for reference.

   .. image:: engineering_change_orders/view-BOM-change.png
      :align: center
      :alt: Find the new ECO in the "BOM Changes" ECO type, in the *New* stage.

On the new |BOM|, switch to the :guilabel:`Operations` tab, and select the :guilabel:`☰ (Show
Instructions)` icon. Doing so opens a list of :guilabel:`Steps` to perform the operation, with the
newest instruction titled `New Step Suggestion:`, followed by the user-entered title. Click the line
item to view the suggested changes.

.. image:: engineering_change_orders/show-instructions.png
   :align: center
   :alt: "Show Instructions" icon in the *Operations* tab of a BoM.

On the :ref:`quality control point <quality/quality_control_points>` form, ensure the following form
fields are accurately filled out to give detailed instructions for operators:

- :guilabel:`Title`: rename to give a concise description of the new instruction
- :guilabel:`Control per`: using the drop-down menu, determine whether this instruction applies
  broadly for the :guilabel:`Product`, specifically for this :guilabel:`Operation` *only*, or a
  particular :guilabel:`Quantity` of the product
- :guilabel:`Type`: categorizes the control point type. From the drop-down menu, select
  :guilabel:`Instructions` to detail an instruction for the worker. To receive input from the
  workers, select the :guilabel:`Take a Picture`, :guilabel:`Register Consumed Materials`,
  :guilabel:`Print Label`, or other :ref:`quality check options <quality/quality_control_points>`.

Once the quality control point is configured, return to the :guilabel:`Steps` list using the
breadcrumbs. Finally, drag the last quality control line item to its intended order of instructions.

.. example::
   Drag and reorder the `Check for broken switches` instruction, by clicking and dragging its "6
   dots" icon to move it from the bottom to the second position.

   .. image:: engineering_change_orders/reorder.png
      :align: center
      :alt: Drag and reorder instructions by selecting the "6 dots" icon on the far left.

.. _plm/eco/eco-type:

Create ECO type
===============

To access and manage ECO types, navigate to :menuselection:`PLM app --> Configuration --> ECO
Types`.

Create a new ECO type by clicking :guilabel:`New`, and fill in the :guilabel:`Name`. The
:guilabel:`Email Alias` field is optional, but feedback submitted to the filled-in email address
will automatically create an |ECO| in this ECO type.

Modify existing ECO type names and email aliases by clicking on the respective ECO type in the list.

Existing ECO types are displayed in the task form, on the :guilabel:`PLM Overview` page, which is
accessible by navigating to :menuselection:`PLM app --> Overview`.

.. _plm/eco/stage-config:

Stage configuration
-------------------

Click an ECO type from :menuselection:`PLM app --> Overview` to open a kanban view of |ECOs| of this
type.

In the pipeline, ensure there is at least one *verification* stage, where |ECO| changes can be
applied, and a *closing stage*, for storing completed |ECOs|.

To configure a stage, hover over the intended stage, and select the :guilabel:`⚙️ (gear)` icon.
Then, click :guilabel:`Edit` to open a pop-up window.

Configure the verification stage in the edit stage pop-up window, by checking the box for
:guilabel:`Allow to apply changes`.

Optionally, add :guilabel:`Approvals` to automatically notify people to verify the changes before
they go live. Once finished, select the :guilabel:`Save & Close` button.

.. example::

   The stage titled, `Validated,` is intended to store |ECOs| that will be reviewed by the main
   approver (the engineering manager) before the changes are applied to production. To reflect this,
   the engineering manager is listed in the :guilabel:`Approvals` section. Additionally, the
   :guilabel:`Allow to apply changes` option is checked.

   .. image:: engineering_change_orders/verification-stage.png
      :align: center
      :alt: Show "Allow to apply changes" option is checked.

Next, hover over the closing stage, and select the corresponding :guilabel:`⚙️ (gear)` icon to open
the edit stage pop-up window. Ensure that the :guilabel:`Folded in kanban view`, :guilabel:`Allow to
apply changes`, and :guilabel:`Final Stage` options are checked.

.. image:: engineering_change_orders/closing-stage.png
   :align: center
   :alt: Show configurations of the closing stage.

