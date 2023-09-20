---
title: Software
layout: default
has_children: false
nav_order: 3
---

# Testbed Software 

Our testbed systems all use the same software framework. At a high level, each has an external control computer, and a Raspberry Pi physically attached to the testbed.
- Control Computer
    
    The control computer runs the ROS master node, as well as nodes for FlexBE (the state machine), data collection, and arm (manipulator) control.

- Raspberry Pi
    
    The Raspberry Pi controls the physical actuators and collects data on the testbed itself. Reset operations are triggered by ROS action clients on the control computer.

Currently, the systems use ROS Melodic. Details about setting up each are outlined in the Initial Setup section.

## Initial Setup

### Control Computer

As ROS Melodic is not compatible with the latest versions of Ubuntu (and to enable easy setup across multiple devices), a Docker container is used. The Docker container is build from Ubuntu 18.04, and enables the control computer to be running newer versions of Ubuntu or other operating systems.

The [infrastructrue-packages repository](https://github.com/OSUrobotics/infrastructure-packages) provides setup instuctions for the container, and includes all of the base modules (FlexBE, custom messages, visualization, etc.).


### Raspberry Pi

The Raspberry Pi requires a Ubuntu 18.04 image with ROS Melodic. [We provide one, as well instructions for flashing here](https://oregonstate.box.com/s/s0gt75lpap5d37oyjeo47on6a7t4ze4d).

Once the Raspberry Pi is booted up, we recomend updating packages with the following:
```console,
   sudo apt-get update && sudo apt-get upgrade
```

Now, follow the instructions in the [infrastructure-raspi repository](https://github.com/OSUrobotics/infrastructure-raspi) to finish setup on the Pi.

## Arm/Manipulator Control



