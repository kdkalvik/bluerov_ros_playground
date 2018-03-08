# BlueRov-ROS-playground
Bluerov2 Gazebo simulation.

# Setup
1.Install [freebuoyancy_gazebo](https://github.com/bluerobotics/freebuoyancy_gazebo#install)
    plugin for buoyancy simulation.
    
2. Install [ardupilot_gazebo/add_link](https://github.com/patrickelectric/ardupilot_gazebo/tree/add_link#usage-)
    plugin for ardupilot-gazebo communication. *add_link* is a branch that provides actuation over sdf links, after the `git clone`, it's necessary to run `git checkout add_link`.
    
3. Run BlueRov2 Gazebo model without ROS and MAVROS
    a. Download bluerov_ros_playground
        ```bashz
        git clone https://github.com/kdkalvik/bluerov_ros_playground/
        cd bluerov_ros_playground/
        ```
 
    b. Run Gazebo model
        ```bash
        cd bluerov_ros_playground
        source gazebo.sh
        gazebo worlds/underwater.world -u
        # Start the simulation
        ```
        
3. Run BlueRov2 Gazebo model with ROS and MAVROS
    a. Make sure you have ROS kinetic installed and then install mavros 
        ```bash
        sudo apt-get install ros-kinetic-mavros*
        ```
    b. Download bluerov_ros_playground
        ```bash
        cd catkin_ws/src
        git clone https://github.com/kdkalvik/bluerov_ros_playground/
        cd ..
        catkin_make
        ```
 
    c. Run Gazebo model
        ```bash
        cd catin_ws/src/bluerov_ros_playground
        source gazebo.sh
        roslaunch bluerov_ros_playground gazebo_sitl.launch
        # Start the simulation
        ```
 
4. Execute ArduSub [SITL](https://http://ardupilot.org/dev/docs/setting-up-sitl-on-linux.html)
    ```bash
    sim_vehicle.py -f gazebo-bluerov2 -I 0 -j4 -D -L RATBeach --console
    ```

The console will start to display the output if the connection was successful (Use QGC to control the ROV).
