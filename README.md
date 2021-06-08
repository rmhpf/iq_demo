# iq_demo

# Dependencies 
iq_sim
iq_demo


# Basic demo
roslaunch iq_sim runway.launch

./startsitl.sh # inside iq_sim/scripts

roslaunch iq_sim apm.launch


rosservice call /mavros/set_mode "base_mode: 0
custom_mode: 'GUIDED'" 


rosservice call /mavros/cmd/arming "value: true"


rosservice call /mavros/cmd/takeoff "{min_pitch: 0.0, yaw: 0.0, latitude: 0.0, longitude: 0.0, altitude: 1.0}"



rostopic pub /mavros/setpoint_position/local ...
