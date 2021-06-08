# iq_demo

# Dependencies 
iq_sim
iq_demo


# Basic demo
roslaunch iq_sim runway.launch

./startsitl.sh # inside iq_sim/scripts

roslaunch iq_sim apm.launch

rosservice call /mavros/cmd/arming "value: true"

rostopic pub /mavros/setpoint_position/local geometry_msgs/PoseStamped "header:
  seq: 0
  stamp:
    secs: 0
    nsecs: 0
  frame_id: 'map'
pose:
  position:
    x: 0.0
    y: 0.0
    z: 1.0
  orientation:
    x: 0.0
    y: 0.0
    z: 0.0
    w: 1.0" -r 10


rosservice call /mavros/cmd/arming "value: true"

rosservice call /mavros/cmd/takeoff "{min_pitch: 0.0, yaw: 0.0, latitude: 0.0, longitude: 0.0, altitude: 0.0}"
