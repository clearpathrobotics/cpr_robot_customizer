^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
Changelog for package cpr_robot_customizer
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

0.1.0 (2022-03-04)
------------------
* Rename package to cpr_robot_customizer; separate Gazebo and Rviz launch files
* Add comments
* Combine gazebo and rviz into same launch file
* Remove ros controllers from Gazebo for simplicity; currently out of scope
* Add Gazebo support for generic robot example
* Add gazebo support for microstrain IMU URDF
* Log output of nodes to screen
* Add missing dependencies to package.xml
* Remove FLIR camera support for now since it requires external SDK for driver to work
* Able to pass in any description.launch into view_model.launch as an argument
* Remove README contents, point to tutorial instead
* Remove redundant </node>
* Add example files
* Change CPR_BLACKFLY_CALIBRATION to CPR_BLACKFLY_CALIB; remove references to NovAtel SMART6
* Update README
* Add CODEOWNERS; add bug and feature in ISSUE_TEMPLATE
* Remove UST10 URDF; use urg_node UST10 URDF instead
* Add Garmin GPS support; update some link names
* Remove Novatel SMART6 URDF
* Specify CPR_IMU as CPR_MICROSTRAIN for microstrain family of IMU devices; add general URDF for microstrain IMU devices
* Rename envars from _HOST to _IP, and from _NAVSAT to _GPS
* Add roslaunch checks
* Fix version name, fix name, list dependencies in alphabetical order
* Fix HDL32E typo
* Update CPR_LASER default value
* Add setup and usage instructions
* Add envars script
* Revert "Add enviroment variables script"
  This reverts commit 8048f794e28e591a2101ebeaf32094f6d56f10dd.
* Add enviroment variables script
* Fix typos
* Update support of FLIR FLEA3 to Blackfly S
* Use sick_scan instead of lms1xx
* Use microstrain_inertial_driver instead of ros_mscl
* Remove support for Novatel SMART6 since EOL
* README fix
* Initial README
* Working driver launch files; added dependencies
* URDF support for Intel RealSense family cameras
* Initial accessories.launch file
* Add GX5 IMU URDF
* Add URDF support for Novatel SMART6 and SMART7
* Add HDL32E support; fix LASER_3D envar names
* Add URDF support for 2D lasers, 3D lasers, and FLEA3 camera
* Initial package commit
* Contributors: Joey Yang, jyang-cpr
