## Development_of_an_Autonomous_Navigation_System_Based_on_Rolling_2D_Lidar_in_Modern_Apple_Orchards (The Project is in Process)
We have developed an autonomous mobile robot for modern orchards. This robot is capable of scanning the orchard environment using a 2D lidar through rolling motion to obtain 3D point cloud data of the orchard. It then utilizes the 3D point cloud of the current tree row to extract and fit tree row lines and the navigation line. By employing trajectory tracking, the robot achieves motion control, enabling autonomous navigation between rows. At the end of each row, it utilizes point cloud data to determine and locate the end of the row, and ultimately performs the U-turn. The robot is mainly composed of a 2D lidar, a servo motor (equipped with high-precision magnetic encoders), an IMU (Inertial Measurement Unit), and a four-wheel independently driven chassis (with wheel speed feedback). The robot and all sensors follow the right-hand Cartesian coordinate system

<p align="center">
  <img src="img/Hardware_Schematic.jpg" alt="Hardware Overview" width="80%"/>
</p>

### Construction of 3D Point Clouds
Synchronizing the 2D point cloud, servo motor angle feedback, wheeled odometry, and IMU data, and registering the 2D point cloud data into the O3d-xyz reference coordinate system for 3D point clouds, ultimately publishing the accumulated 3D point cloud data from every half rolling cycle at a frequency of 15 Hz for environmental perception processing. We have tested the system in a modern apple orchard, the results are as follows:

<p align="center">
  <img src="img/3D_pointcloud_construction.gif" alt="3D pointcloud construction" width="80%"/>
</p>

<p align="center">
  <img src="img/3D_pointcloud.jpg" alt="3D pointcloud" width="80%"/>
</p>

### Tree row 3D Point cloud segmentation
We used a point cloud segmentation strategy to extract the point cloud data of the fruit tree in the tree row where the robot is currently located, and the results are as follows:

<p align="center">
  <img src="img/tree_row_segmentation.gif" alt="tree row segmentation" width="80%"/>
</p>

<p align="center">
  <img src="img/treerow_extraction.jpg" alt="tree row extraction" width="80%"/>
</p>
