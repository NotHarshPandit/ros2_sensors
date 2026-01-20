Ensure that Isaac Sim is installed.  
Open terminal and go to the Isaac Sim directory.  
Run the following command to open Isaac Sim:

```bash
./isaac-sim.selector.sh
```

Open the file Carter_ROS2_Sensors.usd.

For the camera rgb, open the terminal and run the following command: 

```bash
ros2 topic echo /rgb --once
```

This will give the values for one frame. If you want continous values, run: 
```bash
ros2 topic echo /rgb 
```

For the IMU values, run the following command: 

```bash
ros2 topic echo /imu
```
The values will be constant because the robot is not moving.To change this, go to isaac sim and in chasis link, give taget velocity to left_wheel and right_wheel. Then run the command to see the change in values:

```bash
ros2 topic echo /imu
```

For the lidar scan, run :
```bash
ros2 topic echo /scan
```
In another teriminal, run:
```bash
rviz2
```
In rviz2, click on add, select by topic and select LaserScan and then click ok. Then change the Fixed Frame from map to sim_lidar and in LaserScan, change the size from 0.01 to 0.1.

For the point cloud, run :
```bash
ros2 topic echo /point_cloud
```
In rviz2, click on add, select by topic and select PointCloud2 and then click ok. In PointCloud2, change the size from 0.01 to 0.1.