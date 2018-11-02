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
    
    
  
   并行度
	一个worker进程执行的是一个topo的子集
	一个worker进程会启动1..n个executor线程来执行一个topo的component
	一个运行的topo就是由集群中多台物理机上的多个worker进程组成

	executor是一个被worker进程启动的单独线程，每个executor只会运行1个topo的一个component
	task是最终运行spout或者bolt代码的最小执行单元

	默认：
		一个supervisor节点最多启动4个worker进程  ?
		每一个topo默认占用一个worker进程         ?
		每个worker进程会启动一个executor        ?
		每个executor启动一个task                ?
    
    
   =================================================
   
   
   storm  的grouping
   
   参考官网
   
   storm的  可靠性
   
   
   
   
   
   
   
   
   
   
   
   
    
