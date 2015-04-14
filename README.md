#ihmc\_atlas

The `ihmc_atlas` package allows for integration with the IHMC ROS API and the Boston Dynamics Atlas humanoid.

##Usage

`ihmc_atlas` provides the `ihmc_atlas.launch` file, which starts up the IHMC ROS API configured to talk to the real robot.

You can set the following roslaunch args:

- `ihmc_network_file:=<absolute path to network file>`: Specific the network configuration .ini file for the IHMC software. See [the wiki](https://bitbucket.org/ihmcrobotics/ihmc_ros/wiki/network-config) for more information
- `ihmc_model:=<MODEL_NAME>`: Specify an argument for the IHMC Controller letting it know which model to use internally. If you would like to see additional models, please feel free to submit a [feature request](https://bitbucket.org/ihmcrobotics/ihmc_ros/issues/new). Currently valid model arguments:
  - ATLAS\_UNPLUGGED\_V5\_NO\_HANDS
  - ATLAS\_UNPLUGGED\_V5\_DUAL\_ROBOTIQ
- `description_model:=<path to urdf file>`: The .urdf used by ROS when publishing robot descriptions. Defaults to one of the models vendored in the `ihmc_models` package, but can be overriden.
