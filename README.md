# unitree-api-wrapper - for the Unitree Go1

## Setup

REQUIRES Python 3.8 BC THAT'S WHAT THE UNITREE LIBRARY IS COMPILED FOR FOR SOME REASON

Copy or symlink library https://github.com/unitreerobotics/unitree_legged_sdk/blob/master/lib/python/amd64/robot_interface.cpython-38-x86_64-linux-gnu.so

over into `/unitree_api_wrapper/lib`

## Train policy

IMPORTANT:

This works best if you don't have to estimate the linear/angular velocity from IMU.
There are 2 tasks in https://github.com/simonchamorro/legged-gym-rl/ that support this:

`a1_flat_novel` and
`go1_flat_novel`

The difference between `go1_flat_novel` and `go1_flat` is that the former is trained without access to the ground truth linear and angular velocities of the robot body.


## Run policy

(Make sure you're using a jitted policy - see README over here: https://github.com/simonchamorro/legged-gym-rl/tree/main/legged_gym)

1. Copy your policy into the ./policies directory,
2. Then cd into the scripts folder `cd scripts`
3. Edit the file `05-run-base-policy.py` and replace the `policy_path` parameter with the name of your policy
4. Run the script `python 05-run-base-policy.py`
5. ...
6. Profit
