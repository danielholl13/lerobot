# Commands

PS4 Teleoperation: 
python lerobot/scripts/control_robot.py teleoperate --robot-path lerobot/configs/robot/so100-ps4.yaml --robot-overrides '~cameras' --display-cameras 0




python lerobot/scripts/control_robot.py record --robot-path lerobot/configs/robot/so100-ps4.yaml --fps 30 --push-to-hub 0 --tags tutorial --warmup-time-s 10 --episode-time-s 30 --reset-time-s 30 --num-episodes 2 --single-task 'Pickup the object and put it in the box'