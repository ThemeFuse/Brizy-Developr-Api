Popover
=======

Popover option container type.

Config
------

+------------+-------------------+-----------------+--------------------------------------------------------------------+
| **Name**   |  **Type**         | **Default**     | **Description**                                                    |
+============+===================+=================+====================================================================+
| icon       | ``string|object`` | ``"nc-cog"``    | Specify popover icon name.                                         |
|            |                   |                 ||                                                                   |
|            |                   |                 || You can additionally set custom HTML and CSS.                     |
|            |                   |                 |  In this case, the *icon* key should be and object,                |
|            |                   |                 |  where the keys are the are element attribute names.               |
|            |                   |                 |  The ``content`` key will allow to add any html content.           |
+------------+-------------------+-----------------+--------------------------------------------------------------------+
| title      | ``string``        | ``""``          | Specify popover icon title.                                        |
+------------+-------------------+-----------------+--------------------------------------------------------------------+
| size       | ``string``        | ``"medium"``    | Specify the popover size.                                          |
|            |                   |                 ||                                                                   |
|            |                   |                 || There are 4 sizes:                                                |
|            |                   |                 || - ``"small"``, for small popover.                                 |
|            |                   |                 || - ``"medium"``, for normal size popover.                          |
|            |                   |                 || - ``"large"``, for an extra large popover.                        |
|            |                   |                 || - ``"auto"``, popover size is determined by it's options.         |
+------------+-------------------+-----------------+--------------------------------------------------------------------+
| placement  | ``string``        | ``"top-center"``| Specify the popover placement.                                     |
|            |                   |                 ||                                                                   |
|            |                   |                 || List of all available placements:                                 |
|            |                   |                 || - ``"top-left"``                                                  |
|            |                   |                 || - ``"top-center"``                                                |
|            |                   |                 || - ``"top-right"``                                                 |
|            |                   |                 || - ``"center-left"``                                               |
|            |                   |                 || - ``"center-center"``                                             |
|            |                   |                 || - ``"center-right"``                                              |
|            |                   |                 || - ``"bottom-left"``                                               |
|            |                   |                 || - ``"bottom-center"``                                             |
|            |                   |                 || - ``"bottom-right"``                                              |
+------------+-------------------+-----------------+--------------------------------------------------------------------+

Options
-------
This options renders other options. You need to provide an array of option under the ``options`` key.


Minimal Usage
-------------

.. code-block:: javascript

    {
      id: "popoverTypography",
      type: "popover-dev",
      options: [
        {
          label: "Insert page title",
          id: "title",
          type: "inputText-dev",
        },
        {
          id: "title-style",
          type: "typography-dev",
          config: {
            fontFamily: false,
          }
        }
      ]
    }

Usage
-----

.. code-block:: javascript

    {
      id: "popoverColor",
      type: "popover-dev",
      config: {
        size: "auto",
        title: t("Colors"),
        icon: {
          style: {
            backgroundColor: v.color,
          }
        }
      },
      options: [
        {
          id: "color",
          type: "colorPicker-dev",
        }
      ]
    }