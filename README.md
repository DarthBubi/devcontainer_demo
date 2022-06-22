# VSCode Devcontainer Demo

Here are some instructions to follow the hands-on demo.

## Preperations on your host

```
xhost +
```

disables access control on your XServer. Maybe needed if you don't see a Gazebo Windows opening.


## Use the repository as template

Press the "Use template" button on the top right.

This moves the repo to your own namespace without the commit history. You can now clone the repository.

## Open and build the devcontainer

Now open the cloned repository with VSCode. While opening it will propose to open the folder
in a remote container. Press the button "Reopen in container" and Code will build the container
environment.

You may need to remove `"--gpus=all"` from the `devcotainer.json` file if you don't have a
Nvidia GPU, since this is a `nvidia-runtime2` specific option.

Now build the clone the `turtlebot3_gazebo` repository using the following command:
```
vcs import < src/ros2.repos src
```

After completing this task, you can build the packages:
```
colcon build --symlink-install
```

And now source the ROS2 environment:
```
source install/setup.bash
```

## Run the demo packages

Now you can run the demo by first starting a simulation:

```
ros2 launch turtlebot3_gazebo turtlebot3_house.launch.py
```

and in another terminal, which you can open with the little split button:

```
ros2 run turtlebot3_teleop teleop_keyboard
```
