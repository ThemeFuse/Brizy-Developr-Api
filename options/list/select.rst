Select
======

Select option type.

Fields
------

+------------+-------------+---------------+----------------------------------------------------------------------------+
| **Name**   |  **Type**   | **Required**  | **Description**                                                            |
+============+=============+===============+============================================================================+
| placeholder| ``string``  |               | Specify input placeholder.                                                 |
+------------+-------------+---------------+----------------------------------------------------------------------------+
| choices    | ``array``   | ``yes``       | List of items to choose from. Please checkout *Choices structure*.         |
+------------+-------------+---------------+----------------------------------------------------------------------------+

Select option type.

Config
------

+------------+-------------+-------------+------------------------------------------------------------------------------+
| **Name**   |  **Type**   | **Default** | **Description**                                                              |
+============+=============+=============+==============================================================================+
| size       | ``string``  | ``"medium"``| Specify the input size.                                                      |
|            |             |             ||                                                                             |
|            |             |             || There are 4 sizes:                                                          |
|            |             |             || - ``"short"``, for short input.                                             |
|            |             |             || - ``"medium"``, for normal input.                                           |
|            |             |             || - ``"large"``, for a large input.                                           |
|            |             |             || - ``"full"``, for full width input.                                         |
+------------+-------------+-------------+------------------------------------------------------------------------------+
| scroll     | ``number``  | ``5``       | Specify from what number of items to apply scroll.                           |
+------------+-------------+-------------+------------------------------------------------------------------------------+
| search     | ``boolean`` | ``false``   | Enable or disable search feature.                                            |
+------------+-------------+-------------+------------------------------------------------------------------------------+

Value
-----

+---------------+-------------------+-------------+---------------------------------------------------------------------+
| **Name**      |  **Type**         | **Default** | **Description**                                                     |
+===============+===================+=============+=====================================================================+
| value         | ``string|number`` |             | A `string` or `number` value.                                       |
+---------------+-------------------+-------------+---------------------------------------------------------------------+

Choices structure
-----------------

+---------------+-------------------+-------------+---------------------------------------------------------------------+
| **Name**      |  **Type**         | **Default** | **Description**                                                     |
+===============+===================+=============+=====================================================================+
| value         | ``string|number`` | Any `string` or `number` value.                                                   |
+---------------+-------------------+-------------+---------------------------------------------------------------------+
| title         | ``string``        | A valid value title.                                                              |
+---------------+-------------------+-------------+---------------------------------------------------------------------+
| icon          | ``string``        | Add a custom icon for select item.                                                |
+---------------+-------------------+-------------+---------------------------------------------------------------------+

Choices as function
-------------------
Also the ``choices`` key can be a function that returns a promise of choices. This is use full in case the choices
needs to be fetched from an API.


.. code-block:: javascript

    /**
     * @param {string} s, search item
     * @return {Promise<{title: string, value: string}[]>}
     */
    const fetchNames = s => fetch(`http://some.resource/?q=${s}`).then(users =>
      users.map(user => ({ title: user.name, value: user.id }))
    );

    // ...

    {
      id: "name",
      type: "select-dev",
      choices: fetchNames
      value: {
        value: "john",
      }
    },


Minimal Usage
-------------

.. code-block:: javascript

    {
      id: "names",
      type: "select-dev"
      choices: [
        { value: "john", title: "John" },
        { value: "andy", title: "Andy" },
        { value: "tom", title: "Tom" }
      ],
    }

Usage
-----

.. code-block:: javascript

    {
      id: "name",
      type: "select-dev",
      config: {
        size: "medium",
        scroll: 5,
        placeholder: "Select name",
        search: true,
      },
      choices: [
        { value: "john", title: "John", icon: "nc-user" },
        { value: "andy", title: "Andy", icon: "nc-user" },
        { value: "tom", title: "Tom", icon: "nc-user" }
      ],
      value: {
        value: "john",
      }
    },
