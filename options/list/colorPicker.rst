Color Picker
============

Color picker option type with opacity support.

Config
------

+----------+-------------+-------------+--------------------------------------+
| **Name** |  **Type**   | **Default** | **Description**                      |
+==========+=============+=============+======================================+
| opacity  | ``boolean`` | ``true``    | Enable or disable **opacity** slider.|
+----------+-------------+-------------+--------------------------------------+

Value
-----

+----------+-------------+-------------+--------------------------------------+
| **Name** |  **Type**   | **Default** | **Description**                      |
+==========+=============+=============+======================================+
| hex      | ``string``  | ``#000000`` | Color code in ``HEX`` format.        |
+----------+-------------+-------------+--------------------------------------+
| opacity  | ``number``  | ``1``       | Opacity value from ``0`` to ``1``    |
+----------+-------------+-------------+--------------------------------------+
| palette  | ``string``  | ``""``      | Specify specific palette value       |
|          |             |             || Allowed palette values:             |
|          |             |             ||                                     |
|          |             |             || - ``"color1"``                      |
|          |             |             || - ``"color2"``                      |
|          |             |             || - ``"color3"``                      |
|          |             |             || - ``"color4"``                      |
|          |             |             || - ``"color5"``                      |
|          |             |             || - ``"color6"``                      |
|          |             |             || - ``"color7"``                      |
|          |             |             || - ``"color8"``                      |
+----------+-------------+-------------+--------------------------------------+


Minimal Usage
-----

.. code-block:: javascript

    {
      id: "color",
      type: "colorPicker",
    }

Usage
-----

.. code-block:: javascript

    {
      id: "color",
      type: "colorPicker",
      config: {
        opacity: false,
      },
      value: {
        hex: "#333333",
        opacity: 0.5,
        palette: ""
      }
    }
