FROM ros:crystal-ros-base-bionic

MAINTAINER Lander Usategui  <lander@erlerobotics.com>

RUN apt-get update && apt-get install -y \
    python3-colcon-common-extensions \
    && rm -rf /var/lib/apt/lists/*

# Setup ROS2 workspace
RUN mkdir -p ros2_ws/src
WORKDIR ros2_ws
