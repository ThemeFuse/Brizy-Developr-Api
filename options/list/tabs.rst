Tabs
====

Tabs option container type.

Config
------

+------------+-------------------+-----------------+--------------------------------------------------------------------+
| **Name**   |  **Type**         | **Default**     | **Description**                                                    |
+============+===================+=================+====================================================================+
| showSingle | ``boolean``       | ``false``       | Specify if tabs should show the tabs handles when it has only      |
|            |                   |                 | a single tab.                                                      |
+------------+-------------------+-----------------+--------------------------------------------------------------------+
| saveTab    | ``boolean``       | ``false``       | Specify if you want to save the last active tab.                   |
+------------+-------------------+-----------------+--------------------------------------------------------------------+
| position   | ``string``        | ``top``         | Specify tabs handles position.                                     |
|            |                   |                 ||                                                                   |
|            |                   |                 || There are 2 available positions:                                  |
|            |                   |                 || - ``top``                                                         |
|            |                   |                 || - ``left``                                                        |
+------------+-------------------+-----------------+--------------------------------------------------------------------+
| align      | ``string``        | ``center``      | Specify tabs handles alignment.                                    |
|            |                   |                 ||                                                                   |
|            |                   |                 || There are 3 available alignments:                                 |
|            |                   |                 || - ``start`` - If the position is ``top``, that means ``left``     |
|            |                   |                 |                alignment.                                          |
|            |                   |                 ||               If position is ``left``, means ``top`` alignment.   |
|            |                   |                 || - ``center``- If the position is ``top``, the items are aligned   |
|            |                   |                 | in center horizontally. If position is ``left``, items are aligned |
|            |                   |                 | in center vertically.                                              |
|            |                   |                 || - ``end`` - If the position is ``top``, that means ``right``      |
|            |                   |                 | alignment``. If position is ``left``, means ``bottom`` alignment.  |
+------------+-------------------+-----------------+--------------------------------------------------------------------+

Tab structure
-------------
+------------+-------------------+-----------------+--------------------------------------------------------------------+
| **Name**   |  **Type**         | **Required**    | **Description**                                                    |
+============+===================+=================+====================================================================+
| id         | ``string``        | ``*``           | An unique value among that defines tab identity.                   |
+------------+-------------------+-----------------+--------------------------------------------------------------------+
| label      | ``string``        |                 | Tab handle text.                                                   |
+------------+-------------------+-----------------+--------------------------------------------------------------------+
| icon       | ``string``        |                 | Tab handle icon.                                                   |
+------------+-------------------+-----------------+--------------------------------------------------------------------+
| title      | ``string``        |                 | Tab handle hover title.                                            |
+------------+-------------------+-----------------+--------------------------------------------------------------------+
| position   | ``number``        | 0               | Tab order priority among the other tabs.                           |
|            |                   |                 || This is useful when you want to arrange tabs when toolbars        |
|            |                   |                 | are merged                                                         |
+------------+-------------------+-----------------+--------------------------------------------------------------------+

Minimal Usage
-------------

.. code-block:: javascript

    {
      id: "coloTabs",
      type: "tabs",
      tabs: [
        {
          id: "bgTab",
          label: "Background",
          options: [
            {
              id: "bg",
              type: "colorPicker"
            }
          ]
        },
        {
          id: "borderTab",
          label: "Border",
          options: [
            {
              id: "border",
              type: "border"
            }
          ]
        },
        {
          id: "shadowTab",
          label: "Shadow",
          options: [
            {
              id: "shadow",
              type: "boxShadow"
            }
          ]
        },
      ]
    }

Usage
-----

.. code-block:: javascript

    {
      id: "coloTabs",
      type: "tabs",
      config: {
        showSingle: true,
        saveTab: true,
        position: "left",
        align: "start"
      },
      tabs: [
        {
          id: "settings",
          label: "Settings",
          position: 4,
          options: [
            {
              id: "enableShadow",
              label: "Enable Shadow",
              type: "switch"
            }
          ]
        },
        {
          id: "bgTab",
          label: "Background",
          position: 3,
          options: [
            {
              id: "bg",
              type: "colorPicker"
            }
          ]
        },
        {
          id: "borderTab",
          label: "Border",
          position: 2,
          options: [
            {
              id: "border",
              type: "border",
              disable: v.enableShadow === "off"
            }
          ]
        },
        {
          id: "shadowTab",
          label: "Shadow",
          position: 1,
          options: [
            {
              id: "shadow",
              type: "boxShadow"
            }
          ]
        }
      ]
    }