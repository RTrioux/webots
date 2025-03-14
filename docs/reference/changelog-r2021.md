# Webots R2021 Change Log

## Webots R2021b Revision 1
Released on XX, XXth, 2021.

  - Bug fixes:
    - Fixed [`wb_supervisor_node_set_visibility`](supervisor.md#wb_supervisor_node_set_visibility) applying visibility to parent and sibling nodes if not used with geometry or [Transform](transform.md) nodes ([#3543](https://github.com/cyberbotics/webots/pull/3543)).
    - Fixed updating the robot window after restarting an extern controller ([#3544](https://github.com/cyberbotics/webots/pull/3544)).
    - Fixed calculation of `front_speed_sum` in the Driver library so that both front wheels are considered in case of 4x4 cars ([#3546](https://github.com/cyberbotics/webots/pull/3546)).
    - Fixed Shift + Left Button drag event when the picked [Solid](solid.md) is child of a [Transform](transform.md) node and the horizontal plane is not clearly visible from view ([#3530](https://github.com/cyberbotics/webots/pull/3530)).
    - Fixed various Python API functions crashing with Python 3.9 ([#3502](https://github.com/cyberbotics/webots/pull/3502)).
    - Fixed mass computation after inserting a [Physics](physics.md) node in case the [Solid.boundingObject](solid.md) was already defined ([#3240](https://github.com/cyberbotics/webots/pull/3240)).
    - Fixed a crash caused when getting contact points of a PROTO ([#3522](https://github.com/cyberbotics/webots/pull/3522)).
    - Fixed starting of Webots from the Windows CMD.exe console ([#3512](https://github.com/cyberbotics/webots/pull/3512)).
    - Fixed bug which made the points returned by `getPointCloud` python API inaccessible ([#3558](https://github.com/cyberbotics/webots/pull/3558)).
    - Fixed 'Convert to Base Node(s)' with textures defined by urls ([#3591](https://github.com/cyberbotics/webots/pull/3591)).
    - Fixed pickable state for cone and cylinder ([#3644](https://github.com/cyberbotics/webots/pull/3644)).

## Webots R2021b
Released on July, 16th, 2021.

  - New Robots
    - Added a model of the [Summit-XL Steel](../guide/summit-xl-steel.md) robot from [Robotnik](https://robotnik.eu/products/mobile-robots/summit-xl-steel-en/) ([#3121](https://github.com/cyberbotics/webots/pull/3121)).
    - Added a model of the [MiR100](../guide/mir100.md) robot from [Mobile Industrial Robots](https://www.mobile-industrial-robots.com/en/solutions/robots/mir100/) ([#3010](https://github.com/cyberbotics/webots/pull/3010)).
    - Added a model of the [Fabtino](../guide/fabtino.md) robot from [REC](http://servicerobotics.eu/en/homepage/) ([#2999](https://github.com/cyberbotics/webots/pull/2999)).
    - Added a model of the [JetBot](../guide/jetbot.md) robot from [NVIDIA](https://jetbot.org) ([#2951](https://github.com/cyberbotics/webots/pull/2951)).
    - Added a model for the [Niryo Ned](../guide/ned.md) robot ([#2925](https://github.com/cyberbotics/webots/pull/2925)).
  - New Devices and Objects:
    - Added a new altimeter device contributed by [sishamilton](https://github.com/sishamilton) ([#3241](https://github.com/cyberbotics/webots/pull/3241)).
    - Added a model of the [SickS300](../guide/lidar-sensors.md) lidar ([#3122](https://github.com/cyberbotics/webots/pull/3122)).
    - Added [HingeJointWithBacklash](../guide/hinge-joint-with-backlash.md) PROTO that extends [HingeJoint](hingejoint.md) to model the effect of backlash and a corresponding sample world ([#2786](https://github.com/cyberbotics/webots/pull/2786)).
    - Added [Hinge2JointWithBacklash](../guide/hinge-2-joint-with-backlash.md) PROTO that extends [Hinge2Joint](hinge2joint.md) to model the effect of backlash and a corresponding sample world ([#2850](https://github.com/cyberbotics/webots/pull/2850)).
    -  Added a generic [Gear](../guide/object-gear.md) PROTO and a demo showing it being used in a collision-based transmission ([#2805](https://github.com/cyberbotics/webots/pull/2805)).
    - Added a nice looking FIFA soccer ball PROTO ([#2782](https://github.com/cyberbotics/webots/pull/2782)).
  - New Samples:
    - Added a draft Robocup Virtual Humanoid League 2021 environment ([#2783](https://github.com/cyberbotics/webots/pull/2783)).
    - Add an example that shows an integration of OpenAI Gym with Webots ([#2711](https://github.com/cyberbotics/webots/pull/2711)).
    - Added a simple room with a Nao robot ([#2701](https://github.com/cyberbotics/webots/pull/2701)).
  - New Features:
    - Support `http://` and `https://` file download and cache for the URL fields of [Background](background.md), [Camera](camera.md), [ContactProperties](contactproperties.md), [ImageTexture](imagetexture.md), [Mesh](mesh.md), and [Motor](motor.md) ([#2591](https://github.com/cyberbotics/webots/pull/2591) and [#2787](https://github.com/cyberbotics/webots/pull/2787)).
    - Reduced installation package size by using online resources for images, meshes, etc. ([#2787](https://github.com/cyberbotics/webots/pull/2787)). **The local URLs to textures and meshes in previous worlds files should be updated to point to online resources, e.g., "textures/carpet.jpg" should be changed to "https://raw.githubusercontent.com/cyberbotics/webots/R2021b/projects/default/worlds/textures/carpet.jpg".**
    - Added the `wb_supervisor_node_set_joint_position` function to artificially set the position of active and passive joints ([#3160](https://github.com/cyberbotics/webots/pull/3160)).
    - Added the `wb_supervisor_node_export_string` function which returns a string from which the node is constructed ([#2743](https://github.com/cyberbotics/webots/pull/2743)).
    - Added the `wb_supervisor_node_save/load_state` functions that allow partial world reverting to a saved state ([#2740](https://github.com/cyberbotics/webots/pull/2740)).
    - Added coupled motors feature which allows to control multiple logically linked [Motors](motor.md) at once ([#2939](https://github.com/cyberbotics/webots/pull/2939)).
    - Added the [Billboard](billboard.md) node. A Billboard node contains children nodes that translate and rotate automatically to always face the viewpoint ([#3023](https://github.com/cyberbotics/webots/pull/3023)).
    - Added the `redColorSensitivity` field to [DistanceSensor](distancesensor.md) that allows tuning (or even disabling) of the red color sensitivity for an infra-red distance sensor ([#3077](https://github.com/cyberbotics/webots/pull/3077)).
    - Changed the rendering engine of the streaming viewer and of the animations for WREN ([#2769](https://github.com/cyberbotics/webots/pull/2769)).
    - Added JavaScript scripting support for [Procedural Proto Nodes](procedural-proto-nodes.md) ([#3087](https://github.com/cyberbotics/webots/pull/3087)).
  - Enhancements
    - Altered the collision detection logic for [Robot.selfCollision](robot.md) to ignore chains of joints if the intermediary joints all share the same `anchor` point ([#2868](https://github.com/cyberbotics/webots/pull/2868)).
    - Allow the [Robot](robot.md) node to be added inside the [Group](group.md) node and other nodes derived from the Group node like [Transform](transform.md) and [Solid](solid.md) ([#2732](https://github.com/cyberbotics/webots/pull/2732)).
    - Make the external controller check more frequently (and indefinitely) for the simulation ([#2442](https://github.com/cyberbotics/webots/pull/2442)).
    - Added pose and field tracking functions to improve the performance of getting pose and field data ([#2279](https://github.com/cyberbotics/webots/pull/2279)).
    - Added contact point tracking functions to improve the performance of getting contact point data ([#3162](https://github.com/cyberbotics/webots/pull/3162)).
    - Added [Supervisor](supervisor.md) functions to retrieve all the fields of a given node ([#3202](https://github.com/cyberbotics/webots/pull/3202)).
    - Added the `wb_supervisor_node_get_pose` function that retrieves an absolute or relative pose. Relative pose is expressed in the coordinate system of another node specified as an argument ([#2932](https://github.com/cyberbotics/webots/pull/2932)).
    - Allowed the `wb_supervisor_node_reset_physics` function to reset the physics of solid descendants of the given node ([#2742](https://github.com/cyberbotics/webots/pull/2742)).
    - Added the `dragForceScale` and `dragTorqueScale` fields to [WorldInfo](worldinfo.md) which enable to set the order of magnitude of the force/torque to be applied in the interface ([#3175](https://github.com/cyberbotics/webots/pull/3175)).
    - Significantly improved the performance of the `wb_camera_get_image`, `wb_range_finder_get_range_image`, and `wb_lidar_get_range_image` functions ([#3032](https://github.com/cyberbotics/webots/pull/3032)).
    - Added an `allowedChannels` field in the [Emitter](emitter.md) and [Receiver](receiver.md) nodes to restrict the channel usage ([#2849](https://github.com/cyberbotics/webots/pull/2849)).
    - Exposed `stopERP` and `stopCFM` parameters in [HingeJointParameters](hingejointparameters.md) that define the local `ERP` and `CFM` used by joint limits.
    - Made the `static` behavior the default for PROTO files and removal of the tag. Non static cases must be labeled as such using the `nonDeterministic` tag instead ([#2903](https://github.com/cyberbotics/webots/pull/2903)).
    - Display magnitude of linear and rotational velocity vectors in the [Field Editor](../guide/the-scene-tree.md#field-editor), to help monitoring robot displacement ([#3209](https://github.com/cyberbotics/webots/pull/3209)).
    - Ensure that any node "name" is displayed in the scene tree to help navigation ([#3198](https://github.com/cyberbotics/webots/pull/3198)).
    - Added a script to convert PROTO files to use [Mesh](mesh.md) nodes instead of [IndexedFaceSet](indexedfaceset.md) nodes to speed-up loading times, improve PROTO readability and maintenance ([#2668](https://github.com/cyberbotics/webots/pull/2668)).
    - Converted several PROTO files to use [Mesh](mesh.md) nodes ([#2668](https://github.com/cyberbotics/webots/pull/2668)).
    - Added flag to [RobotisOp2](../guide/robotis-op2.md) that enables the modeling of backlash in the robot ([#2881](https://github.com/cyberbotics/webots/pull/2881)).
    - Added a version of the [RobotisOp2](../guide/robotis-op2.md) modeled using [Hinge2Joint](hinge2joint.md) on the ankles, hips, and neck ([#2861](https://github.com/cyberbotics/webots/pull/2861)).
    - Made the [TIAGo](../guide/tiago-base.md) robot more sturdy by increasing the `suspensionSpringConstant` value ([#2876](https://github.com/cyberbotics/webots/pull/2876)).
    - Added a `stadium_dry` [background](../guide/object-backgrounds.md) with dry grass to allow Robocup players to distinguish the soccer field from the background ([#2874](https://github.com/cyberbotics/webots/pull/2874)).
    - Added conversion from PROTO to URDF from the Webots command line ([#2885](https://github.com/cyberbotics/webots/pull/2885)).
    - Rework of car meshes to have more realistic rear lights for Mercedes Benz, Lincoln, Citroen, BMW and Range Rover models ([#2615](https://github.com/cyberbotics/webots/pull/2615)).
    - **`<webots/utils/default_robot_window.h>` C include file moved to `<webots/plugins/robot_window/default.h>` ([#2655](https://github.com/cyberbotics/webots/pull/2655)).**
    - Improve generic robot window ([#2655](https://github.com/cyberbotics/webots/pull/2655)).
      - Skip updates when the robot window is hidden to not affect the simulation performance.
      - Add toggle button to choose if the enabling/disabling the graph(s) will also enable/disable the robot device.
      - Add buttons to enable and disable all the devices with the same type at once.
      - Add "Settings" tab to choose the refresh rate, disable all the devices (of any type), and enabling recording data from devices when the corresponding tab is not visible.
      - Improve motor slider visibility by moving it to the left of the graph if the plot is not completely visible.
      - Split the generic robot window code in different libraries and JS files so that it can be easily reused for custom projects.
      - Speed up drawing using WebGL ([#2854](https://github.com/cyberbotics/webots/pull/2854)).
    - Added the HTML robot window for vehicles replacing the deprecated Qt-based robot window (#[2602](https://github.com/cyberbotics/webots/pull/2602)).
    - Support labels in animations ([#3019](https://github.com/cyberbotics/webots/pull/3019)).
    - Modernized and improved the animations' player ([#2979](https://github.com/cyberbotics/webots/pull/2979)).
    - Added support for fonts in the streaming viewer ([#2976](https://github.com/cyberbotics/webots/pull/2976)).
    - Don't display warnings for recent Intel and AMD graphics cards ([#2623](https://github.com/cyberbotics/webots/pull/2623)).
    - Added measurement of the load time and average speed factor when using the `--log-performance` command ([#3002](https://github.com/cyberbotics/webots/pull/3002)).
    - Simplified the usage of the `ros` controller ([#2822](https://github.com/cyberbotics/webots/pull/2822)).
      - Integrated `ros_control` (activated through the `--use-ros-control` flag) to allow the usage of a `diff_drive_controller` and `joint_state_controller` from the [`ros_controllers`](https://github.com/ros-controls/ros_controllers) package.
      - Added an option (activated through the `--auto-publish` flag) to automatically enable all devices on startup and create the corresponding topics.
      - Exposed the `robot_description` ROS parameter (activated through the `--robot-description` flag) that contains the URDF of the robot.
    - Improved the URDF naming convention ([#2875](https://github.com/cyberbotics/webots/pull/2875)).
  - Bug fixes:
    - Fixed resource leak in simulation server script ([#3412](https://github.com/cyberbotics/webots/pull/3412), thanks to [Luiz Felipe Vecchietti](https://github.com/lfelipesv)).
    - Sanitized controller name in MATLAB launcher ([#3404](https://github.com/cyberbotics/webots/pull/3404), thanks to [Bartek Łukawski](https://github.com/PeterBowman) and [Juan Victores](https://github.com/jgvictores)).
    - Fixed bug in [Lidar](lidar.md) / [RangeFinder](../guide/range-finder-sensors.md) measurement when hitting an edge ([#3230](https://github.com/cyberbotics/webots/pull/3230)).
    - Fixed the restart of Webots on Windows after changing the theme or the language from the preferences ([#3367](https://github.com/cyberbotics/webots/pull/3367)).
    - Fixed instabilities in the box-cylinder collision detection ([#3105](https://github.com/cyberbotics/webots/pull/3105)).
    - Fixed wrong computation of the asymmetric friction force direction for [Cylinder](cylinder.md) and [Box](box.md) ([#3150](https://github.com/cyberbotics/webots/pull/3150)).
    - Fixed the return value handling from the `webots_physics_collide` when the [Group](group.md) node is one of the colliding objects ([#2781](https://github.com/cyberbotics/webots/pull/2781)).
    - Fixed the conversion from quaternions to Euler angles in the [InertialUnit](inertialunit.md) for the ENU coordinate system ([#2768](https://github.com/cyberbotics/webots/pull/2768)).
    - Fixed a controller crashing after resetting the simulation and changing the `controller` field value ([#3237](https://github.com/cyberbotics/webots/pull/3237)).
    - Fixed triangle count for [Mesh](mesh.md) and [IndexedFaceSet](indexedfaceset.md) when there is a lot of triangles ([#3086](https://github.com/cyberbotics/webots/pull/3086)).
    - Fixed in the interaction between [IndexedFaceSets](indexedfaceset.md) and distance sensor rays that resulted in the wrong contact point being considered for collision ([#2610](https://github.com/cyberbotics/webots/pull/2610)), affecting TexturedBoxes.
    - Fixed crash visualizing node properties in Node Editor for nodes in deeply nested PROTO structures ([#3109](https://github.com/cyberbotics/webots/pull/30109)).
    - Fixed crash when selecting velocities relative to kinematic ancestor [Solid](solid.md) node in Node Editor ([#3098](https://github.com/cyberbotics/webots/pull/3098)).
    - Fixed crash due to invalid SFColor values in PROTO fields by clamping the value and printing a warning in the Webots console ([#3218](https://github.com/cyberbotics/webots/pull/3218)).
    - Fixed crash triggered by a kinematic simulation involving a PROTO with template regenerable fields ([#3227](https://github.com/cyberbotics/webots/pull/3227)).
    - Fixed crash occurring when a PROTO having template regeneration fields is used as a [`Solid.boundingObject`](solid.md#field-summary) ([#3226](https://github.com/cyberbotics/webots/pull/3226)).
    - Fixed incorrect regeneration of the PROTO nodes inserted in a [`Solid.boundingObject`](solid.md#field-summary) field ([#3226](https://github.com/cyberbotics/webots/pull/3226)).
    - Fixed crash where the deletion of an item in a MF field resulted in an endless regeneration which eventually lead to a crash ([#3188](https://github.com/cyberbotics/webots/pull/3188)).
    - Fixed crash when the top node of a [SolidReference](solidreference.md) was a [Transform](transform.md) or a [Group](group.md) ([#3039](https://github.com/cyberbotics/webots/pull/3039)).
    - Fixed the wireframe rendering badly affected by lighting ([#2806](https://github.com/cyberbotics/webots/pull/2806)).
    - Fixed external force/torque logic such that the closest dynamic [Solid](solid.md) ancestor is picked if the selected one lacks it ([#2635](https://github.com/cyberbotics/webots/pull/2635)).
    - Fixed a strategy used to find a MATLAB executable in the `PATH` environment variable ([#2624](https://github.com/cyberbotics/webots/pull/2624)).
    - Fixed various issues when an extern [Robot](robot.md) controller exits without disconnecting and reconnects to the same [Robot](robot.md) ([#3189](https://github.com/cyberbotics/webots/pull/3189)).
    - Fixed start-up of extern controllers in case a remaining temporary folder resulting from a previous Webots crash was still there ([#2800](https://github.com/cyberbotics/webots/pull/2800)).
    - Fixed broken multithreading in Python controllers due to Python GIL ([#3104](https://github.com/cyberbotics/webots/pull/3104)).
    - Fixed compilation of default controllers using Qt on Windows ([#2718](https://github.com/cyberbotics/webots/pull/2718)).
    - Fixed controllers output printed in the Webots console one step too late when running the simulation step-by-step ([#2741](https://github.com/cyberbotics/webots/pull/2741)).
    - Fixed invalid world loading errors cleared from the console when reverting to the empty world ([#2737](https://github.com/cyberbotics/webots/pull/2737)).
    - Fixed high DPI support on Windows and Linux ([#2631](https://github.com/cyberbotics/webots/pull/2631)).
    - Windows: Fixed double-click opening of a world file located in a path with UTF-8 characters ([#2750](https://github.com/cyberbotics/webots/pull/2750)).
    - Fixed adding textures to a simulation while a streaming-viewer is running ([#2704](https://github.com/cyberbotics/webots/pull/2704)).
    - Fixed crash applying [`wb_supervisor_node_add_force`](supervisor.md#wb_supervisor_node_add_force) on kinematic objects ([#3036](https://github.com/cyberbotics/webots/pull/3036)).
    - Fixed [Supervisor](supervisor.md) API operations on nodes defined in multiple nested PROTO fields ([#3036](https://github.com/cyberbotics/webots/pull/3036)).
    - Fixed crash due to [Supervisor](supervisor.md) MF field operations based on negative positions that were not translated into valid indices after resetting the simulation from the same [Supervisor](supervisor.md) controller ([#2997](https://github.com/cyberbotics/webots/pull/2997)).
    - Fixed [`wb_supervisor_node_reset_physics`](supervisor.md#wb_supervisor_node_reset_physics) not working if during the same step the node is also artificially moved with the [Supervisor](supervisor.md) API ([#2991](https://github.com/cyberbotics/webots/pull/2991)).
    - Fixed the [`wb_supervisor_field_get_count`](supervisor.md#wb_supervisor_field_get_count) function's returned value not updated after modifying the fields from the GUI or from another [Supervisor](supervisor.md) controller ([#2812](https://github.com/cyberbotics/webots/pull/2812)).
    - Fixed [`wb_supervisor_node_get_velocity`](supervisor.md#wb_supervisor_node_get_velocity) in MATLAB API returning 3 elements instead of 6 ([#2764](https://github.com/cyberbotics/webots/pull/2764)).
    - Fixed simulation reset
      - Fixed synchronization of [Supervisor](supervisor.md) simulation reset that was applied after the step and now it is applied at the very end of the step ([#2720](https://github.com/cyberbotics/webots/pull/2720)).
      - Fixed incorrect position retrieval immediately after resetting nested [Transform](transform.md) nodes ([#3051](https://github.com/cyberbotics/webots/issues/3051)).
      - Fixed reset of [Charger](charger.md) energy when the recharging [Robot](robot.md) battery is full ([#2879](https://github.com/cyberbotics/webots/pull/2879)).
      - Fixed [Camera](camera.md) image update in controllers after simulation reset ([#2725](https://github.com/cyberbotics/webots/pull/2725)).
      - Fixed reset of simulations including [BallJoint](balljoint.md) nodes like the [Stewart Platform](https://github.com/cyberbotics/webots/blob/master/projects/samples/demos/worlds/stewart_platform.wbt) ([#2593](https://github.com/cyberbotics/webots/pull/2593)) and ([#3394](https://github.com/cyberbotics/webots/pull/3394)).
      - Fixed step button status if simulation is reset from UI when the step button is disabled ([#2741](https://github.com/cyberbotics/webots/pull/2741)).
    - Fixed bug in the C++, Python and Java API where the [Robot.getDevice()](robot.md#wb_robot_get_device) methods were returning different objects when passing the same string argument for the device name ([#2957](https://github.com/cyberbotics/webots/pull/2957)).
    - Fixed the `robot_get_urdf` function to include leaf nodes in URDF ([#2803](https://github.com/cyberbotics/webots/pull/2803)).
    - Fixed issue where motor position limits in [Hinge2Joint](hinge2joint.md) and [BallJoint](balljoint.md) were enforced incorrectly ([#2825](https://github.com/cyberbotics/webots/pull/2825)).
    - Fixed issue where the hidden field of a [BallJoint](balljoint.md) is not stored in the world file when saving after the simulation has run ([#2964](https://github.com/cyberbotics/webots/pull/2964)).
    - Fixed [`Camera.getRecognitionObjects`](camera.md#wb_camera_recognition_get_objects) function not available and the return value of [`CameraRecognitionObject.getPositionOnImage`](camera.md#camera-recognition-object) and [`CameraRecognitionObject.getSizeOnImage`](camera.md#camera-recognition-object) in Java API ([#2923](https://github.com/cyberbotics/webots/pull/2923)).
    - Fixed return value type of [`CameraRecognitionObject.get_size`](camera.md#camera-recognition-object) Python function ([#2923](https://github.com/cyberbotics/webots/pull/2923)).
    - Fixed detection of scaled objects in the [Camera](camera.md) image using the [Recognition](recognition.md) functionality ([#2921](https://github.com/cyberbotics/webots/pull/2921)).
    - Fixed [Lens](lens.md) distortion ([#2961](https://github.com/cyberbotics/webots/pull/2961), [#3191](https://github.com/cyberbotics/webots/pull/3191)).
    - Fixed memory leak in [Display](display.md) image ([#2663](https://github.com/cyberbotics/webots/issues/2663)).
    - Fixed [Display](display.md) external window not updated when the attached camera image changes ([#2589](https://github.com/cyberbotics/webots/pull/2589)).
    - Fixed erasing [Pen](pen.md) ink on simulation reset ([#2796](https://github.com/cyberbotics/webots/pull/2796)).
    - Fixed the [Pen](pen.md) ink mixed with the background and other ink when the `inkDensity` is lower than 1.0 ([#2804](https://github.com/cyberbotics/webots/pull/2804)).
    - Fixed painting with the [Pen](pen.md) device on the bottom face of a [Cylinder](cylinder.md) geometry ([#2629](https://github.com/cyberbotics/webots/pull/2629)).
    - Fixed crash changing the [`Lidar.type`](lidar.md) field during the simulation run by requiring to save and reload the world ([#2983](https://github.com/cyberbotics/webots/pull/2983)).
    - Fixed [`Lidar.getLayerRangeImage`](lidar.md#wb_lidar_get_layer_range_image) Python and Java functions wrongly returning the full image ([#2799](https://github.com/cyberbotics/webots/pull/2799)).
    - Fixed visual bug where the [Lidar](lidar.md) point cloud disappears when out-of-range points are present ([#2666](https://github.com/cyberbotics/webots/pull/2666)).
    - Fixed update of [PointSet](pointset.md) subnodes ([#2766](https://github.com/cyberbotics/webots/pull/2766)).
    - Fixed [X3D export](../guide/web-interface.md) of USE nodes linking to DEF nodes declared in PROTO exposed fields ([#2687](https://github.com/cyberbotics/webots/pull/2687)).
    - Fixed the [robot window example](../guide/samples-howto.md#custom_robot_window-wbt) ([#2639](https://github.com/cyberbotics/webots/pull/2639)).
    - Fixed mecanum wheels [ContactProperties](contactproperties.md) in [YouBot](../guide/youbot.md) worlds ([#3025](https://github.com/cyberbotics/webots/pull/3025)).
    - Fixed value of the `verticalFieldOfView` for the [Hokuyo UTM-30LX](../guide/lidar-sensors.md#hokuyo-utm-30lx) ([#2972](https://github.com/cyberbotics/webots/pull/2972)).
    - Fixed [RandomBuilding](../guide/object-buildings.md#randombuilding) PROTO where different instances generated the same building ([#2897](https://github.com/cyberbotics/webots/pull/2897)).
    - Fixed [PedestrianCrossing](../guide/object-traffic.md#pedestriancrossing) PROTO model not correctly displaying the yellow stripes ([#2857](https://github.com/cyberbotics/webots/pull/2857)).
    - **Changed ROS message type published by the [Camera Recognition Objects](camera.md#wb_camera_recognition_get_objects) node that now sends a single message including all the recognized objects ([#3234](https://github.com/cyberbotics/webots/pull/3234))**.
    - **Changed ROS data type of [`/supervisor/node/get_type_name`](supervisor.md#wb_supervisor_node_get_type_name) service that now uses `webots_ros::node_get_name` instead of `webots_ros::node_get_type_name` ([#3202](https://github.com/cyberbotics/webots/pull/3202))**.
    - Fixed incorrect resetting of [PointLight](pointlight.md) nodes ([#3345](https://github.com/cyberbotics/webots/pull/3345)).
    - Fixed incorrect cleaning of [Light](light.md) node ([3374](https://github.com/cyberbotics/webots/pull/3374)).
    - Fixed crash provoked by canceling and switching world in the Guided Tour ([#3376](https://github.com/cyberbotics/webots/pull/3376)).
    - Fixed the path to the python command on macOS ([#3402](https://github.com/cyberbotics/webots/pull/3402)).
    - Fixed [HighwaySign](../guide/object-traffic.md#highwaysign) PROTO not displaying the texture ([#3407](https://github.com/cyberbotics/webots/pull/3407)).
    - Fixed the transparency of [Material](material.md) and [PBRAppearance](pbrappearance.md) such that the object are no longer visible to cameras when completely transparent ([#3436](https://github.com/cyberbotics/webots/pull/3436)).
  - Cleanup
    - Deleted deprecated DifferentialWheels node ([#2749](https://github.com/cyberbotics/webots/pull/2749)).
    - Changed structure of the [projects/samples/howto]({{ url.github_tree }}/projects/samples/howto) directory, so each demonstration is in a dedicated directory ([#2639](https://github.com/cyberbotics/webots/pull/2639)).
    - Deprecated `wb_supervisor_node_get_contact_point`, `wb_supervisor_node_get_contact_point_node`, and `wb_supervisor_node_get_number_of_contact_points` functions in favor of [`wb_supervisor_node_get_contact_points`](supervisor.md#wb_supervisor_node_get_contact_points) ([#3162](https://github.com/cyberbotics/webots/pull/3162)).
    - Remove the viewpoint_control benchmark that was not working in Webots ([#3192](https://github.com/cyberbotics/webots/pull/3192)).
  - Dependency Updates
    - Upgraded to Qt 5.15.2 on macOS ([#2721](https://github.com/cyberbotics/webots/pull/2721)).
    - Upgraded to Qt 5.15.2 on Linux ([#3089](https://github.com/cyberbotics/webots/pull/3089)).

## Webots R2021a
Released on December 15th, 2020.

  - New Features
    - Added the `wb_supervisor_node_get_from_device` function to retrieve the node's handle of a device ([#2074](https://github.com/cyberbotics/webots/pull/2074)).
    - Devices added during simulation run are now available in the robot controller ([#2237](https://github.com/cyberbotics/webots/pull/2237)).
    - Added the `wb_connector_is_locked` function to returns the current *isLocked* state of a [Connector](connector.md) ([#2087](https://github.com/cyberbotics/webots/pull/2087)).
    - Added the possibility to use an EUN (East-Up-North) coordinate system in the `coordinateSystem` field of the [WorldInfo](worldinfo.md) node ([#2228](https://github.com/cyberbotics/webots/pull/2228)).
    - Added the possibility to disable rendering in the `realtime` mode ([#2286](https://github.com/cyberbotics/webots/pull/2286)).
    - **Added a new argument to the [Supervisor](supervisor.md) `wb_supervisor_node_get_number_of_contact_points` API function to retrieve the number of contact points including those of the desendant nodes ([#2228](https://github.com/cyberbotics/webots/pull/2228)).**
    - Added a new `wb_supervisor_node_get_contact_point_node` [Supervisor](supervisor.md) API function to get the node reference associated to a given contact point ([#2228](https://github.com/cyberbotics/webots/pull/2228)).
    - Added two new functions to the [Camera](camera.md) API called [`wb_camera_get_exposure`](camera.md#wb_camera_get_exposure) and [`wb_camera_set_exposure`](camera.md#wb_camera_set_exposure) to retrieve and change the [Camera](camera.md) exposure ([#2363](https://github.com/cyberbotics/webots/pull/2363)).
    - Added a new functionality in the [Recognition](recognition.md) node and [Camera](camera.md) API for generating segmented ground truth images ([#2199](https://github.com/cyberbotics/webots/pull/2199)).
    - Added options to enable and disable recognition and segmentation functionalities in the [Camera](camera.md) tab of the default robot window ([#2431](https://github.com/cyberbotics/webots/pull/2431)).
    - Added a new [`wb_inertial_unit_get_quaternion`](inertialunit.md#wb_inertial_unit_get_quaternion) [InertialUnit](inertialunit.md) API function to get the orientation measurement represented as a quaternion ([#2424](https://github.com/cyberbotics/webots/pull/2424)).
    - **The [InertialUnit](inertialunit.md)`.lookupTable` field was deprecated and the related `wb_inertial_unit_get_lookup_table_size` and `wb_inertial_unit_get_lookup_table` functions were removed ([#2424](https://github.com/cyberbotics/webots/pull/2424)).**
    - Added a `PlasticFruitBox` and a `MetalStorageBox` PROTO object ([#2427](https://github.com/cyberbotics/webots/pull/2427)).
    - Added a `data_type` parameter to a Python method [`getPointCloud`](lidar.md#wb_lidar_get_point_cloud) that retrieves a `bytearray` representation of points a few times faster than the previous version.
  - Enhancements
    - Added support for Python 3.9 ([#2318](https://github.com/cyberbotics/webots/pull/2079)).
    - Improved [Solid](solid.md).`recognitionColors` value for the [BiscuitBox](../guide/object-kitchen.md#biscuitbox) PROTO model ([#2401](https://github.com/cyberbotics/webots/pull/2401)).
    - Improved documentation of [Camera](camera.md) image format and how to show the image retrieved through the [Camera](camera.md) API in a [Display](display.md) device ([#2443](https://github.com/cyberbotics/webots/pull/2443)).
    - The [Lidar](lidar.md) and [RangeFinder](rangefinder.md) devices now return infinity when the depth is out of range ([#2509](https://github.com/cyberbotics/webots/pull/2509)).
  - Bug fixes
    - **Fixed reversed pixel bytes order for [Display](display.md) images loaded with [`wb_display_image_new`](display.md#wb_display_image_new)** ([#2452](https://github.com/cyberbotics/webots/pull/2452)).
    - **Fixed cube, compact and flat texture mappings of [TexturedParallelepiped](../guide/object-geometries.md#texturedparallelepiped) proto** ([#2364](https://github.com/cyberbotics/webots/pull/2364)).
    - macOS: Fixed ability to inverse the distance sensor condition in BotStudio with the e-puck robot ([#2391](https://github.com/cyberbotics/webots/pull/2391)).
    - Fixed crash in the Python [Display.imageNew](display.md#wb_display_image_new) function when passing the image data in string/bytes format ([#2443](https://github.com/cyberbotics/webots/pull/2443)).
    - Fixed crash in the [Supervisor](supervisor.md) API occurring when [setting](supervisor.md#wb_supervisor_field_set_mf_bool) an item of a multiple field just before [inserting](supervisor.md#wb_supervisor_field_insert_mf_bool) or [removing](supervisor.md#wb_supervisor_field_remove_mf) an item in the same field during the same controller step ([#2366](https://github.com/cyberbotics/webots/pull/2366)).
    - Fixed values returned by the [Supervisor](supervisor.md) [get field value](supervisor.md#wb_supervisor_field_get_sf_bool) functions after [setting](supervisor.md#wb_supervisor_field_set_sf_bool) the field value in the same controller step ([#2375](https://github.com/cyberbotics/webots/pull/2375)).
    - Fixed supervisor label color change which was not working if the text remained unchanged ([#2357](https://github.com/cyberbotics/webots/pull/2357)).
    - Fixed recording of movies which was broken when the [WorldInfo](worldinfo.md).`basicTimeStep` was greater than 40 ([#2268](https://github.com/cyberbotics/webots/pull/2268)).
    - Fixed recording of movie canceled on simulation reset if recording is started from a [Supervisor](supervisor.md#wb_supervisor_movie_start_recording) controller ([#2406](https://github.com/cyberbotics/webots/pull/2406)).
    - macOS: Fixed handling of <kbd>Ctrl</kbd> key from the [Keyboard](keyboard.md) API ([#2265](https://github.com/cyberbotics/webots/pull/2265)).
    - Fixed synchronization bug in the start up of extern controllers when the `WEBOTS_PID` environment variable was defined ([#2260](https://github.com/cyberbotics/webots/pull/2260)).
    - Fixed large amount of CPU resources consumed by Webots in run mode when waiting for extern controllers ([#2377](https://github.com/cyberbotics/webots/pull/2377)).
    - Fixed [Lidar](lidar.md) and [RangeFinder](rangefinder.md) memory leak when the robot-window is opened ([#2210](https://github.com/cyberbotics/webots/pull/2210)).
    - Fixed noise generation for [Camera](camera.md), [Lidar](lidar.md) and [RangeFinder](rangefinder.md) producing fixed patterns on some GPUs (like the NVIDIA GeForce RTX series)([#2215](https://github.com/cyberbotics/webots/pull/2215)).
    - Fixed re-initialization of external camera window if recognition is enabled ([#2196](https://github.com/cyberbotics/webots/pull/2196)).
    - Fixed precision of devices using rays ([Camera](camera.md), [DistanceSensor](distancesensor.md), [Radar](radar.md), and [Receiver](receiver.md)) located on articulated robots' parts ([#2266](https://github.com/cyberbotics/webots/pull/2266)).
    - Fixed position lags of articulated robots' parts in recorded [animations](../guide/web-animation.md) ([#2266](https://github.com/cyberbotics/webots/pull/2266)).
    - Fixed the `inverse_kinematics` controller ([#2211](https://github.com/cyberbotics/webots/pull/2211)).
    - Fixed exported URDF axis when the [Joint](joint.md) anchor is not equal to the [Solid](solid.md) endpoint translation ([#2212](https://github.com/cyberbotics/webots/pull/2212)).
    - Fixed disappearing [DistanceSensor](distancesensor.md) rays [optional rendering](https://cyberbotics.com/doc/guide/the-user-interface#view-menu) after simulation reset ([#2276](https://github.com/cyberbotics/webots/pull/2276)).
    - Fixed cylinder-to-cylinder collision detection in certain cases ([#2282](https://github.com/cyberbotics/webots/pull/2282)).
    - Windows: Fixed parsing of arguments with spaces when starting Webots from a DOS console ([#2330](https://github.com/cyberbotics/webots/pull/2330)).
    - Fixed [Battery](robot.md#wb_robot_battery_sensor_enable) sensor when the [Robot](robot.md) contains a [Propeller](propeller.md) device ([#1801](https://github.com/cyberbotics/webots/pull/1801)).
    - Fixed [Motor](motor.md) target position not updated when changing the `position` field of a [JointParameters](jointparameters.md) node ([#2326](https://github.com/cyberbotics/webots/pull/2326)).
    - Fixed [`wb_motor_get_target_position`](motor.md#wb_motor_get_target_position) function if the joint initial position is not 0 ([#2326](https://github.com/cyberbotics/webots/pull/2326)).
    - Fixed the disabled `Help...` item in the context menu for some nodes ([#2327](https://github.com/cyberbotics/webots/pull/2327)).
    - Added missing `supervisor` field in the `Tractor` and `TeslaModel3` PROTO nodes ([#2351](https://github.com/cyberbotics/webots/pull/2351)).
    - Fixed infra-red [DistanceSensor](distancesensor.md) returned value when pointing at a texture used several times in the world (thanks to [Justin-Fisher](https://github.com/Justin-Fisher)) ([#2378](https://github.com/cyberbotics/webots/pull/2378)).
    - Fixed performance regression (thanks to [Acwok](https://github.com/Acwok)) ([#2434](https://github.com/cyberbotics/webots/pull/2434)).
    - **Deprecated all the device getter methods in Python.** They are replaced by a new [`Robot.getDevice`](robot.md#wb_robot_get_device) method which is closer to the C API ([#2510](https://github.com/cyberbotics/webots/pull/2510)).
    - **Fixed reversed pixel bytes order for [Display](display.md) images loaded with [`wb_display_image_new`](display.md#wb_display_image_new)** ([#2452](https://github.com/cyberbotics/webots/pull/2452)).
    - Fixed the [webots\_physics\_collide(dGeomID, dGeomID)](callback-functions.md) callback function so that it gets called even if the [`boundingObject`](solid.md#field-summary) is a [Group](group.md) node ([#2505](https://github.com/cyberbotics/webots/pull/2505)).
  - Cleanup
    - **Deleted `run` mode as the same behavior now can be achieved by using `fast` mode while keeping the rendering turned on ([#2286](https://github.com/cyberbotics/webots/pull/2286)).**
    - **Changed ROS message type published by the [GPS](gps.md) node when it is configured to work in `local` GPS coordinate system ([#2368](https://github.com/cyberbotics/webots/pull/2368))**.
    - Fixed updating the robot's device list after importing a device node at run time in a field descending from a joint ([#2482](https://github.com/cyberbotics/webots/pull/2482)).
  - Dependency Updates
    - Upgraded to Qt 5.15.1 on Windows ([#2312](https://github.com/cyberbotics/webots/pull/2312)).
    - **Stopped releasing Webots packages compatible with Ubuntu 16.04.** To run Webots on Ubuntu 16.04, please [compile from sources](https://github.com/cyberbotics/webots/wiki/Linux-installation) ([#2473](https://github.com/cyberbotics/webots/pull/2473)).
    - Updated the Thymio II Aseba controller to Aseba 1.3.3 ([#2518](https://github.com/cyberbotics/webots/pull/2518)).
