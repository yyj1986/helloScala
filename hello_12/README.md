参考资料

https://github.com/datastax/SparkBuildExamples/tree/master/scala/gradle/oss

spark cassandra connector的文档中提到了这个示例参考
我是从这里才了解到gradle作为scala, spark的构建工具

spark 2.2.1 要求 scala 2.11.x 版本，参考spark文档:
https://spark.apache.org/docs/2.2.1/

官方文档说明了 scala 的版本要求

具体要求的版本号，可以到 https://mvnrepository.com/ 查找

启动spark
=========

./sbin/start-master.sh -h localhost
./sbin/start-slave.sh spark://localhost:7077

spark自带管理器
http://localhost:8080/

交互式环境
========

./bin/spark-shell --master spark://localhost:7077

提交计算
=======

spark-submit --master spark://localhost:7077 --class hello_12.SparkPi ./build/libs/hello_12-all.jar


20/04/27 10:54:36 WARN Utils: Your hostname, yyj-ZHAOYANG-E51-80 resolves to a loopback address: 127.0.1.1; using 192.168.124.10 instead (on interface wlp3s0)
20/04/27 10:54:36 WARN Utils: Set SPARK_LOCAL_IP if you need to bind to another address
20/04/27 10:54:37 WARN NativeCodeLoader: Unable to load native-hadoop library for your platform... using builtin-java classes where applicable
Using Spark's default log4j profile: org/apache/spark/log4j-defaults.properties
20/04/27 10:54:37 INFO SparkContext: Running Spark version 2.4.5
20/04/27 10:54:37 INFO SparkContext: Submitted application: Spark Pi
20/04/27 10:54:37 INFO SecurityManager: Changing view acls to: yyj
20/04/27 10:54:37 INFO SecurityManager: Changing modify acls to: yyj
20/04/27 10:54:37 INFO SecurityManager: Changing view acls groups to: 
20/04/27 10:54:37 INFO SecurityManager: Changing modify acls groups to: 
20/04/27 10:54:37 INFO SecurityManager: SecurityManager: authentication disabled; ui acls disabled; users  with view permissions: Set(yyj); groups with view permissions: Set(); users  with modify permissions: Set(yyj); groups with modify permissions: Set()
20/04/27 10:54:37 INFO Utils: Successfully started service 'sparkDriver' on port 45967.
20/04/27 10:54:37 INFO SparkEnv: Registering MapOutputTracker
20/04/27 10:54:37 INFO SparkEnv: Registering BlockManagerMaster
20/04/27 10:54:37 INFO BlockManagerMasterEndpoint: Using org.apache.spark.storage.DefaultTopologyMapper for getting topology information
20/04/27 10:54:37 INFO BlockManagerMasterEndpoint: BlockManagerMasterEndpoint up
20/04/27 10:54:37 INFO DiskBlockManager: Created local directory at /usr/local/spark-2.4.5/blockmgr-d804fba1-6cc7-4813-8006-99c41a5b6afb
20/04/27 10:54:37 INFO MemoryStore: MemoryStore started with capacity 93.3 MB
20/04/27 10:54:37 INFO SparkEnv: Registering OutputCommitCoordinator
20/04/27 10:54:38 INFO Utils: Successfully started service 'SparkUI' on port 4040.
20/04/27 10:54:38 INFO SparkUI: Bound SparkUI to 0.0.0.0, and started at http://192.168.124.10:4040
20/04/27 10:54:38 INFO SparkContext: Added JAR file:/home/yyj/yyj/helloScala/hello_12/./build/libs/hello_12-all.jar at spark://192.168.124.10:45967/jars/hello_12-all.jar with timestamp 1587956078083
20/04/27 10:54:38 INFO StandaloneAppClient$ClientEndpoint: Connecting to master spark://localhost:7077...
20/04/27 10:54:38 INFO TransportClientFactory: Successfully created connection to localhost/127.0.0.1:7077 after 37 ms (0 ms spent in bootstraps)
20/04/27 10:54:38 INFO StandaloneSchedulerBackend: Connected to Spark cluster with app ID app-20200427105438-0002
20/04/27 10:54:38 INFO StandaloneAppClient$ClientEndpoint: Executor added: app-20200427105438-0002/0 on worker-20200421133619-192.168.124.10-46703 (192.168.124.10:46703) with 4 core(s)
20/04/27 10:54:38 INFO StandaloneSchedulerBackend: Granted executor ID app-20200427105438-0002/0 on hostPort 192.168.124.10:46703 with 4 core(s), 1024.0 MB RAM
20/04/27 10:54:38 INFO Utils: Successfully started service 'org.apache.spark.network.netty.NettyBlockTransferService' on port 45245.
20/04/27 10:54:38 INFO NettyBlockTransferService: Server created on 192.168.124.10:45245
20/04/27 10:54:38 INFO StandaloneAppClient$ClientEndpoint: Executor updated: app-20200427105438-0002/0 is now RUNNING
20/04/27 10:54:38 INFO BlockManager: Using org.apache.spark.storage.RandomBlockReplicationPolicy for block replication policy
20/04/27 10:54:38 INFO BlockManagerMaster: Registering BlockManager BlockManagerId(driver, 192.168.124.10, 45245, None)
20/04/27 10:54:38 INFO BlockManagerMasterEndpoint: Registering block manager 192.168.124.10:45245 with 93.3 MB RAM, BlockManagerId(driver, 192.168.124.10, 45245, None)
20/04/27 10:54:38 INFO BlockManagerMaster: Registered BlockManager BlockManagerId(driver, 192.168.124.10, 45245, None)
20/04/27 10:54:38 INFO BlockManager: Initialized BlockManager: BlockManagerId(driver, 192.168.124.10, 45245, None)
20/04/27 10:54:38 INFO StandaloneSchedulerBackend: SchedulerBackend is ready for scheduling beginning after reached minRegisteredResourcesRatio: 0.0
20/04/27 10:54:39 INFO SparkContext: Starting job: reduce at SparkPi.scala:23
20/04/27 10:54:39 INFO DAGScheduler: Got job 0 (reduce at SparkPi.scala:23) with 2 output partitions
20/04/27 10:54:39 INFO DAGScheduler: Final stage: ResultStage 0 (reduce at SparkPi.scala:23)
20/04/27 10:54:39 INFO DAGScheduler: Parents of final stage: List()
20/04/27 10:54:39 INFO DAGScheduler: Missing parents: List()
20/04/27 10:54:39 INFO DAGScheduler: Submitting ResultStage 0 (MapPartitionsRDD[1] at map at SparkPi.scala:19), which has no missing parents
20/04/27 10:54:39 INFO MemoryStore: Block broadcast_0 stored as values in memory (estimated size 2.0 KB, free 93.3 MB)
20/04/27 10:54:39 INFO MemoryStore: Block broadcast_0_piece0 stored as bytes in memory (estimated size 1378.0 B, free 93.3 MB)
20/04/27 10:54:39 INFO BlockManagerInfo: Added broadcast_0_piece0 in memory on 192.168.124.10:45245 (size: 1378.0 B, free: 93.3 MB)
20/04/27 10:54:39 INFO SparkContext: Created broadcast 0 from broadcast at DAGScheduler.scala:1163
20/04/27 10:54:39 INFO DAGScheduler: Submitting 2 missing tasks from ResultStage 0 (MapPartitionsRDD[1] at map at SparkPi.scala:19) (first 15 tasks are for partitions Vector(0, 1))
20/04/27 10:54:39 INFO TaskSchedulerImpl: Adding task set 0.0 with 2 tasks
20/04/27 10:54:40 INFO CoarseGrainedSchedulerBackend$DriverEndpoint: Registered executor NettyRpcEndpointRef(spark-client://Executor) (192.168.124.10:47554) with ID 0
20/04/27 10:54:40 INFO TaskSetManager: Starting task 0.0 in stage 0.0 (TID 0, 192.168.124.10, executor 0, partition 0, PROCESS_LOCAL, 7870 bytes)
20/04/27 10:54:40 INFO TaskSetManager: Starting task 1.0 in stage 0.0 (TID 1, 192.168.124.10, executor 0, partition 1, PROCESS_LOCAL, 7870 bytes)
20/04/27 10:54:40 INFO BlockManagerMasterEndpoint: Registering block manager 192.168.124.10:46311 with 366.3 MB RAM, BlockManagerId(0, 192.168.124.10, 46311, None)
20/04/27 10:54:41 INFO BlockManagerInfo: Added broadcast_0_piece0 in memory on 192.168.124.10:46311 (size: 1378.0 B, free: 366.3 MB)
20/04/27 10:54:41 INFO TaskSetManager: Finished task 0.0 in stage 0.0 (TID 0) in 654 ms on 192.168.124.10 (executor 0) (1/2)
20/04/27 10:54:41 INFO TaskSetManager: Finished task 1.0 in stage 0.0 (TID 1) in 633 ms on 192.168.124.10 (executor 0) (2/2)
20/04/27 10:54:41 INFO TaskSchedulerImpl: Removed TaskSet 0.0, whose tasks have all completed, from pool 
20/04/27 10:54:41 INFO DAGScheduler: ResultStage 0 (reduce at SparkPi.scala:23) finished in 1.758 s
20/04/27 10:54:41 INFO DAGScheduler: Job 0 finished: reduce at SparkPi.scala:23, took 2.048705 s
Pi is roughly 3.145955729778649
20/04/27 10:54:41 INFO SparkUI: Stopped Spark web UI at http://192.168.124.10:4040
20/04/27 10:54:41 INFO StandaloneSchedulerBackend: Shutting down all executors
20/04/27 10:54:41 INFO CoarseGrainedSchedulerBackend$DriverEndpoint: Asking each executor to shut down
20/04/27 10:54:41 INFO MapOutputTrackerMasterEndpoint: MapOutputTrackerMasterEndpoint stopped!
20/04/27 10:54:41 INFO MemoryStore: MemoryStore cleared
20/04/27 10:54:41 INFO BlockManager: BlockManager stopped
20/04/27 10:54:41 INFO BlockManagerMaster: BlockManagerMaster stopped
20/04/27 10:54:41 INFO OutputCommitCoordinator$OutputCommitCoordinatorEndpoint: OutputCommitCoordinator stopped!
20/04/27 10:54:41 INFO SparkContext: Successfully stopped SparkContext
20/04/27 10:54:41 INFO ShutdownHookManager: Shutdown hook called
20/04/27 10:54:41 INFO ShutdownHookManager: Deleting directory /usr/local/spark-2.4.5/spark-d385e30e-45d4-4b61-851c-3fe24b93d443
20/04/27 10:54:41 INFO ShutdownHookManager: Deleting directory /tmp/spark-d3985818-3ba2-42f1-be7a-89db17d7f7e8
