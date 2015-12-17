# Trajectories for the humanoid robot HOAP-3

A set of movement trajectories developed for the humanoid robot HOAP-3

## Starting the robot
There are several ways to control the robot, the most usual is the wireless mode. 

* The first step is to switch on the robot. First you have to switch the '''logic power''' (internal computer of the robot) and then, the '''motor power''' (servos of the robot). Change the order may cause damage to the robot.
* The robot is initialized when its eyes are switched on.

![Power](/img/Power.png)


* You have to connect to HOAP wifi router, called corega. To do it you may log in the HOAP PC or connect from your own laptop. If you connect from your own laptop, skip this step, to start HOAP PC:

 login: root
 password: default

* Once you are connected to corega, you have to log to HOAP robot through telnet. Open a terminal and follow the instructions:

 $ telnet 10.59.145.197
 login: guest
 password: guest

 $ su
 password: default

* Now you are inside the robot, you have to initialize the encoders. The relative encoders will try to reach their origin, if you get an error, don't panic, do it again.
 $ cd /usr/local/hoap3/data
 $ sh start.sh

* Finally you can send a trajectory to the robot.
 $ sh walk.sh

* Or you can move its head.

 $ ../bin/sendone
 command:1,3,22,e,15
 command:1,3,22,e,75


## Stopping the robot 
* To stop the robot first you have to stop the servos.
 $ svoff
* Then you have to shut down the internal computer of the robot.
 $ poff
* The robot eyes start to shine and then turn off. In this moment the internal computer of the robot is shutted down. 
* Finally you have to switch off the '''motor power''' and then the '''logic power'''. Change the order may cause damage to the robot.


## Collection of trajectories 
All the trajectories are stored in data folder. To send a trajectory to the robot we use the instruction sendseq (for more details see the manual in docs folder).
    $ ../bin/sendseq < m03.csv



