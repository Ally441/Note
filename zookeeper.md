### zookeeper

- 中间件，提供协调服务
- 作用于分布式系统，发挥其优势，可以为大数据服务
- 支持java,提供java和c语言的客户端api

分布式系统

- 很多台计算机组成一个整体，一个整体一致对外并且处理同一请求
- 内部的每台计算机都可以相互通信(rest/rpc)
- 客户端到服务端的一次请求到响应结束会经历多台计算机

![image-20201029220849020](C:\Users\Ally\AppData\Roaming\Typora\typora-user-images\image-20201029220849020.png)

![image-20201029220905440](C:\Users\Ally\AppData\Roaming\Typora\typora-user-images\image-20201029220905440.png)

![image-20201029220939946](C:\Users\Ally\AppData\Roaming\Typora\typora-user-images\image-20201029220939946.png)

##### 常用的zookeeper java客户端

- zookeeper原生api
- zkclient
- Apache curator

###### zookeeper原生api的不足之处：

- 超时重连，不支持自动，需要手动操作
- Watch注册一次后会失效
- 不支持递归创建节点

Apache curator

- 提供更多解决方案并且实现简单：比如 分布式锁
- 提供常用的ZooKeeper工具类
- 编程风格更爽

#### Curator创建zookeeper客户端的步骤：

1. 创建重试策略- retryPolicy
2. 创建客户端- client
3. 初始化客户端

