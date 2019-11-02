Multi-Picker
------------

Pick a choice, then complete options related to that choice.

The ``picker`` parameter holds a valid option type with choices. Supported option types are ``select``, ``radio``, ``image-picker`` and ``switch``.

.. code-block:: php

    array(
        'type'  => 'multi-picker',
        'label' => false,
        'desc'  => false,
        'value' => array(
            /**
             * '<custom-key>' => 'default-choice'
             */
            'gadget' => 'phone',

            /**
             * These are the choices and their values,
             * they are available after option was saved to database
             */
            'laptop' => array(
                'price' => '123',
                'webcam' => false
            ),
            'phone' => array(
                'price' => '456',
                'memory' => '32'
            )
        ),
        'picker' => array(
            // '<custom-key>' => option
            'gadget' => array(
                'label'   => __('Choose device', '{domain}'),
                'type'    => 'select', // or 'short-select'
                'choices' => array(
                    'phone'  => __('Phone', '{domain}'),
                    'laptop' => __('Laptop', '{domain}')
                ),
                'desc'    => __('Description', '{domain}'),
                'help'    => __('Help tip', '{domain}'),
            )
        ),
        /*
        'picker' => array(
            // '<custom-key>' => option
            'gadget' => array(
                'label'   => __('Choose device', '{domain}'),
                'type'    => 'radio',
                'choices' => array(
                    'phone'  => __('Phone', '{domain}'),
                    'laptop' => __('Laptop', '{domain}')
                ),
                'desc'    => __('Description', '{domain}'),
                'help'    => __('Help tip', '{domain}'),
            )
        ),
        */
        /*
        'picker' => array(
            // '<custom-key>' => option
            'gadget' => array(
                'label'   => __('Choose device', '{domain}'),
                'type'    => 'image-picker',
                'choices' => array(
                    'phone'  => 'http://placekitten.com/70/70',
                    'laptop' => 'http://placekitten.com/71/70'
                ),
                'desc'    => __('Description', '{domain}'),
                'help'    => __('Help tip', '{domain}'),
            )
        ),
        */
        /*
        picker => array(
            // '<custom-key>' => option
            'gadget' => array(
                'label' => __('Choose device', '{domain}'),
                'type'  => 'switch',
                'right-choice' => array(
                    'value' => 'laptop',
                    'label' => __('Laptop', '{domain}')
                ),
                'left-choice' => array(
                    'value' => 'phone',
                    'label' => __('Phone', '{domain}')
                ),
                'desc' => __('Description', '{domain}'),
                'help' => __('Help tip', '{domain}'),
            )
        ),
        */
        'choices' => array(
            'phone' => array(
                'price' => array(
                    'type'  => 'text',
                    'label' => __('Price', '{domain}'),
                ),
                'memory' => array(
                    'type'  => 'select',
                    'label' => __('Memory', '{domain}'),
                    'choices' => array(
                        '16' => __('16Gb', '{domain}'),
                        '32' => __('32Gb', '{domain}'),
                        '64' => __('64Gb', '{domain}'),
                    )
                )
            ),
            'laptop' => array(
                'price' => array(
                    'type'  => 'text',
                    'label' => __('Price', '{domain}'),
                ),
                'webcam' => array(
                    'type'  => 'switch',
                    'label' => __('Webcam', '{domain}'),
                )
            ),
        ),
        /**
         * (optional) if is true, the borders between choice options will be shown
         */
        'show_borders' => false,
    )

.. _multi-picker-get-db-value:

.. rubric:: Get database option value

.. code-block:: php

    $value = fw_get_db_..._option(
        'option_id/'. fw_get_db_..._option('option_id/'. 'gadget')
    );

.. _multi-picker-add-support-for-new-option-type-in-picker:

.. rubric:: Add support for new option type in picker

If you want to use in ``picker`` an option type that is not supported by default (is not present in the examples above), follow the steps below.
In this example, is added support for ``icon`` option type *(it is not practical, just for demonstration purposes)*.

1. Add in ``{theme}/inc/hooks.php``

    .. code-block:: php

        /**
         * Generate array( 'choice_id' => array( Choice Options ) )
         * @internal
         * @param array $choices
         * @param array $data
         * @return array
         */
        function _filter_theme_option_type_multi_picker_choices_icon($choices, $data) {
            $choices = $data['option']['choices'];

            // maybe check and remove invalid choices ...

            return $choices;
        }
        add_filter(
            'fw_option_type_multi_picker_choices:icon',
            '_filter_theme_option_type_multi_picker_choices_icon',
            10, 2
        );

        /**
         * @internal
         */
        function _admin_theme_multi_picker_custom_picker_scripts() {
            wp_enqueue_script(
                'multi-picker-custom-pickers',
                get_template_directory_uri() . '/js/multi-picker-custom-pickers.js',
                array('fw-events'),
                false,
                true
            );
        }
        add_action(
            'admin_enqueue_scripts',
            '_admin_theme_multi_picker_custom_picker_scripts'
        );

2. Add in ``{theme}/js/multi-picker-custom-pickers.js``

    .. code-block:: javascript

        fwEvents.on('fw:option-type:multi-picker:init:icon', function(data){
            data.$pickerGroup.find('.fw-option-type-icon > input[type="hidden"]').on('change', function() {
                data.chooseGroup(
                    this.value // this is `choice_id` from the `fw_option_type_multi_picker_choices:{type}` filter (above)
                );
            }).trigger('change');
        });

3. Add in ``{theme}/framework-customizations/theme/options/settings.php``

    .. code-blocK:: php

        $options = array(

            'demo_multi_picker_icon' => array(
                'type'         => 'multi-picker',
                'label'        => false,
                'desc'         => false,
                'picker'       => array(
                    'gadget' => array(
                        'label'   => __( 'Multi Picker: Icon', 'unyson' ),
                        'type'    => 'icon',
                    )
                ),
                'choices' => array(
                    'fa fa-btc'  => array(
                        'price'  => array(
                            'label' => __( 'Price', 'unyson' ),
                            'type'  => 'slider',
                            'value' => 70,
                        ),
                    ),
                    'fa fa-viacoin' => array(
                        'price'  => array(
                            'label' => __( 'Price', 'unyson' ),
                            'type'  => 'slider',
                            'value' => 30
                        ),
                    ),
                ),
            ),

        );

4. Open **Theme Settings** page and pick the Bitcoin or Viacoin icon.

Dynamic Multi Picker
====================

While basic set of pre-defined pickers is enough in most of the cases, you may
want to move it somewhere up or down from the main multi picker block. You
may even want to move the picker in another tab so that your options looks
more clean. In this case, the possibility of **detaching** the picker for the
multi picker will help you a lot.

The first step is to define your picker somewhere in the same **form** (we name
that a **context**) Please note that the ``select`` here is not nested under
a ``multi`` or other option. Also, it is important to note that the ID for
the ``select`` here is ``gadget``.

    .. code-blocK:: php

        $options = array(
            'gadget' => array(
                'type'    => 'select',
                'choices' => array(
                    'phone'  => __('Phone', '{domain}'),
                    'laptop' => __('Laptop', '{domain}')
                ),
            ),
        );

        // In view.php
        $current_value = fw_akg('gadget', $atts);

Next, you would add the ``multi-picker`` body and **connect** it to that
particular ``select`` with ``gadget`` ID.

    .. code-blocK:: php

        $options = array(
            'gadget' => array(
                'type'    => 'select',
                'choices' => array(
                    'phone'  => __('Phone', '{domain}'),
                    'laptop' => __('Laptop', '{domain}')
                ),
            ),

            'multi-picker' => array(
                'type' => 'multi-picker',

                // Here is the ID of our select
                'picker' => 'gadget',

                'choices' => array(
                    'phone' => array(
                        'text' => array(
                            'type' => 'text'
                        )
                    ),

                    'laptop' => array(
                        'text' => array(
                            'type' => 'icon-v2'
                        )
                    )
                )
            ),


        );


        // In view.php
        $current_value = fw_akg('gadget', $atts);

        $current_picker_value = fw_akg(
            'multi-picker/' . $current_value . '/text',
            $atts
        );

        fw_print($current_picker_value);


You would notice that the multi picker updates when that select changes.

You can even connect two (or three) multi pickers to the same picker.

    .. code-blocK:: php

        $options = array(
            'gadget' => array(
                'type'    => 'select',
                'choices' => array(
                    'phone'  => __('Phone', '{domain}'),
                    'laptop' => __('Laptop', '{domain}')
                ),
            ),

            'first-multi-picker' => array(
                'type' => 'multi-picker',

                // Here is the ID of our select
                'picker' => 'gadget',

                'choices' => array(
                    'phone' => array(
                        // options for the first choice
                    ),

                    'laptop' => array(
                        // options for the second choice
                    )
                )
            ),

            'second-multi-picker' => array(
                'type' => 'multi-picker',

                // Here is the ID of our select
                'picker' => 'gadget',

                'choices' => array(
                    'phone' => array(
                        // options for the first choice
                    ),

                    'laptop' => array(
                        // options for the second choice
                    )
                )
            ),
        );

Enjoy!
