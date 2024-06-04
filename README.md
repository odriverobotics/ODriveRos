# TAMU fork of the [ROS2 Package for ODrive](https://github.com/odriverobotics/ros_odrive/tree/00940442a34e55ef206f4d62f91e4980812d9984)

This repository contains ROS2 packages for the [ODrive motor controller](https://odriverobotics.com):

- **`odrive_node`**: Standalone ROS2 node for communication with ODrives via CAN bus. → [More info](odrive_node/README.md)
- **`odrive_ros2_control`**: [work in progress] [ros2_control](https://control.ros.org/master/index.html) integration for communication with ODrives via CAN bus.
 → [More info](odrive_ros2_control/README.md)
- **`odrive_botwheel_explorer`**: Example for using the `odrive_ros2_control` package in the context of the [ODrive BotWheel Explorer](https://odriverobotics.com/shop/botwheel-explorer). → [More info](odrive_botwheel_explorer/README.md)

`odrive_node` and `odrive_ros2_control` are two alternative approaches and cannot be used at the same time.

For information about installation, prerequisites and getting started, check out the ODrive [ROS CAN Package Guide](https://docs.odriverobotics.com/v/latest/guides/ros-package.html).

## Compatible Devices

- [ODrive Pro](https://odriverobotics.com/shop/odrive-pro)
- [ODrive S1](https://odriverobotics.com/shop/odrive-s1)
- [ODrive Micro](https://odriverobotics.com/shop/odrive-micro)

(not compatible with ODrive 3.x)

## System Requirements

- Ubuntu >= 20.04
- ROS2 >= Humble

## Developer Notes

(For user instructions, see [this guide](https://docs.odriverobotics.com/v/latest/guides/ros-package.html) instead.)

You can build this node on a non-ROS developer PC by using the DevContainer configurations in this repository. For example with VSCode:

1. Clone repository
2. Open the repository folder in VSCode. It should automatically present an option "Reopen in Dev Container". Click on that and select the desired ROS version.
3. Once it's re-opened, in the VSCode terminal, run:

   ```bash
   colcon build --packages-select odrive_can
   source ./install/setup.bash
   ```
4. Running the node requires hardware access and only works if the container host is Linux.
