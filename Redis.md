# Redis

安装步骤：

下载——》解压 tar -zxvf redis-4.0.2.tar.gz——》进入解压目录

——》进行编译: make——》安装 make install PREFIX=/usr/local/redis——》安装成功之后，进入reids/bin,找到redis-server——》运行:  ./redis-server

后台运行redis: 在解压目录找到redis.conf——》拷贝到安装目录：

cp redis.conf  /usr/local/redis/bin/——》cd /usr/local/redis/bin/

——》vim redis.conf——》修改 bind 127.0.0.1为bind 0.0.0.0 和

daemonize no 改为daemonize yes和修改密码requirepass 073018——》退出保存:wq——》启动redis: ./redis-server redis.conf

测试redis是否安装成功：./redis-cli -p 6379 -a 073018







