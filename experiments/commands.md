# Commands

PS4 Teleoperation: 
python lerobot/scripts/control_robot.py teleoperate --robot-path lerobot/configs/robot/so100-ps4.yaml --robot-overrides '~cameras' --display-cameras 0
python lerobot/scripts/control_robot.py teleoperate --robot-path lerobot/configs/robot/so100-ps4.yaml



python lerobot/scripts/control_robot.py record --robot-path lerobot/configs/robot/so100-ps4.yaml --fps 30 --push-to-hub 0 --tags tutorial --warmup-time-s 5 --episode-time-s 60 --reset-time-s 30 --num-episodes 1 --single-task 'Pickup the object and put it in the box'


python lerobot/scripts/control_robot.py record --robot-path lerobot/configs/robot/so100-ps4.yaml --fps 30 --repo-id danielholl/koch_test --tags tutorial --warmup-time-s 5 --episode-time-s 60 --reset-time-s 30 --num-episodes 1 --single-task 'Pickup the object and put it in the box'

python lerobot/scripts/control_robot.py record --fps 30 --repo-id danielholl/koch_test --num-episodes 1 --run-compute-stats 0 --single-task 'Pickup the object and put it in the box'





{
    // Use IntelliSense to learn about possible attributes.
    // Hover to view descriptions of existing attributes.
    // For more information, visit: https://go.microsoft.com/fwlink/?linkid=830387
    "version": "0.2.0",
    "configurations": [

        {
            "name": "Record Dataset",
            "type": "debugpy",
            "request": "launch",
            "program": "${workspaceFolder}/lerobot/lerobot/scripts/control_robot.py",
            "python": "C:/Users/DHoll/anaconda3/envs/lerobot/python",
            "console": "integratedTerminal",
            "args": [
                "record",
                "--robot-path", "lerobot/lerobot/configs/robot/so100-ps4-debug.yaml",
                "--fps", "30",
                "--push-to-hub", "0",
                "--repo-id", "danielholl/test1",
                "--tags", "tutorial",
                "--warmup-time-s", "5",
                "--episode-time-s", "60",
                "--reset-time-s", "10",
                "--num-episodes", "1",
                "--single-task", "Pickup the object and put it in the box"
            ]
        }
    ]
}