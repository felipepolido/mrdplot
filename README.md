# mrdplot
mrdplot and clmcplot tools for variable logging (C++) and data manipulation/visualization (MATLAB)

## Description 

mrdplot/clmcplot is a logging tool first developed by Stefan Schaal along with the SL robot simulator. Since then many researchers have modified the code dramatically with improvements, new features, etc... But unfortunately, due to the lack of a central repository, each different group developed their own variations of the code.

The goal of this repository is to 1) try integrating some of these different variations into a single common place, 2) further develop existing functionality.

The current version of C++ wrapper compiles easily as a ROS Catkin project.

#### mrdplot tool

![MRDPLOT](/docs//mrdplot.png?raw=true "mrdplot")

#### clmcplot tool

![CLMCPLOT](/docs//clmcplot.png?raw=true "clmcplot")

## How-to use (ROS environment)


### Installation

Clone this package on your catkin workspace source folder:
```bash
cd ~/catkin_ws/src
git clone git@github.com:felipepolido/mrdplot.git
```
And compile the workspace:
```bash
cd ~/catkin_ws/
catkin_make
```

As of this writing the log files will be saved into the folder /logs/mrdplot, this can be easily change, but do create the common folder:

```bash
sudo mkdir -p /logs/mrdplot
sudo chmod -R 777 /logs/mrdplot
```

### Example:
To launch the [example logger](https://github.com/felipepolido/mrdplot/blob/master/example/ExampleLogger.cpp):
```bash
rosrun mrdplot example_logger
```

If the file was logged properly you will get the following message:

```bash
/logs/mrdplot/ctrl_<user>_<date and time>.mrd SAVING DATA .....
/logs/mrdplot/ctrl_<user>_<date and time>.mrd SAVED DATA.
```

For example:
```bash
/logs/mrdplot/ctrl_fpolido_06_29_11_48_32.mrd SAVING DATA .....
/logs/mrdplot/ctrl_fpolido_06_29_11_48_32.mrd SAVED DATA.
```

### ROS Example:

To launch the ros example, start the 
[ros publisher](https://github.com/felipepolido/mrdplot/blob/master/example/RosExamplePublisher.cpp):
```bash
rosrun mrdplot ros_example_pub
```

And in another terminal start the 
[ros logger](https://github.com/felipepolido/mrdplot/blob/master/example/RosExampleLogger.cpp):
```bash
rosrun mrdplot ros_example_logger
```

### Data Visualization:

First, open MATLAB and include /mrdplot/matlab to MATLAB's path:
- traverse to the mrdplot folder
- right click on the mrdplot/matlab folder
- go to "Add to Path"  
- click on "Select Folders and Subfolders" 

Then on the command window type "mrdplot" or "clmcplot" to open either tool.
At this point open a log by cliking the "Open" button on the GUI.

After the log has opened, to add signals to each plot click 
on the signal and then click on the desired plot.

### Dependencies

To include mrdplot to your project, 
first make sure the CMakeLists.txt find the mrdplot package:

```bash
find_package(catkin REQUIRED
  mrdplot
  )
```

And add the dependency to your package.xml:

```bash
  <build_depend>mrdplot</build_depend>
  <run_depend>mrdplot</run_depend>
```



## Thank you 
Thank you Stefan Schaal for developing mrdplot along with the SL simulator.

Thank you for anyone who has contributed to this library along the way. If you would like to be explicitly aknowledged please let me know or create a pull request.

Thank you personally to:

[Stefan Schaal](http://www-clmc.usc.edu/~sschaal/) ,
[Siyuan Feng](https://github.com/siyuanfeng) ,
[Matt DeDonato](https://github.com/mdedonato) , 
[Chris Atkseon](https://github.com/cga-cmu)
