Motion
======


``motion-dev`` option type.

Value
-----

.. code-block:: javascript

    {
      vertical?: {
        speed: number, // A number from 0 to 1
        direction: "up" | "down",
      },
      horizontal?: {
        speed: number, // A number from 0 to 1
        direction: "up" | "down",
      },
      transparency?: {
        direction: "in" | "out",
        level: number, // A number from 0 to 1
      },
      blur?: {
        direction: "in" | "out" | "outIn" | "inOut",
        level: number, // A number from 0 to 1
      },
      rotate?: {
        direction: "left" | "right",
        x: "left" | "center" | "right",
        y: "top" | "center" | "bottom",
        speed: number, // A number from 0 to 1
      },
      scale?: {
        direction: "up" | "down",
        speed: number, // A number from 0 to 1
        x: "left" | "center" | "right",
        y: "top" | "center" | "bottom",
      },
      mouseTrack?: {
        direction: "direct" | "opposite",
        speed: number, // A number from 0 to 1
      },
      mouseTilt?: {
        direction: "direct" | "opposite",
        speed: number, // A number from 0 to 1
      },
    }

Minimal Usage
-------------

.. code-block:: javascript

    {
      id: "motion",
      type: "motion-dev"
    }

Usage
-----

.. code-block:: javascript

    {
      id: "motion",
      type: "motion-dev"
      defaultValue: {
        rotate: {
          direction: "left"
          x: "center",
          y: "center",
          speed: 0.5,
        },
      }
   }

