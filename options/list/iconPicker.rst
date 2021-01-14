Icon Picker
===========

Icon Picker option type.

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

+---------------+-------------+-------------+---------------------------------------------------------------------------+
| **Name**      |  **Type**   | **Default** | **Description**                                                           |
+===============+=============+=============+===========================================================================+
| value         | ``string``  | ``""``      | Any `string` value.                                                       |
+---------------+-------------+-------------+---------------------------------------------------------------------------+


Minimal Usage
-------------

.. code-block:: javascript

    {
      id: "item",
      type: "iconPicker-dev",
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
      type: "iconPicker-dev",
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
