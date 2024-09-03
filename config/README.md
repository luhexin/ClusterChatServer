nginx默认并没有编译tcp负载均衡模块，需要加入--with-stream参数来激活这个模块
- lu@tony-virtual-machine:~/package/nginx-1.12.2$ sudo ./configure --with-stream
- lu@tony-virtual-machine:~/package/nginx-1.12.2$ sudo make && sudo make install
    - 编译完成后，默认安装在了/usr/local/nginx目录
- lu@tony-virtual-machine:~/package/nginx-1.12.2$ cd /usr/local/nginx/
    - 可执行文件在sbin目录里面，配置文件在conf目录里面; 替换原配置文件为当前目录下配置文件
- ./nginx -s reload平滑重启