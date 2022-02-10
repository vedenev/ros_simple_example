# ROS simple example
This is a learning of ROS with this tutorial:  
[Writing a Simple Publisher and Subscriber (C++)](http://wiki.ros.org/ROS/Tutorials/WritingPublisherSubscriber%28c%2B%2B%29)  
I made this in a Docker container.
  
Get docker image:  
```docker pull ros:rolling-ros1-bridge-focal```  
Run the image:  
```docker run -it -v /mnt/disk3tb/freelance/ros_learning/root:/root ros:rolling-ros1-bridge-focal /bin/bash```  
here I share /root internal folder to external folder to be able to save data after close the docker container.  
Setup ROS 1:  
```unset ROS_DISTRO```  
```source /opt/ros/noetic/setup.bash```  
 Create catkin workspace:  
```mkdir -p ~/catkin_ws/src```  
```cd ~/catkin_ws/```  
```catkin_make```  
Create package beginner_tutorials:  
```cd src```  
```catkin_create_pkg beginner_tutorials std_msgs roscpp```  
```cd beginner_tutorials/src```  
Install nano editor:  
```apt update```  
```apt install nano```  
create [talker.cpp](./catkin_ws/src/beginner_tutorials/src/talker.cpp) and [listener.cpp](./catkin_ws/src/beginner_tutorials/src/listener.cpp), modify [CMakeLists.txt](catkin_ws/src/beginner_tutorials/CMakeLists.txt), see [Writing a Simple Publisher and Subscriber (C++)](http://wiki.ros.org/ROS/Tutorials/WritingPublisherSubscriber%28c%2B%2B%29)  
compile:  
```cd ~/catkin_ws```  
```catkin_make```  
If a error, try to stop the container, run container again and run ```catkin_make``` again.    
Then use next tutorial [Examining the Simple Publisher and Subscriber](http://wiki.ros.org/ROS/Tutorials/ExaminingPublisherSubscriber):  
Run nodes:  
```roscore &```  
ctrl-C  
```cd ~/catkin_ws```  
```source ./devel/setup.bash```  
```rosrun beginner_tutorials talker > talker_log.txt &```  
ctrl-C  
```rosrun beginner_tutorials listener > listener_log.txt &```  
ctrl-C  
It should write logs to the files [talker_log.txt](./catkin_ws/talker_log.txt):  
```text
[0m[ INFO] [1644467507.486462480]: hello world 0[0m
[0m[ INFO] [1644467507.586523810]: hello world 1[0m
[0m[ INFO] [1644467507.686495980]: hello world 2[0m
...
```
[listener_log.txt](./catkin_ws/listener_log.txt):  
```text
[0m[ INFO] [1644467593.686626953]: I heard: [hello world 862][0m
[0m[ INFO] [1644467593.786564990]: I heard: [hello world 863][0m
[0m[ INFO] [1644467593.886566036]: I heard: [hello world 864][0m
...
```
To print nodes list:  
```rosnode list```  
result:
```text
/listener
/rosout
/talker
```
kill nodes:  
```rosnode kill -a```  
ctrl-C  





  

