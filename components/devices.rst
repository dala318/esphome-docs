Sub Device Configuration
========================

.. seo::
    :description: Instructions for setting up sub devices in ESPHome.
    :image: folder-open.svg

ESPHome has support for createting sub devices in configuration where
individual entities can be grouped to. The grouping has no direct effect
on the functionality of the entities, but it can be used to group
entities together in the Home Assistant UI. This is useful for
example when you have a mix sensors on one device that are related to
different physical devices.

.. note::

    Requires Home Assistant 2025.x or newer.

Base Sub Device Configuration
-----------------------------

All devices in ESPHome have an id and name, and an optional suggested area.

.. code-block:: yaml

    # Example devices configuration
    id: my_device
    name: My Device

    # Optional variables:
    area: Living Room

Configuration variables:

- **id** (**Required**, string): Specify the ID for code generation.
- **name** (**Required**, string): The name for the sub device.
- **area** (*Optional*, string): The suggested area for the sub device.

Assign entity to sub device
---------------------------

For individual entities in your configuration, you can assign them to a
sub device by using the ``device_id`` option. This is done by adding
the ``device_id`` option to the entity configuration. The value should
be the ID of the sub device you want to assign the entity to.

.. code-block:: yaml

    sensor:
      - platform: template
        # ...
        device_id: my_device


See Also
--------

- :doc:`esphome`
- :ghedit:`Edit`
