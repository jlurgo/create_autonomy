FROM create_ros_kinetic
LABEL maintainer="Emiliano Borghi"

ENV ROS1_DISTRO=kinetic

USER root

# Setup sources.list for Gazebo
RUN echo "deb http://packages.osrfoundation.org/gazebo/ubuntu-stable $(lsb_release -sc) main" > /etc/apt/sources.list.d/gazebo-stable.list

# Setup keys for Gazebo
RUN apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys D2486D2DD83DB69272AFE98867170598AF249743

RUN apt-get update && \
    apt-get install -y \
    gazebo9 \
    libgazebo9-dev \
    ros-$ROS1_DISTRO-gazebo9-ros-pkgs \
    ros-$ROS1_DISTRO-gazebo9-ros-control

USER create
CMD tmux
