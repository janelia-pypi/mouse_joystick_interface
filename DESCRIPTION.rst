mouse_joystick_interface_python
===============================

This Python package creates a class named MouseJoystickInterface.

Authors::

    Peter Polidoro <peterpolidoro@gmail.com>

License::

    BSD

Example Usage::

    dev = MouseJoystickInterface() # Might automatically find devices if available
    # if devices not found automatically, specify ports directly
    dev = MouseJoystickInterface(use_ports=['/dev/ttyACM0','/dev/ttyACM0']) # Linux specific ports
    dev = MouseJoystickInterface(use_ports=['/dev/tty.usbmodem262471','/dev/tty.usbmodem262472']) # Mac OS X specific ports
    dev = MouseJoystickInterface(use_ports=['COM3','COM4']) # Windows specific ports
    # abort_assay prematurely stops a running assay and leaves the rig ready to start a new assay
    dev.abort_assay()
    # start_assay is the main method that starts the assay, collects assay data, and saves data files
    dev.start_assay(set_path='~/set_example.csv')

    # optional mouse_joystick_controller methods
    dev.mouse_joystick_controller.set_properties_to_defaults(['ALL'])
    dev.mouse_joystick_controller.get_property_values(['ALL'])
    dev.mouse_joystick_controller.repeat_aborted_trial('setValue',False)
    dev.mouse_joystick_controller.get_assay_status()
    dev.mouse_joystick_controller.move_joystick_to_base_position()
    dev.mouse_joystick_controller.move_joystick_to_reach_position()
    duration = 10
    count = 1
    dev.mouse_joystick_controller.activate_lickport(duration,count)
    dev.mouse_joystick_controller.get_trial_timing_data()
    dev.mouse_joystick_controller.abort_trial()
