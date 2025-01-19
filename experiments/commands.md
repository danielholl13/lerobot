# Commands

## PS4 Teleoperation:

### Without cameras
python lerobot/scripts/control_robot.py teleoperate --robot-path lerobot/configs/robot/so100-ps4.yaml --robot-overrides '~cameras' --display-cameras 0
### With cameras
python lerobot/scripts/control_robot.py teleoperate --robot-path lerobot/configs/robot/so100-ps4.yaml

## Record Dataset

### New Dataset
python lerobot/scripts/control_robot.py record --robot-path lerobot/configs/robot/so100-ps4.yaml --fps 30 --push-to-hub 0 --tags tutorial --warmup-time-s 5 --episode-time-s 60 --reset-time-s 30 --num-episodes 1 --single-task 'Pickup the object and put it in the box'

### Resume record dataset
python lerobot/scripts/control_robot.py record --robot-path lerobot/configs/robot/so100-ps4.yaml --fps 30 --push-to-hub 1 --repo-id danielholl/pickandplace1 --tags tutorial --warmup-time-s 10 --episode-time-s 60 --reset-time-s 1 --num-episodes 20 --single-task 'Pickup the object and put it in the box' --resume 1 --local-files-only 1

## Replay

### Replay an episode fron an online dataset
python lerobot/scripts/control_robot.py replay --robot-path lerobot/configs/robot/so100-ps4.yaml --fps 30 --repo-id danielholl/test2 --episode 0 --local-files-only 1
