# Commands

## PS4 Teleoperation:

### Without cameras
python lerobot/scripts/control_robot.py teleoperate --robot-path lerobot/configs/robot/so100-ps4.yaml --robot-overrides '~cameras' --display-cameras 0
### With cameras
python lerobot/scripts/control_robot.py teleoperate --robot-path lerobot/configs/robot/so100-ps4.yaml

## Record Dataset

### New Dataset
python lerobot/scripts/control_robot.py record --robot-path lerobot/configs/robot/so100-ps4-3cam.yaml --fps 30 --push-to-hub 0 --repo-id danielholl/pickandplace2 --tags tutorial --warmup-time-s 5 --episode-time-s 60 --reset-time-s 1 --num-episodes 10 --single-task 'Pickup the object and put it in the box' --num-image-writer-processes 4 --num-image-writer-threads-per-camera 4 --resume 1 --local-files-only 1

### Resume record dataset
python lerobot/scripts/control_robot.py record --robot-path lerobot/configs/robot/so100-ps4.yaml --fps 30 --push-to-hub 1 --repo-id danielholl/pickandplace1 --tags tutorial --warmup-time-s 10 --episode-time-s 60 --reset-time-s 1 --num-episodes 20 --single-task 'Pickup the object and put it in the box' --resume 1 --local-files-only 1

## Replay

### Replay an episode fron an online dataset
python lerobot/scripts/control_robot.py replay --robot-path lerobot/configs/robot/so100-ps4.yaml --fps 30 --repo-id danielholl/test2 --episode 0 --local-files-only 1


## Visualize dataset

python lerobot/scripts/visualize_dataset_html.py --repo-id danielholl/pickandplace1

## Train

python lerobot/scripts/train.py dataset_repo_id=danielholl/pickandplace1 policy=act_so100_real env=so100_real hydra.run.dir=outputs/train/act_so100_test hydra.job.name=act_so100_test device=cuda wandb.enable=false

### Copy checkpoints from EC2 Instance

scp -r -i ".ssh/vs-ec2-key.pem" ubuntu@ec2-3-249-211-46.eu-west-1.compute.amazonaws.com:/home/ubuntu/lerobot/outputs C:\Users\DHoll\Desktop\robot



## Eval


python lerobot/scripts/control_robot.py record --robot-path lerobot/configs/robot/so100-ps4.yaml --fps 30 --repo-id $danielholl/eval_act_so100_test --tags so100 tutorial eval --warmup-time-s 5 --episode-time-s 60 --reset-time-s 10 --num-episodes 10 -p outputs/train/act_so100_test/checkpoints/last/pretrained_model

python lerobot/scripts/control_robot.py record --robot-path lerobot/configs/robot/so100-ps4.yaml --fps 30 --repo-id danielholl/eval_act_so100_test --tags so100 tutorial eval --warmup-time-s 5 --episode-time-s 60 --reset-time-s 10 --num-episodes 10 -p C:/Users/DHoll/Desktop/robot/lerobot/outputs/train/act_so100_test/checkpoints/last/pretrained_model --single-task 'Pickup the object and put it in the box'