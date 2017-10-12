# SVO_edgelete
ChangeList， compare with the origin svo:
1. add edgelete feature
2. inition VO: auto select H model and E model
3. Keyframe selection 
4. add pangolin to draw trajectory and remove ROS

## 安装程序（ubuntu）
### 安装依赖项
* boost - c++ Librairies (thread and system are needed)
	> sudo apt-get install libboost-all-dev	
* Eigen 3 - Linear algebra
	> apt-get install libeigen3-dev
* Sophus - Lie groups
 	> cd workspace
 	> 
 	> git clone https://github.com/strasdat/Sophus.git	
 	> 
    > cd Sophus	
    > 
 	> <font color=red>git checkout a621ff</font>	
 	> 
 	> mkdir build	
 	> 
 	> cd build	
 	> 
 	> cmake ..	
 	> 
 	> make


* g2o - General Graph Optimization **OPTIONAL**	
	Only required if you want to run bundle adjustment. It is not necessary for visual odometry. 
    I suggest an out-of-source build of g2o:
	> cd workspace	
	> 
	> git clone https://github.com/RainerKuemmerle/g2o.git
	> 
	> cd g2o	
	> 
	> mkdir build	
	> 
	> cd build	
	> 
	> cmake ..	
	> 
	> make	
	> 
	> sudo make install

### 编译
下载程序到指定路径，程序默认不使用g2o，如果编译的时候想使用g2o，修改cmakerlists.txt：
>SET(HAVE_G2O TRUE)   #TRUE  FALSE

开始编译：
>mkdir build
>
> cmake ..	
> 
> make

## Run code
目前可供测试的程序是test文件夹下的test_pipline和test_live_vo。

Offline datasets：

	To run on tum dataset：test_pipline
	To run on euroc dataset：test_piplel_euroc

Online camera：test_live_vo

## Results

## Authors
Yijia He, Institute of Automation, Chinese Academy of Sciences

Wei Wei, Institute of Computing Technology, Chinese Academy of Sciences

Yanan Gao, Institute of Computing Technology, Chinese Academy of Sciences