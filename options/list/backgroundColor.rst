BackgroundColor
===============

Background color option type with opacity support.

Config
------

+----------+-------------+-------------+--------------------------------------+
| **Name** |  **Type**   | **Default** | **Description**                      |
+==========+=============+=============+======================================+
| opacity  | ``boolean`` | ``true``    | Enable or disable **opacity** slider.|
+----------+-------------+-------------+--------------------------------------+

DefaultValue
------------

+-----------------+-------------+-------------+--------------------------------------+
| **Name**        |  **Type**   | **Default** | **Description**                      |
+=================+=============+=============+======================================+
| type            | ``string``  | ``solid``   | Background type:                     |
|                 |             |             ||                                     |
|                 |             |             || Allowed values:                     |
|                 |             |             || - ``solid``                         |
|                 |             |             || - ``gradient``                      |
+-----------------+-------------+-------------+--------------------------------------+
| gradientType    | ``string``  | ``linear``  | Gradient type:                       |
|                 |             |             ||                                     |
|                 |             |             || Allowed values:                     |
|                 |             |             || - ``linear``                        |
|                 |             |             || - ``radial``                        |
+-----------------+-------------+-------------+--------------------------------------+
| linearDegree    | ``number``  | ``0``       | Linear gradient degree.              |
+-----------------+-------------+-------------+--------------------------------------+
| radialDegree    | ``number``  | ``0``       | Radial gradient degree.              |
+-----------------+-------------+-------------+--------------------------------------+
| hex             | ``string``  | ``#000000`` | Color code in ``HEX`` format.        |
+-----------------+-------------+-------------+--------------------------------------+
| opacity         | ``number``  | ``1``       | Opacity value from ``0`` to ``1``    |
+-----------------+-------------+-------------+--------------------------------------+
| palette         | ``string``  | ``""``      | Specify specific palette value       |
|                 |             |             ||                                     |
|                 |             |             || Allowed palette values:             |
|                 |             |             || - ``"color1"``                      |
|                 |             |             || - ``"color2"``                      |
|                 |             |             || - ``"color3"``                      |
|                 |             |             || - ``"color4"``                      |
|                 |             |             || - ``"color5"``                      |
|                 |             |             || - ``"color6"``                      |
|                 |             |             || - ``"color7"``                      |
|                 |             |             || - ``"color8"``                      |
+-----------------+-------------+-------------+--------------------------------------+
| gradientHex     | ``string``  | ``#000000`` | Color code in ``HEX`` format.        |
+-----------------+-------------+-------------+--------------------------------------+
| gradientOpacity | ``number``  | ``1``       | Opacity value from ``0`` to ``1``    |
+-----------------+-------------+-------------+--------------------------------------+
| gradientPalette | ``string``  | ``""``      | Specify specific palette value       |
|                 |             |             ||                                     |
|                 |             |             || Allowed palette values:             |
|                 |             |             || - ``"color1"``                      |
|                 |             |             || - ``"color2"``                      |
|                 |             |             || - ``"color3"``                      |
|                 |             |             || - ``"color4"``                      |
|                 |             |             || - ``"color5"``                      |
|                 |             |             || - ``"color6"``                      |
|                 |             |             || - ``"color7"``                      |
|                 |             |             || - ``"color8"``                      |
+-----------------+-------------+-------------+--------------------------------------+


Minimal Usage
-------------

.. code-block:: javascript

    {
      id: "",
      type: "backgroundColor",
    }

Usage
-----

.. code-block:: javascript

    {
      id: "color",
      type: "backgroundColor",
      config: {
        opacity: false,
      },
    }
