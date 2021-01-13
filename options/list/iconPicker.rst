Icon Picker
===========

Icon Picker option type.

Config
------

+------------+-------------+-------------+------------------------------------------------------------------------------+
| **Name**   |  **Type**   | **Default** | **Description**                                                              |
+============+=============+=============+==============================================================================+
| icons      | ``array``   | `[]`        | Provide a list of icons with id                                              |
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
      config: {
        icons: [
          {
            id: "corner",
            icon: "nc-corners-round",
            title: "Corner"
          },
          {
            id: "bounce",
            icon: "nc-pin",
            title: "Bounce"
          },
          {
            id: "fade",
            icon: "nc-right-arrow-filled",
            title: "Fade"
          }
        ]
      }
    }

Usage
-----

.. code-block:: javascript

    {
      label: "Pick item",
      id: "item",
      type: "iconPicker-dev",
      defaultValue: {
        value: "bounce"
      },
      config: {
        icons: [
          {
            id: "corner",
            icon: "nc-corners-round",
            title: "Corner"
          },
          {
            id: "bounce",
            icon: "nc-pin",
            title: "Bounce"
          },
          {
            id: "fade",
            icon: "nc-right-arrow-filled",
            title: "Fade"
          }
        ]
      }
    }
