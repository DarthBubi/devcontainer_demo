# This is the development environment
FROM althack/ros2:foxy-gazebo-nvidia

ENV DEBIAN_FRONTEND=noninteractive
RUN sudo apt-get update && sudo apt-get install -y \
    ros-foxy-turtlebot3 \
    ros-foxy-turtlebot3-teleop \
    && rm -rf /var/lib/apt/lists/*
ENV DEBIAN_FRONTEND=

ENV TURTLEBOT3_MODEL=waffle_pi

ARG WORKSPACE
RUN echo "if [ -f ${WORKSPACE}/install/setup.bash ]; then source ${WORKSPACE}/install/setup.bash; fi" >> /home/ros/.bashrc
