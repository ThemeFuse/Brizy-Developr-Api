Multi Select
============

Multi select option type.

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
| placeholder| ``string``  | ``""``      | Specify input placeholder.                                                   |
+------------+-------------+-------------+------------------------------------------------------------------------------+
| items      | ``number``  |             | Specify maximum numbers of items that can be selected                        |
+------------+-------------+-------------+------------------------------------------------------------------------------+
| scroll     | ``number``  | ``5``       | Specify from what number of items to apply scroll.                           |
+------------+-------------+-------------+------------------------------------------------------------------------------+
| search     | ``boolean`` | ``true``    | Enable or disable search feature.                                            |
+------------+-------------+-------------+------------------------------------------------------------------------------+
| choices    | ``array``   |             | List of items to choose from. Please checkout *Choices structure*.           |
+------------+-------------+-------------+------------------------------------------------------------------------------+

Value
-----

+---------------+-------------+-------------+---------------------------------------------------------------------------+
| **Name**      |  **Type**   | **Default** | **Description**                                                           |
+===============+=============+=============+===========================================================================+
| value         | ``array``   |             | Array of `string` or `number` values.                                     |
+---------------+-------------+-------------+---------------------------------------------------------------------------+

Choices structure
-----------------

+---------------+-------------------+-------------+---------------------------------------------------------------------+
| **Name**      |  **Type**         | **Default** | **Description**                                                     |
+===============+===================+=============+=====================================================================+
| value         | ``string|number`` | Any `string` or `number` values.                                                  |
+---------------+-------------------+-------------+---------------------------------------------------------------------+
| title         | ``string``        | A valid value title.                                                              |
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
      id: "names",
      type: "multiSelect-dev",
      config: {
        choices: fetchNames
      },
      value: {
        value: ["john", "andy"],
      }
    },


Minimal Usage
-------------

.. code-block:: javascript

    {
      id: "names",
      type: "multiSelect-dev"
    }

Usage
-----

.. code-block:: javascript

    {
      id: "names",
      type: "multiSelect-dev",
      config: {
        size: "medium",
        items: 5,
        scroll: 5,
        placeholder: "Select names",
        search: true,
        choices: [
          { value: "john", title: "John" },
          { value: "andy", title: "Andy" },
          { value: "tom", title: "Tom" }
        ]
      },
      value: {
        value: ["john", "andy"],
      }
    },
