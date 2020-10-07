Toggle
======

Toggle option type.

Fields
------

+------------+-------------+--------------+-----------------------------------------------------------------------------+
| **Name**   |  **Type**   | **Requires** | **Description**                                                             |
+============+=============+==============+=============================================================================+
| choices    | ``array``   | ``yes``      | An list of toggle values. Please checkout *Choice structure*.               |
+------------+-------------+--------------+-----------------------------------------------------------------------------+

DefaultValue
-----

+---------------+-------------------+-----------------------------------------------------------------------------------+
| **Name**      |  **Type**         | **Description**                                                                   |
+===============+===================+===================================================================================+
| value         | ``string|number`` | Any ``string`` or ``number`` value.                                               |
+---------------+-------------------+-----------------------------------------------------------------------------------+

Choice structure
----------------

+---------------+-------------------+-----------------------------------------------------------------------------------+
| **Name**      |  **Type**         | **Description**                                                                   |
+===============+===================+===================================================================================+
| value         | ``string|number`` | Specifies choice id. This value should be unique.                                 |
+---------------+-------------------+-----------------------------------------------------------------------------------+
| title         | ``string``        | Specifies choice title.                                                           |
+---------------+-------------------+-----------------------------------------------------------------------------------+
| icon          | ``string``        | Specifies choice icon name.                                                       |
+---------------+-------------------+-----------------------------------------------------------------------------------+


Minimal Usage
-------------

.. code-block:: javascript

    {
      id: "align",
      type: "toggle",
      choices: [
        {
          icon: "nc-text-align-left",
          title: t("Left"),
          value: "left"
        },
        {
          icon: "nc-text-align-center",
          title: t("Center"),
          value: "center"
        },
        {
          icon: "nc-text-align-right",
          title: t("Right"),
          value: "right"
        }
      ]
    },

Usage
-----

.. code-block:: javascript

    {
      id: "align",
      type: "toggle",
      choices: [
        {
          icon: "nc-text-align-left",
          title: t("Left"),
          value: "left"
        },
        {
          icon: "nc-text-align-center",
          title: t("Center"),
          value: "center"
        },
        {
          icon: "nc-text-align-right",
          title: t("Right"),
          value: "right"
        }
      ]
      defaultValue: {
        value: "center",
      }
    },
