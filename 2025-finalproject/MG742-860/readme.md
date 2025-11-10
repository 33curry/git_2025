# 课程学习总结
## 学习中对课程的认识
  我很高兴自己具备了第一轮考核的能力，在考核通知发送前就已经学习了C/C++，也了解了该课程主要的学习内容：C、C++、Git、CMake、ROS等等，通过该课程也知道了在视觉组中主要倾向的学习与开发方向。在学习中，知道了加入Dyx需要具备很多的系统操作和编程语言知识，当然，紧跟课程的步伐去学习也是可以通过考核的，在课程学习中不能掉以轻心，要多理解课程中讲解的知识中背后的具体实现。
## 课程中的收获
  首先，该课程让我复习了C/C++，并且线性地学习了linux、git、cmake、ros，在课程中，每一次知识的讲解我都会去查找其背后是如何实现的，以及其含义，比如第一课的Linux中，在之前服务器上不懂的命令、文件结构，在第一课后都有了比较明确的认识，比如：
```bash
apt install
```
这个命令是通过apt接口从Ubuntu源安装软件包的指令，其中apt属于一个命令，后面跟着的是该命令要执行什么操作，类似的还有bash、git、ros等。
  Git、CMake等的学习中类似，学习了如何fork并pr，cmake中如何编写cmakelists文件。现在在学习ros中，也知道了ros中需要创建工作空间、catkin_ws文件夹中有严格的文件划分，但是在目前的学习中并没有遇到太大的困难。
## Git  
其中最有意思的地方是github现在不再支持http的认证，在仓库中要复制ssh链接才可以认证。
```bash
ssh -T git@github.com
# 输出：
# Hi MG742-860! You've successfully authenticated, but GitHub does not 
# provide shell access.
# 这样就认证成功了，接着连接仓库：
git remote add origin git@github.com:MG742-860/git_2025.git
# 然后就可以：
# git add/commit/push...

```
## CMake
其中最基本且最重要的就是：
* 最小CMake版本
* 项目名字
* 可执行文件
```cmake
cmake_minimum_required(VERSION 3.0.1)
project(Project_name)
add_executable(exe_name main.cpp ...)
```
当然还有头文件路径等：
```cmake
include_directories($path)
```
以及还有链接库：
* 静态库（*.a）
* 动态库（*.so）
```cmake
# 生成静态库：
add_libraries($path)
# 链接已有静态库：
target_link_libraries(exe_name ${LIBRARIES} ...)
```
cmake最好的掌握方式就是使用cmake，用的多了自然而然就知道以前不动的指令是什么意思、该用什么指令了
## ROS
  目前ROS学习比较简单，但是不知道后续是否会加大难度，比如视觉算法、物体识别、雷达等等，按部就班或许会好一点，不要乱了自己的脚步，打乱已经建立好的学习思路。
  ROS的包中的指令都需要在官网上查找，很不方便，每个包都有自己的变量，应该考虑自己写一个文档便于后续查找（后续或许有学长已经整理好的文档？）。

  现在ROS已经来到了第三课，也开始上难度了，不过凭借已有的CPP经验，对于ROS包的简单开发还是能胜任的。
  每个包不管是pub还是sub都要有：
```CPP
//首先进行ros初始化
ros::init(argc, argv "name_node");
/*其中argv类型是：char * argv[]，由编译器提示并自动补全的是：char const* argv[] 类型，这点要注意*/
//然后是ros大管家的声明：
ros::NodeHandle nh;
```
  在进行了这几行代码的初始化之后才可以通过ros大管家nh声明sub、pub，然后在进行你的代码块。
***
  对于发布者pub：
```CPP
/*发布者不能不向话题topic发送消息，要用循环进行消息的发送*/
while(ros::ok()){
    /*循环条件不能为真(比如写true)，否则节点程序不会响应外部信号*/
    /*在这里写下你的代码*/
    //比如:
    msg.data = "msg form name_node";
}
```
***
对于订阅者sub：
```CPP
//订阅者要一直接收发布者的消息
//方法一：
ros::spin();
//方法二：
while(ros::ok()){
    ros::SpinOnce();
}
//以上方法都可以不断接收发布者的消息，而不退出程序
```
***
有关ros的还有两种配置文件：
* *.launch
* *.yaml

.launch文件可以通过roslaunch命令一次性启动多个包，还能配置一些参数，十分便捷

.yaml文件和配置文件类似，里面记录着一些键值对，用于程序读取该程序并进行对相应变量的复制
## 收获总结
  新的知识：Git、CMake、ROS，除此以外还对已经学习的linux有了更明确的认识