1. 取消打开文件数限制

/etc/security/limits.conf
* soft nofile 65536
* hard nofile 65536
* soft nproc 131072
* hard nproc 131072

/etc/security/limits.d/90-nproc.conf
* soft nofile 65536
* hard nofile 65536
* soft nproc 131072
* hard nproc 131072

2. 取消SELINUX
vi /etc/selinux/config
SELINUX=disabled

3. 关闭防火墙
service iptables stop

4. 安装依赖
yum install -y libtool
yum install -y *unixODBC*

5. 重启电脑 reboot

6. 安装

7. 启动clickserver
前台启动
clickhouse-server --config-file=/etc/clickhouse-serve/config.xml

后台启动
nohup clickhouse-service --config-file=/etc/clickhouse-service/config.xml >null 2>&1 &

8. 使用client连接service
clickhouse-client

9. 集群安装
重复上面1-5步骤
vi /etc/clickhouse-server/config.xml
修改
<listen_host>::<listen_host>
注释掉下面的
<!-- <listen_host>::2</listen_host> -->
<!-- <listen_host>127.0.0.1</listen_host> -->

10. 集群安装在etc目录下创建metrika.xml
vi /etc/metrika.xml
主机配置， zk配置

11. 分别启动


https://blog.csdn.net/ctypyb2002/article/details/116046451


