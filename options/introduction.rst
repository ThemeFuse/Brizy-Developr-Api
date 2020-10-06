Introduction
============

.. |_| unicode:: 0xA0 
   :trim:

.. contents::
    :local:
    :backlinks: top

Introduction
------------

Some general description about option types

Structure
---------

TODO: Add description that options isn't just a json, there're inside js function which get { v, device, state } object

Each option support the next specified fields. Any additional fields that are specific to option are added under ``config`` key.
The ``id`` and ``type`` files are required.

+-----------------+-------------+--------------+------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| **Name**        | **Type**    | **\***       | **Default**                  | **Description**                                                                                                                                                       |
+=================+=============+==============+==============================+=======================================================================================================================================================================+
| id              | ``string``  | Yes          |                              | Uniq option identification, used to save value in mode                                                                                                                |
+-----------------+-------------+--------------+------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| type            | ``string``  | Yes          |                              | Defines specific option control used to edit the value.                                                                                                               |
|                 |             |              |                              || Check option types list.                                                                                                                                             |
+-----------------+-------------+--------------+------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| defaultValue    | ``string``  | Yes          | ``{``                        | Initial option value. Check your specific option type value structure in order ot provide a proper value                                                              |
|                 |             |              || |_| |_| ``desktop: {},``    |                                                                                                                                                                       |
|                 |             |              || |_| |_| ``tablet: {},``     |                                                                                                                                                                       |
|                 |             |              || |_| |_| ``mobile: {},``     |                                                                                                                                                                       |
|                 |             |              || ``}``                       |                                                                                                                                                                       |
+-----------------+-------------+--------------+------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| label           | ``string``  | No           | ``""``                       | Label text that is added along with option UI                                                                                                                         |
+-----------------+-------------+--------------+------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| disabled        | ``boolean`` | No           | ``false``                    | Prevent option to be rendered in toolbar.                                                                                                                             |
|                 |             |              |                              | Check **Disable Option** docs.                                                                                                                                        |
+-----------------+-------------+--------------+------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| devices         | ``string``  | No           | ``"all"``                    | Specify on what devices value will appear in builder.                                                                                                                 |
|                 |             |              |                              || Allowed values:                                                                                                                                                      |
|                 |             |              |                              || - ``"all"`` - Appears on all devices.                                                                                                                                |
|                 |             |              |                              || - ``"desktop"`` - Appears only on ``desktop``.                                                                                                                       |
|                 |             |              |                              || - ``"responsive"`` - Appears only on mobile devices: ``tablet``, ``phone``.                                                                                          |
+-----------------+-------------+--------------+------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| states          | ``array``   | No           | ``["normal"]``               | Specify the list of supported states                                                                                                                                  |
|                 |             |              |                              || Allowed values:                                                                                                                                                      |
|                 |             |              |                              || - ``"normal"`` - The option supports normal state.                                                                                                                   |
|                 |             |              |                              || - ``"hover"`` - The option supports hover state.                                                                                                                     |
+-----------------+-------------+--------------+------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| config          | ``object``  | No           | ``{}``                       | Option configuration. Configuration fields are specific to each option. Check option specific docs                                                                    |
+-----------------+-------------+--------------+------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| className       | ``string``  | No           | ``""``                       | Add optional CSS class on option wrapper                                                                                                                              |
+-----------------+-------------+--------------+------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| population      | ``array``   | No           |                              | List of available population methods. Check below **Population Methods** docs.                                                                                        |
+-----------------+-------------+--------------+------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| helper          | ``object``  | No           |                              | Help tooltip configuration. Check below **Helper Structure** docs.                                                                                                    |
+-----------------+-------------+--------------+------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------+

Usage
-----

.. code-block:: javascript

    {
      id: "myOption",
      type: "colorPicker",
      label: "Set the color",
      className: "my-class",
      disabled: false,
      devices: "desktop",
      states: ["normal", "hover"],
      helper: {
        enabled: true,
        content: "Set the header background color",
        position: "top-start"
      },
      config: {
        opacity: false
      },
      value: {
        hex: "#000000",
        opacity: 0.5
      },
      population: [
        {
          value: "myPopulation",
          title: "My Population"
        },
        {
          value: "otherPopulation",
          title: "Other Population",
          icon: "icon"
        }
      ]
    }


Disable Options
----------------
There are moments when you want to prevent an option or group of options to be rendered in toolbar under specific circumstances.
First thing that may come in mid is to render options partially depending on the current state:

.. code-block:: javascript

    export function getItems({ v }) {
      const myOptionalOptions =
        v.someOption === "off"
          ? []
          : [
              {
                id: "otherOption",
                type: "colorPicker",
                states: ["normal", "hover"]
              }
            ];

      return [
        // ...
        ...myOptionalOptions
        // ...
      ];
    }

It is strongly requested to not use this method

 - This looks very ugly and verbose
 - This will create problems in some particular cases, as builder will not have all options list.

Instead you may use ``disabled`` property instead. This solution is safe and way more elegant.

.. code-block:: javascript

    export function getItems({ v }) {
      return [
        // ...
        {
            id: "otherOption",
            type: "colorPicker",
            disabled: v.someOption === "off",
            states: ["normal", "hover"]
        }
        // ...
      ];
    }


Helper Structure (TODO: Check how it works)
----------------

+-----------------+-------------+------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| **Name**        | **Type**    | **Default**      | **Description**                                                                                                                                                       |
+=================+=============+==================+=======================================================================================================================================================================+
| content         | ``string``  | ``""``           | Help tooltip content                                                                                                                                                  |
+-----------------+-------------+------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| position        | ``string``  | ``"top"``        | Help tooltip position over the option.                                                                                                                                |
|                 |             |                  || Allowed values:                                                                                                                                                      |
|                 |             |                  ||                                                                                                                                                                      |
|                 |             |                  || - ``"top"``                                                                                                                                                          |
|                 |             |                  || - ``"top-start"``                                                                                                                                                    |
|                 |             |                  || - ``"top-end"``                                                                                                                                                      |
|                 |             |                  || - ``"right"``                                                                                                                                                        |
|                 |             |                  || - ``"right-start"``                                                                                                                                                  |
|                 |             |                  || - ``"right-end"``                                                                                                                                                    |
|                 |             |                  || - ``"bottom"``                                                                                                                                                       |
|                 |             |                  || - ``"bottom-start"``                                                                                                                                                 |
|                 |             |                  || - ``"bottom-end"``                                                                                                                                                   |
|                 |             |                  || - ``"left"``                                                                                                                                                         |
|                 |             |                  || - ``"left-start"``                                                                                                                                                   |
|                 |             |                  || - ``"left-end"``                                                                                                                                                     |
+-----------------+-------------+------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------+


Population Method (TODO: Check how it works)
-----------------

+-----------------+-------------+------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| **Name**        | **Type**    | **Required**     | **Description**                                                                                                                                                       |
+=================+=============+==================+=======================================================================================================================================================================+
| value           | ``string``  | **Yes**          | Population method id.                                                                                                                                                 |
+-----------------+-------------+------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| title           | ``string``  | **Yes**          | Population method title that will be presented in the population methods list.                                                                                        |
+-----------------+-------------+------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| icon            | ``string``  | **No**           | Population method icon.                                                                                                                                               |
+-----------------+-------------+------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------+


