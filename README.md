# Installing ROS Noetic on Ubuntu 20.04 using VirtualBox
This guide will install ROS Noetic in the virual machine(Ubuntu 20.04). 

- Ubuntu Version: 20.04 LTS

- ROS Version: ROS Noetic

## 1. Installing ROS on Ubuntu

1. Open a terminal by using the keyboard shortcut `Ctrl+Alt+T`.

2. Run the following commands one after another. 

    > You can look all the commands from here: http://wiki.ros.org/noetic/Installation/Ubuntu.

    Set up sources.list
    
    ```
    sudo sh -c 'echo "deb http://packages.ros.org/ros/ubuntu $(lsb_release -sc) main" > /etc/apt/sources.list.d/ros-latest.list'
    ```
    
    Set up keys
    ```
    sudo apt-key adv --keyserver 'hkp://keyserver.ubuntu.com:80' --recv-key C1CF6E31E6BADE8868B172B4F42ED6FBAB17C654
    ```
    
    Update Debian package index
    ```
    sudo apt update
    ```
    
    Install ROS Desktop-Full
    ```
    sudo apt install -y ros-noetic-desktop-full
    ```
    
    Source setup.bash
    ```
    echo "source /opt/ros/noetic/setup.bash" >> ~/.bashrc
    source ~/.bashrc
    ```
    
    Install dependencies for building packages
    ```
    sudo apt install -y python3-rosdep python3-rosinstall python3-rosinstall-generator python3-wstool build-essential
    ```
    ```
    sudo rosdep init
    rosdep update
    ```
    
    Create a ROS Workspace
    ```
    mkdir -p ~/catkin_ws/src
    cd ~/catkin_ws/
    catkin_make
    ```
    
    Source catkin workspace
    ```
    echo "source $(pwd)/devel/setup.bash" >> ~/.bashrc
    source ~/.bashrc
    ```
