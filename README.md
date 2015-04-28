#ihmc\_atlas

The `ihmc_atlas` package allows for integration with the IHMC ROS API and the Boston Dynamics Atlas humanoid.

## Getting Started

To download the latest IHMC Controller-plus-Sim binaries, run `rosrun ihmc_atlas ihmc_dist_update.py`. This should always be done on the first run. This will pull in the latest version of the .java distribution.

##Usage

`ihmc_atlas` provides the following launch files:

- `ihmc_atlas_scs.launch`: Launch the ROS API node and the IHMC Simulation Construction Set simulated robot
- `ihmc_atlas_gazebo.launch`: Launch the ROS API node and the IHMC Gazebo plugin
- `ihmc_atlas_robot.launch`: Launch the ROS API node to work with the real robot
- `ihmc_atlas_remote_visualizer.launch`: Launch the SCS Remote Visualizer for performing analysis and diagnostics on the real robot.

You can set the following roslaunch args:

- `ihmc_network_file:=<absolute path to network file>`: Specific the network configuration .ini file for the IHMC software. See [the wiki](https://bitbucket.org/ihmcrobotics/ihmc_ros/wiki/network-config) for more information

In addition, the Visualizer, Robot and SCS launches can take the following argument:

- `ihmc_model:=<MODEL_NAME>`: Specify an argument for the IHMC Controller letting it know which model to use internally. If you would like to see additional models, please feel free to submit a [feature request](https://bitbucket.org/ihmcrobotics/ihmc_ros/issues/new). Currently valid model arguments:
  - ATLAS\_UNPLUGGED\_V5\_NO\_HANDS
  - ATLAS\_UNPLUGGED\_V5\_DUAL\_ROBOTIQ

Further, Robot and SCS launches can take the following argument:

- `description_model:=<path to urdf file>`: The .urdf used by ROS when publishing robot descriptions. Defaults to one of the models vendored in the `ihmc_models` package, but can be overriden.

Lastly, the SCS launch can take an argument for starting position:

- `starting_location:=<STARTING POSITION>`: Specify landmarks in the test environment to spawn the robot near.

### Starting Positions
The starting position in the demo world can be defined. Currently the options are:

    DEFAULT, DRC_TRIALS_TRAINING_WALKING, DRC_TRIALS_QUALS, MID_LADDER, RAMP_BOTTOM, RAMP_TOP, NARROW_DOORWAY, BARRIERS, SMALL_PLATFORM, MEDIUM_PLATFORM,   ON_MEDIUM_PLATFORM, EASY_STEPPING_STONES, STEPPING_STONES, STAIRS, ROCKS, LADDER, IN_FRONT_OF_ZIGZAG_BLOCKS, SINGLE_CYLINDERBLOCKS, TOP_OF_SLOPES,   DEFAULT_BUT_ALMOST_PI, IN_FRONT_OF_CINDERBLOCK_FIELD, IN_FRONT_OF_TWO_HIGH_CINDERBLOCKS, IN_FRONT_OF_CYLINDER_BLOCKS, IN_FRONT_OF_SLANTED_CINDERBLOCK_FIELD,   OFFSET_ONE_METER_X_AND_Y, OFFSET_ONE_METER_X_AND_Y_ROTATED_PI, SMALL_PLATFORM_TURNED, SMALL_WALL
