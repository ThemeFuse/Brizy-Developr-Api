Population
==========

Population option type.

Important
---------
Do no use this option by any means. Use the official method of adding population for the options presented in
**Introduction**. This option was created for some special cases:
 - Backward compatibility, where the option value was saved under a specific id, but population value under another.
 - Case when you want to create a population method for an option that doesn't exist in toolbar, so you have no option to attach your population.

In 99% of the cases the official method will meet all your needs.

Fields
------

+------------+-------------+---------------+----------------------------------------------------------------------------+
| **Name**   |  **Type**   | **Required**  | **Description**                                                            |
+============+=============+===============+============================================================================+
| options    | ``array``   | ``no``        | List of options that population covers.                                    |
+------------+-------------+---------------+----------------------------------------------------------------------------+

Config
------

+------------+-------------+-------------+------------------------------------------------------------------------------+
| **Name**   |  **Type**   | **Default** | **Description**                                                              |
+============+=============+=============+==============================================================================+
| iconOnly   | ``boolean`` | ``false``   | Hide the input with the population name, keeping only the dropdown.          |
+------------+-------------+-------------+------------------------------------------------------------------------------+
| choices    | ``array``   |             | List of population methods. Check out **Population method** section.         |
+------------+-------------+-------------+------------------------------------------------------------------------------+

DefaultValue
-----

+---------------+-------------------+-------------+---------------------------------------------------------------------+
| **Name**      |  **Type**         | **Default** | **Description**                                                     |
+===============+===================+=============+=====================================================================+
| value         | ``string``        | ``""``      | Population method id.                                               |
+---------------+-------------------+-------------+---------------------------------------------------------------------+

Population method
-----------------

+---------------+-------------------+-------------+---------------------------------------------------------------------+
| **Name**      |  **Type**         | **Required**| **Description**                                                     |
+===============+===================+=============+=====================================================================+
| value         | ``string``        | ``yes``     | Valid population method is.                                         |
+---------------+-------------------+-------------+---------------------------------------------------------------------+
| title         | ``string``        | ``yes``     | Population method title.                                            |
+---------------+-------------------+-------------+---------------------------------------------------------------------+
| icon          | ``string``        | ``no``      | Custom icon for population method.                                  |
+---------------+-------------------+-------------+---------------------------------------------------------------------+


Usage
-------------

.. code-block:: javascript

    {
      id: "titlePopulation",
      type: "population"
      config: {
        choices: [
          { id: "post-id", title: "Post ID" },
          { id: "post-title", title: "Post Title" },
          { id: "post-excerpt", title: "Post Excerpt" },
        ]
      },
      options: [
        {
          id: "title",
          label: "title"
          type: "inputText"
        }
      ]
    }

With icon only
--------------

.. code-block:: javascript

    {
      id: "titlePopulation",
      type: "population"
      config: {
        iconOnly: true,
        choices: [
          { id: "post-id", title: "Post ID" },
          { id: "post-title", title: "Post Title" },
          { id: "post-excerpt", title: "Post Excerpt" },
        ]
      }
    }
