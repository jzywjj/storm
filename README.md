# storm
开发环境直接在pom.xml 直接加入想的jar 就能够运行

2.torm 集群的安装

安装 zookeeper集群
安装 jdk 1.7+  python 2.6.6
下载 storm realease 发布包解压  并修改storm.yaml配置文件


运行：
  Nimbus: Run the command "bin/storm nimbus" under supervision on the master machine.
  Supervisor: Run the command "bin/storm supervisor" under supervision on each worker machine. The supervisor daemon is responsible for starting and stopping worker processes on that machine.
  UI: Run the Storm UI (a site you can access from the browser that gives diagnostics on the cluster and topologies) by running the command
  "bin/storm ui" under supervision. The UI can be accessed by navigating your web browser to http://{ui host}:8080.
  
  
  配置文件
  
  1) storm.zookeeper.servers:  zookeeper 主机地址

storm.zookeeper.servers:
  - "111.222.333.444"
  - "555.666.777.888"
  
  storm.local.dir: "/mnt/storm"  storm 存储数据的位置
  
  
  nimbus.seeds: ["111.222.333.44"]   storm  nimbus master主机的地址  可以写多个实现高可用
  
  supervisor.slots.ports:  启动的worker 数  下面表示启动四个worker
    - 6700
    - 6701
    - 6702
    - 6703
    
    
