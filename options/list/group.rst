Group
=====

Group option container type.

Options
-------
This options renders other options. You need to provide an array of option under the ``options`` key.

Usage
-----

.. code-block:: javascript

    {
      id: "groupSettings",
      type: "group",
      options: [
        {
          id: "start",
          label: "Start",
          type: "slider",
        },
        {
          id: "end",
          label: "end",
          type: "slider",
        }
      ]
    }

Also you cna use the `group` option type to emulate dependent options,
where on or few options are visible only if the parent option has specific value.

.. code-block:: javascript

    {
      id: "groupSettings",
      type: "group",
      options: [
        {
          id: "enableBoundaries",
          label: "Enable Boundaries",
          type: "toggle",
        },
        {
          id: "start",
          label: "Start",
          type: "slider",
          disabled: v.enableBoundaries !== "on",
        },
        {
          id: "end",
          label: "end",
          type: "slider",
          disabled: v.enableBoundaries !== "on",
        }
      ]
    }