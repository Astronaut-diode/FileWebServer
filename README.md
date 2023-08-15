# FileWebServer

## Introduce

本项目为C++11编写的文件服务器，使用有限状态机解析HTTP请求，支持用户注册、用户登陆、上传文件、共享文件、改变位置、下载文件，拷贝文件等功能。

## Technical points

- 用状态机解析HTTP 1.1请求报文，支持GET/POST两种请求方式；
- 采用信号及升序链表管理定时器系统，统一事件源，处理非活动连接；
- 采用线程池+非阻塞socket+I/O多路复用实现Reactor以及Proactor两种并发模型；
- 采用连接池，基于MySQL实现用户信息持久化；
- 采用生产者-消费者模型，实现异步/同步日志系统，记录服务器运行状态；
- 访问服务器数据库实现用户注册、登录、上传、下载、分享等功能；



## Demo演示
https://github.com/Astronaut-lunikhod/FileWebServer/assets/57606131/4cabc998-b52e-43db-9245-50f1f6d756f0



## Environment

- OS: Ubuntu 18.04
- MySQL: 5.7.42
- Redis: 4.0.9
- Compiler: g++ 7.5
- 浏览器测试：Windows、Linux下使用Chrome、Edge、FireFox均可。


## Usage


1. 创建FileWebServer数据库。

   ``` sql
   create database FileWebServer character set utf8mb4 collate utf8mb4_unicode_ci;
   ```

2. ``` shell
   make # 进行编译
   ```

3. ``` shell
   ./FileWebServer
   ```

8. 浏览器端访问端口号默认使用7777
   **IP地址:端口号/register.html**进行注册，**IP地址:端口号/login.html**进行登录。


## 致谢

[TinyWebServer](https://github.com/qinguoyi/TinyWebServer)

