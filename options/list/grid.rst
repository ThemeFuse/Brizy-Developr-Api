Grid
====

Create vertical options grid

Config
------

+------------+-------------------+-----------------+--------------------------------------------------------------------+
| **Name**   |  **Type**         | **Default**     | **Description**                                                    |
+============+===================+=================+====================================================================+
| separator  | ``boolean``       | ``false``       | Specify if columns should be separated by a vertical line.         |
+------------+-------------------+-----------------+--------------------------------------------------------------------+

Column structure
-------------
+------------+--------------------------------+-----------------+-------------------------------------------------------+
| **Name**   |  **Type**                      | **Default**     | **Description**                                       |
+============+=========================+=================+==============================================================+
| size       | ``"auto" | number``            |   ``"auto"``    | Tab handle icon.                                      |
+------------+-------------------------+-----------------+--------------------------------------------------------------+
| align      | ``"start" | "end" | "center"`` |   ``"start"``   | Tab handle hover title.                               |
+------------+--------------------------------+-----------------+-------------------------------------------------------+

Minimal Usage
-------------

.. code-block:: javascript

    {
      id: "someGrid",
      type: "grid-dev",
      columns: [
        {
          options: [
            {
              id: "first-name",
              label: "FName",
              type: "text-dev"
            }
          ]
        },
        {
          options: [
            {
              id: "lastName",
              label: "LName",
              type: "text-dev"
            }
          ]
        },
      ]
    }

Usage
-----

.. code-block:: javascript

    {
      id: "someGrid",
      type: "grid-dev",
      config: {
        separator: true,
      },
      columns: [
        {
          size: 2,
          options: [
            {
              id: "first-name",
              label: "FName",
              type: "text-dev"
            },
            {
              id: "lastName",
              label: "LName",
              type: "text-dev"
            }
          ]
        },
        {
          size: 1,
          align: "start",
          options: [
            {
              id: "age",
              label: "Age",
              type: "number-dev"
            }
          ]
        },
      ]
    }