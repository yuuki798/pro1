# File Service Application

## 项目概述
一个简单的可以正常使用的HTTP服务器，成品使用`cpp-httplib`库，实现了socket⽹络通信和基本的报⽂解析，实现了nio和event loop，实现了多线程。支持文件上传、下载、创建和删除文件夹等操作。

## 主要功能
- 可以在linux或docker容器环境下运⾏ ◦ 
- 可以⽀持多个⽤⼾同时和其建⽴TCP连接、通过⼀定的协议进⾏通信 ◦ 
- 支持文件上传、下载、创建和删除文件夹等操作。采用多级文件夹节点模式进行文件管理。

## 技术栈
- C++,
- cpp-httplib库,
- C++17 文件系统库 (std::filesystem),
- Docker,
- SSH,
- 多线程编程，
- Git

## 项目结构
```
/

|-- src/               # 一些前期尝试的时候废弃的产物，可以忽略
|-- cpp-httplib/       # httplib库
|-- src1/              # 后端功能函数，如文件上传、下载、创建和删除文件夹、线程池等

|-- test.cpp           # 主程序入口
```

## 如何运行
1. 克隆此仓库

2. 配置必要的环境

3. 进入项目目录：`cd [项目目录]`

4. 创建镜像`docker build -t hello .`

5. 运行docker容器，其中2222:22用于SSH主机交互，

   `docker run -d -p 2222:22 -p 8090:8090 hello`

6. 在项目的根目录下执行编译命令（例如，使用`g++`或`cmake`）。

7. 运行生成的可执行文件。

8. 开始使用！

## 特点与优势
- 支持文件上传到指定的文件夹。

- 支持文件下载，特别是图片文件时，会自动识别并使用正确的MIME类型。

- 支持创建和删除文件夹。

- 多线程支持，确保高并发处理。

- 使用Docker容器进行开发和部署。

  

## 开发过程遇到的困难和解决

- **白手起家无头绪**：基础仅限于学过C语言程序设计，对于技术栈不太了解。对此需要保持积极学习的态度，我首先在b站学习了开发一些基础。后面主要靠疯狂google和gpt。
- **不知道项目应该是什么样的**：在github上简易观摩了一个GO的微服务项目框架，稍微理解了一下。
- **没有看清题目**：由于对于Golang的热衷，忽视了题目要求仅限于C/C++的条件，废弃了一个编写了半天的Golang项目。
- **WSL2注册表错误**：WSL2的错误导致docker和虚拟机出现一些问题，花了较久找技术帖修复。
- **希望通过虚拟机访问本地服务**：尝试用ubuntu访问本地项目，却总是不成功，并且google和gpt的回答并不直截了当，绕了很多弯子，最后发现宿主机和虚拟机只是通过一个IPv4 地址相互连接的，在linux或docker容器中装了net-tools再ifconfig,在windows中直接ipconfig都可以直接找到这个值。
- **远程环境的配置**：由于题目要求linux上运行，因此连夜学习如何配置docker容器并且SSH远程连接进行开发。同时在linux虚拟机上尝试了交互操作。
- **一些AI建议或者IDE建议误导造成bug和项目崩溃**：AI建议和IDE建议固然好，但是还是需要谨慎采纳建议，不然自己的功能会被搞得一团糟，出现巨大bug，越修越大，除非读取存档。
- **进阶分布式存储的时候举步维艰**：由于在github上先前参考的项目竟然是用ceph分布式存储的，我就也尝试学习了一下它。由于需要多一些虚拟机，我就给电脑手动加装了一个硬盘。但是对于这个项目来说有点小题大作了，因此决定以后有时间再作尝试。
- **代码冗长**：尝试把一些类分离出去，放入src文件夹，并且把头文件关联好。
- **知识匮乏造成bug无法解决**：代码堆积出来一堆bug，基础又不扎实，找不到症结所在，熬夜到凌晨三点也没打通，索性放弃了。恰好刷到了一个httplib库，尝试了一下，居然很好用。认知更新到框架和库很香。
- **git不会操作**：版本控制出错了，花了很久去修复。
- 。。。

## 未来改进
- 尝试云存储技术或分布式存储技术

## 开发者
此项目由 **Li-can-cheng**开发，如有任何问题或建议，请通过 b19357160114@gmail.com找到我。

## 贡献

欢迎提交Pull Requests或Issues以改进项目。
