Transform
=========

.. |effects| replace:: ``"rotate"`` 


``transform-dev`` option type.

Config
------

+------------+--------------------+-----------------+-------------------------------------------------------------------+
| **Name**   |  **Type**          | **Default**     | **Description**                                                   |
+============+====================+=================+===================================================================+
| disabled   | Effects[]          | ``[]``          | Specify desired units for margin.                                 |
+------------+--------------------+-----------------+-------------------------------------------------------------------+

**Effects:** |effects|

Value
-----

.. code-block:: javascript

    {
      rotate?: {
        degree: number,
    }

Minimal Usage
-------------

.. code-block:: javascript

    {
      id: "transform",
      type: "transform-dev"
    }

Usage
-----

.. code-block:: javascript

    {
      id: "transform",
      type: "transform-dev",
      config: {
        disabled: ["rotate"]
      },
      defaultValue: {
        rotate: {
          degree: 45
        },
      }
   }

