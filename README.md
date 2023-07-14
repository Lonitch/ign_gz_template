# ros_gz_project_template
A template project integrating ROS2 and Gazebo (Fortress) simulator

## Included packages

* `robot_description` - holds the SDF/URDF description of the simulated system and any other assets
* `robot_gazebo` - holds gazebo specific code and configurations.  Namely this is where systems end up.
* `robot_application` - holds ros2 specific code and configurations
* `robot_bringup` - holds launch files and high level utilities


## Install
### Requirements
On Ubuntu Jammy(22.04)
1. Install [ROS 2 Humble](https://docs.ros.org/en/humble/index.html)
2. Install [Gazebo Fortress](https://gazebosim.org/docs/fortress)
3. Install necessary tools
```bash
sudo apt install python3-vcstool python3-colcon-common-extensions git wget
sudo apt install ros-humble-gz-ros ros-humble-gz-ros-bridge ros-humble-sdformat-urdf
```

### Usage
1. Create a workspace, and clone the repository:
```bash
mkdir -p ~/template_ws/src
cd ~/template_ws/src
git clone https://github.com/Lonitch/ign_gz_template.git
```
2. Set the Gazebo version to Fortress:
```bash
export GZ_VERSION=fortress
```

3. Install ROS dependencies
```bash
sudo rosdep init
rosdep update
rosdep install --from-paths src --ignore-src -r -y -i
```

4. Build and install

```bash
cd ~/template_ws
colcon build --cmake-args -DBUILD_TESTING=ON
```

### Run
1. Source the workspace
    `. ~/template_ws/install/setup.sh`
2. Launch the simulation
    `ros2 launch robot_bringup example.launch.py`
