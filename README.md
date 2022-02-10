# ROS simple example
This is learning of ROS by this tutorial:  
[Writing a Simple Publisher and Subscriber (C++)](http://wiki.ros.org/ROS/Tutorials/WritingPublisherSubscriber%28c%2B%2B%29)  
I made this in Docker.
  
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
create [talker.cpp](./catkin_ws/src/beginner_tutorials/src/talker.cpp) and istener.cpp, see [Writing a Simple Publisher and Subscriber (C++)](http://wiki.ros.org/ROS/Tutorials/WritingPublisherSubscriber%28c%2B%2B%29)  
Then use next tutorial [Examining the Simple Publisher and Subscriber](http://wiki.ros.org/ROS/Tutorials/ExaminingPublisherSubscriber):  
  


  

