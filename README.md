# RCJ-Soccer-LW-2019

This was my program for RoboCup Junior Soccer (Lightweight) Singapore Open 2019 as part of Team Ascension. We finished 4th in the competition, where teams build robots to play robot soccer with an Infrared Ball in a 2v2 match.
#
Team members consists of: 
* Deng Jun (myself, programmer)
* Justin (electrical designer) 
* Shaoliang (hardware/mech designer)

This program was adapted from LJStand, the 2018 Lightweight World Champions from Brisbane Boys' College, Australia. (Their gitbucket can be found here: https://bitbucket.org/ljstand/)
We were inspired by their unique IR ring which could detect the IR signals emitted from the ball very well, which led to them dominating the international competition in 2018.

# Robot Description (aka features)
* Teensy 3.5/3.6 (Main microcontroller)
* Arduino Nano (Slave microcontroller via Serial Communication)
* 3 HC-SR04 Ultrasonic sensors
* 16 TSSP58038 IR sensors placed in a ring
* 28 pairs of white LEDs and LDRs to form a light sensor ring
* Adafruit BNO-055 Compass
* 4x motor drivers and brushless motors
* Self-designed 3D-printed motor mounts and wheels with rubber rollers
* Self-designed carbon fibre plates and PCBs
* OpenMV M7 Camera (eventually scrapped)

Our robot is an omni-directional robot made up of 2 layers (2nd layer is a PCB layer) and is supported with copper and plastic stands, weighing less than 1100g in total. The Arduino Nano (operating as a 'slave') processes data from the 
ultrasonic sensors and sends the data over to the main Teensy controller. The Teensy combines the ultrasonic data with the light sensor data to help keep the robot within the
playing boundaries. The Teensy also processes the remaining data from the other robot components, such as sorting the IR strength detected by the sensors from the strongest to identity the angle of the ball relative to the robot. The compass helps to keep the robot facing front while its moving around the field. 

# Robot Strategies
Generally speaking, we designated 1 robot as the attacker while the other functions as a goalie. The attacker would orbit the ball until its behind, where it charges forward towards the opposing goal. We tried to implement some forms of localisation using the ultrasonic sensors to determine our position on the field and adjust its path accordingly such that it is less likely to miss the goal. Sadly, we did not have enough time to fully refine our strategy. We also orignally planned to integrate an OpenMV M7 camera so that we can detect the goals and improve our localisation efforts. 

# What Actually Happened
Many of our robot parts came late and as such, the final iteration of our robot was not fully assembled until about 3 weeks prior to the competition. Apart from a lack of time, we also encountered many hardware failures and as such, some parts of the program were not properly coded. The BNO-055 compass failed to callibrate properly on the actual competition day and we were forced to do without a working compass for most of our matches. The front light sensors were also returning incosistent readings, presumeably due to poor soldering. This led to our robots going out-of-bounds many times as we didn't have a front ultrasonic sensor at the front we could fall back on to detect where we were on the playing field. 

Ultimately, placing 4th was not ideal, but given the circumstances where we literally only assembled the robot and got it up and running 3 weeks before the competition, it was to be expected. This was also my first major coding project as I have only picked up coding last year so all in all, it was a great learning experience despite the problems we encountered.

Many thanks to my teammates Shaoliang and Justin for taking charge of the mechanical and electronic design respectively. A huge shoutout to entire Hwa Chong Robotics community for all the advice and support given as well.
