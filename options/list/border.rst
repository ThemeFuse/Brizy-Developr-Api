Border
============

Border option type.

Config
------

.. |styles| replace:: ``["none", "solid", "dashed", "dotted"]``
.. |widths| replace:: ``["grouped", "ungrouped" ]``

+----------+-------------+-------------+--------------------------------------------------------------------------------+
| **Name** |  **Type**   | **Default** | **Description**                                                                |
+==========+=============+=============+================================================================================+
| opacity  | ``boolean`` | ``true``    | Enable or disable **opacity** slider.                                          |
+----------+-------------+-------------+--------------------------------------------------------------------------------+
| styles   | ``array``   | |styles|    | Provide a list of the supported border styles.                                 |
|          |             |             || Valid styles:                                                                 |
|          |             |             || - ``"none"``                                                                  |
|          |             |             || - ``"solid"``                                                                 |
|          |             |             || - ``"dashed"``                                                                |
|          |             |             || - ``"dotted"``                                                                |
+----------+-------------+-------------+--------------------------------------------------------------------------------+
| width    | ``array``   | |widths|    | Provide a list of the supported border width types.                            |
|          |             |             || Valid width values:                                                           |
|          |             |             || - ``"grouped"``                                                               |
|          |             |             || - ``"ungrouped"``                                                             |
+----------+-------------+-------------+--------------------------------------------------------------------------------+

DefaultValue
------------

+------------+-------------+-------------+------------------------------------------------------------------------------+
| **Name**   |  **Type**   | **Default** | **Description**                                                              |
+============+=============+=============+==============================================================================+
| style      | ``string``  | ``"none"``  | Border style.                                                                |
|            |             |             ||                                                                             |
|            |             |             || Allowed styles:                                                             |
|            |             |             || - ``"none"``                                                                |
|            |             |             || - ``"solid"``                                                               |
|            |             |             || - ``"dashed"``                                                              |
|            |             |             || - ``"dotted"``                                                              |
+------------+-------------+-------------+------------------------------------------------------------------------------+
| hex        | ``string``  | ``#000000`` | Color code in ``HEX`` format.                                                |
+------------+-------------+-------------+------------------------------------------------------------------------------+
| opacity    | ``number``  | ``1``       | Opacity value from ``0`` to ``1``.                                           |
+------------+-------------+-------------+------------------------------------------------------------------------------+
| palette    | ``string``  | ``""``      | Specify specific palette value                                               |
|            |             |             ||                                                                             |
|            |             |             || Allowed palette values:                                                     |
|            |             |             || - ``"color1"``                                                              |
|            |             |             || - ``"color2"``                                                              |
|            |             |             || - ``"color3"``                                                              |
|            |             |             || - ``"color4"``                                                              |
|            |             |             || - ``"color5"``                                                              |
|            |             |             || - ``"color6"``                                                              |
|            |             |             || - ``"color7"``                                                              |
|            |             |             || - ``"color8"``                                                              |
+------------+-------------+-------------+------------------------------------------------------------------------------+
| widthType  | ``string``  | ``grouped`` | Group all border width values under a single value,                          |
|            |             |             | or split them by edge.                                                       |
|            |             |             ||                                                                             |
|            |             |             || Allowed values:                                                             |
|            |             |             || - ``grouped``                                                               |
|            |             |             || - ``ungrouped``                                                             |
+------------+-------------+-------------+------------------------------------------------------------------------------+
| width      | ``number``  | ``0``       | General value for all 4 border edges.                                        |
|            |             |             || This value is used when ``widthType`` is ``grouped``.                       |
+------------+-------------+-------------+------------------------------------------------------------------------------+
| topWidth   | ``number``  | ``0``       | This value modified top border edge.                                         |
|            |             |             || This value is used when ``widthType`` is ``ungrouped``.                     |
+------------+-------------+-------------+------------------------------------------------------------------------------+
| rightWidth | ``number``  | ``0``       | This value modified right border edge.                                       |
|            |             |             || This value is used when ``widthType`` is ``ungrouped``.                     |
+------------+-------------+-------------+------------------------------------------------------------------------------+
| bottomWidth| ``number``  | ``0``       | This value modified bottom border edge.                                      |
|            |             |             || This value is used when ``widthType`` is ``ungrouped``.                     |
+------------+-------------+-------------+------------------------------------------------------------------------------+
| leftWidth  | ``number``  | ``0``       | This value modified left border edge.                                        |
|            |             |             || This value is used when ``widthType`` is ``ungrouped``.                     |
+------------+-------------+-------------+------------------------------------------------------------------------------+

Minimal Usage
-------------

.. code-block:: javascript

    {
      id: "border",
      type: "border"
    }

Usage
-----

.. code-block:: javascript

    {
      id: "border",
      type: "border"
      config: {
        opacity: true,
        styles: ["none", "solid"],
        width: ["grouped"],
      },
      defaultValue: {
        style: "dashed",
        hex: "#000000",
        opacity: 0.5,
        palette: "",
        widthType: "ungrouped",
        width: 1,
        topWidth: 1,
        rightWidth: 1,
        bottomWidth: 1,
        leftWidth: 1,
      }
   }

