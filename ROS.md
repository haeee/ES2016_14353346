# ROS
14353346	 许瑶婷
***
##  设置源
`sudo sh -c 'echo "deb http://packages.ros.org/ros/ubuntu $(lsb_release -sc) main" > /etc/apt/sources.list.d/ros-latest.list'`    
![](http://yotuku.cn/link?url=VklOqbCAeG&tk_plan=free&tk_storage=tietuku&tk_vuid=19634417-c10e-44e8-bbcb-cbf6b232579c&tk_time=2016111123)  
 
 ## 设置Keys  
` sudo apt-key adv --keyserver hkp://ha.pool.sks-keyservers.net:80 --recv-key 0xB01FA116`  
![](http://yotuku.cn/link?url=EkGJf0RxM&tk_plan=free&tk_storage=tietuku&tk_vuid=19634417-c10e-44e8-bbcb-cbf6b232579c&tk_time=2016111123)   

## 安装ROS  
+ 先更新系统软件  
`sudo apt-get update`   
![](http://yotuku.cn/link?url=NJOvM00xz&tk_plan=free&tk_storage=tietuku&tk_vuid=19634417-c10e-44e8-bbcb-cbf6b232579c&tk_time=2016111123)   

+ 安装豪华版套餐   
`sudo apt-get install ros-kinetic-desktop-full`   
![](http://yotuku.cn/link?url=NJBpM00xM&tk_plan=free&tk_storage=tietuku&tk_vuid=19634417-c10e-44e8-bbcb-cbf6b232579c&tk_time=2016111123)    

+ 查看可使用的包  
`apt-cache search ros-kinetic`   
![](http://yotuku.cn/link?url=EJ-370RxM&tk_plan=free&tk_storage=tietuku&tk_vuid=19634417-c10e-44e8-bbcb-cbf6b232579c&tk_time=2016111123)   


## 初始化ROS
+ `sudo rosdep init`   
![](http://yotuku.cn/link?url=NyouXCRgf&tk_plan=free&tk_storage=tietuku&tk_vuid=19634417-c10e-44e8-bbcb-cbf6b232579c&tk_time=2016111123)   
+ `rosdep update`  
![](http://yotuku.cn/link?url=EyWjQ0Aez&tk_plan=free&tk_storage=tietuku&tk_vuid=19634417-c10e-44e8-bbcb-cbf6b232579c&tk_time=2016111123)  


## 配置环境变量   
`echo "source /opt/ros/kinetic/setup.bash" >> ~/.bashrc`   
` source ~/.bashrc`   
![](http://yotuku.cn/link?url=EJiH4RRxf&tk_plan=free&tk_storage=tietuku&tk_vuid=19634417-c10e-44e8-bbcb-cbf6b232579c&tk_time=2016111123)   

## 安装rosinstall   
` sudo apt-get install python-rosinstall`   
![](http://yotuku.cn/link?url=NJzj4ARxG&tk_plan=free&tk_storage=tietuku&tk_vuid=19634417-c10e-44e8-bbcb-cbf6b232579c&tk_time=2016111123)   


## 测试ROSCORE   
`roscore`   
![](http://yotuku.cn/link?url=EJYRE0RlM&tk_plan=free&tk_storage=tietuku&tk_vuid=19634417-c10e-44e8-bbcb-cbf6b232579c&tk_time=2016111123)   


***
## 参考网址：    
[http://wiki.ros.org/kinetic/Installation/Ubuntu](http://wiki.ros.org/kinetic/Installation/Ubuntu)   
[http://blog.csdn.net/xuehuafeiwu123/article/details/52549872](http://blog.csdn.net/xuehuafeiwu123/article/details/52549872)   
[http://blog.csdn.net/zhangrelay/article/details/51364622](http://blog.csdn.net/zhangrelay/article/details/51364622)   
[http://www.cnblogs.com/liu-fa/p/5779206.html](http://www.cnblogs.com/liu-fa/p/5779206.html)   