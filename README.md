# iq_demo

# Dependencies 
iq_sim
iq_demo


# Basic demo
roslaunch iq_sim runway.launch

./startsitl.sh # inside iq_sim/scripts

roslaunch iq_sim apm.launch

rosservice call /mavros/cmd/arming "value: true"
