# ClusterChatServer
基于Muduo实现的负载均衡聊天服务器以及客户端

---
> 开发环境以及相关工具
- Ubuntu：20.04
- Nginx：1.12.2
- Redis：5.0.7
- Mysql：8.0.39
- Muduo：https://github.com/chenshuo/muduo
- Json库：https://github.com/nlohmann/json
---
> 项目结构
├── autobuild.sh
├── bin
├── build
├── CMakeLists.txt
├── include
│   ├── public.hpp
│   └── server
│       ├── chatserver.hpp
│       ├── chatservice.hpp
│       ├── db
│       │   └── db.h
│       ├── model
│       │   ├── friendmodel.hpp
│       │   ├── group.hpp
│       │   ├── groupmodel.hpp
│       │   ├── groupuser.hpp
│       │   ├── offlinemessagemodel.hpp
│       │   ├── user.hpp
│       │   └── usermodel.hpp
│       └── redis
│           └── redis.hpp
├── README.md
├── src
│   ├── client
│   │   ├── CMakeLists.txt
│   │   └── main.cpp
│   ├── CMakeLists.txt
│   └── server
│       ├── chatserver.cpp
│       ├── chatservice.cpp
│       ├── CMakeLists.txt
│       ├── db
│       │   └── db.cpp
│       ├── main.cpp
│       ├── model
│       │   ├── friendmoel.cpp
│       │   ├── groupmodel.cpp
│       │   ├── offlinemessagemodel.cpp
│       │   └── usermodel.cpp
│       └── redis
│           └── redis.cpp
├── test
│   ├── testjson
│   │   ├── json.hpp
│   │   ├── testjson
│   │   └── testjson.cpp
│   └── testmuduo
│       ├── CMakeLists.txt
│       └── muduo_server.cpp
└── thirdparty
    └── json.hpp

---
> 编译
1. cd build
2. cmake ..
3. make
---
> 运行
0. 确保Mysql，Redis，nginx已启动；确保已建立数据库且插入数据
    - sudo netstat -tanp
1. 启动服务器
    - ./bin/ChatServer 127.0.0.1 6000
    - ./bin/ChatServer 127.0.0.1 6002
2. 启动客户端
    - ./bin/ChatClient 127.0.0.1 8000
    - ./bin/ChatClient 127.0.0.1 8000

