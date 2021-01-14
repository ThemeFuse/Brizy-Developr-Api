Icons Picker
============

Icons Picker option type.

Fields
------

+------------+-------------+-------------+------------------------------------------------------------------------------+
| **Name**   |  **Type**   | **Default** | **Description**                                                              |
+============+=============+=============+==============================================================================+
| choices    | ``array``   | `[]`        | Provide a list of icons with id                                              |
|            |             |             ||                                                                             |
|            |             |             || The id will be used to save the selected icon                               |
+------------+-------------+-------------+------------------------------------------------------------------------------+

DefaultValue
------------

+---------------+-------------+-------------------+---------------------------------------------------------------------+
| **Name**      |  **Type**   | **Default**       | **Description**                                                     |
+===============+=============+===================+=====================================================================+
| value         | ``object``  | ``{ value: [] }`` | Any `string` value.                                                 |
+---------------+-------------+-------------------+---------------------------------------------------------------------+


Minimal Usage
-------------

.. code-block:: javascript

    {
      id: "item",
      type: "iconsPicker-dev",
      choices: [
        {
          value: "corner",
          icon: "nc-corners-round",
          title: "Corner"
        },
        {
          value: "bounce",
          icon: "nc-pin",
          title: "Bounce"
        },
        {
          value: "fade",
          icon: "nc-right-arrow-filled",
          title: "Fade"
        },
        {
          value: "corner2",
          icon: "nc-corners-round",
          title: "Corner"
        }
      ]

Usage
-----

.. code-block:: javascript

    {
      id: "test",
      type: "iconsPicker-dev",
      defaultValue: {
        value: "bounce"
      },
      choices: [
        {
          value: "corner",
          icon: "nc-corners-round",
          title: "Corner"
        },
        {
          value: "bounce",
          icon: "nc-pin",
          title: "Bounce"
        },
        {
          value: "fade",
          icon: "nc-right-arrow-filled",
          title: "Fade"
        },
        {
          value: "corner2",
          icon: "nc-corners-round",
          title: "Corner"
        }
      ]
    }
