
# smc_pyserial_lib
This is a child project of the Samuko Motor Control (SMC) project. This library can be used in your python robotic project to communicate with the **`smc_l298n_pid_driver module`** in order to send target angular velocities to the motors or receive the motor's angular velocity and angular position, after successful velocity PID setup with the [**`smc_l298n_setup_application`**](https://github.com/samuko-things-company/smc_l298n_setup_application).

> you can use it in your microcomputer robotics project (e.g Raspberry Pi, PC, etc.)

A simple way to get started is simply to try out and follow the example code


## Dependencies
- you'll need to pip install the pyserial library
  > pip3 install pyserial


## How to Use the Library
- Ensure you have the **`smc_l298n_pid_driver module`** interfaced with your preferred motors, setup the encoder and PID parameters with the **`smc_l298n_setup_application`**.

- Download (by clicking on the green Code button above) or clone the repo into your PC.

- check the serial port the driver is connected to:
  > The best way to select the right serial port (if you are using multiple serial device) is to select by path
  ```shell
  ls /dev/serial/by-path
  ```
  > you should see a value (if the driver is connected and seen by the computer), your serial port would be -> /dev/serial/by-path/[value]. for more info visit this tutorial from [ArticulatedRobotics](https://www.youtube.com/watch?v=eJZXRncGaGM&list=PLunhqkrRNRhYAffV8JDiFOatQXuU-NnxT&index=8)

  - OR you can also try this:
  ```shell
  ls /dev/ttyU*
  ```
  > you should see /dev/ttyUSB0 or /dev/ttyUSB1 and so on

- A simple way to get started is simply to try out and follow the example `motor_control.py` code.

- You can copy the **`smc_pyserial_lib.py`** file into your python robotics project, import the library as shown in the example `motor_control.py` code, add it to your code, and start using it.


## Basic Library functions and usage

- connect to smc_driver shield module
  > SMC("port_name or port_path")

- send target angular velocity command
  > .sendTargetVel(motorA_TargetVel, motorB_TargetVel)

- send PWM command
  > .sendPwm(motorA_PWM, motorB_PWM)

- read motors angular position
  > .getMotorsPos() # returns angPosA, angPosB

- read motors angular velocity
  > .getMotorsVel() # returns angVelA, angVelB