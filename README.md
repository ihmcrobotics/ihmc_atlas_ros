#ihmc\_atlas

The `ihmc_atlas_ros` package allows for integrating the IHMC ROS API and the Boston Dynamics Atlas humanoid in simulation and on real robot hardware.

## Getting Started

This package provides several launch scripts. By default, they all use the latest stable release of IHMC Open Robotics Software as provided on JCenter/Bintray.

This software can also be used with a local build of IHMC Open Robotics Software. For more information, see [the GitHub Pages documentation](TODO fill this in)

##Usage

`ihmc_atlas_ros` provides the following launch files:

- `ihmc_atlas_scs_demo01.launch`: Launch the ROS API node and the IHMC Simulation Construction Set simulated robot in a custom demo environment.
- `ihmc_atlas_scs_finals.launch`: Launch the ROS API node and the IHMC Simulation Construction Set simulated robot in an environment inspired by the DRC Finals.
- `ihmc_atlas_robot.launch`: Launch the ROS API node to work with the real robot
- `ihmc_atlas_remote_visualizer.launch`: Launch the SCS Remote Visualizer for performing analysis and diagnostics on the real robot.

You can set the following roslaunch args:

- `use_local_build:=<true|false>`: If set to true and if you have your environment configured, this will use a local build of the IHMC software

- `ihmc_network_file:=<absolute path to network file>`: Specific the network configuration .ini file for the IHMC software. See [the GitHub pages documentation](TODO fill this in) for more information

In addition, the Visualizer, Robot and SCS launches can take the following argument:

- `ihmc_model:=<MODEL_NAME>`: Specify an argument for the IHMC Controller letting it know which model to use internally. Currently valid model arguments:
  - ATLAS\_UNPLUGGED\_V5\_NO\_HANDS
  - ATLAS\_UNPLUGGED\_V5\_DUAL\_ROBOTIQ

Further, Robot and SCS launches can take the following argument:

- `description_model:=<path to urdf file>`: The .urdf used by ROS when publishing robot descriptions. Defaults to one of the models vendored in the `ihmc_atlas_ros` package, but can be overriden.

Lastly, the SCS launch can take an argument for starting position:

- `starting_location:=<STARTING POSITION>`: Specify landmarks in the test environment to spawn the robot near.

### Starting Positions
The starting position in the demo worlds can be defined. Currently the options are:

For the Demo01 custom world:
    DEFAULT, DRC_TRIALS_TRAINING_WALKING, DRC_TRIALS_QUALS, MID_LADDER, RAMP_BOTTOM, RAMP_TOP, NARROW_DOORWAY, BARRIERS, SMALL_PLATFORM, MEDIUM_PLATFORM,   ON_MEDIUM_PLATFORM, EASY_STEPPING_STONES, STEPPING_STONES, STAIRS, ROCKS, LADDER, IN_FRONT_OF_ZIGZAG_BLOCKS, SINGLE_CYLINDERBLOCKS, TOP_OF_SLOPES,   DEFAULT_BUT_ALMOST_PI, IN_FRONT_OF_CINDERBLOCK_FIELD, IN_FRONT_OF_TWO_HIGH_CINDERBLOCKS, IN_FRONT_OF_CYLINDER_BLOCKS, IN_FRONT_OF_SLANTED_CINDERBLOCK_FIELD,   OFFSET_ONE_METER_X_AND_Y, OFFSET_ONE_METER_X_AND_Y_ROTATED_PI, SMALL_PLATFORM_TURNED, SMALL_WALL

For the Finals world:
    DEFAULT, DEBRIS_START, DEBRIS_END, DRILL, PLUG, WALKING_START, WALKING_END, STAIRS_START, STAIRS_END, SUPRISE
