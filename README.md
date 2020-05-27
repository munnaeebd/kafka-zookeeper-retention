# kafka-zookeeper-retention
kafka-zookeeper-retention

kubectl edit configmap -n monasca standalone-kafka-zookeeper


    ZK_SNAP_RETAIN_COUNT=${ZK_SNAP_RETAIN_COUNT:-30}
    ZK_PURGE_INTERVAL=${ZK_PURGE_INTERVAL:-24}

30 file
24 hour

save and restart the zookeeper POD


2. Auto Way
Set below 2 parameters in $MAPR_HOME/zookeeper/zookeeper-<version>/conf/zoo.cfg and restart Zookeeper.

autopurge.snapRetainCount
   New in 3.4.0: When enabled, ZooKeeper auto purge feature retains the autopurge.
   snapRetainCount most recent snapshots and the corresponding transaction logs in the dataDir and 
   dataLogDir respectively and deletes the rest. Defaults to 3. Minimum value is 3.

autopurge.purgeInterval
    New in 3.4.0: The time interval in hours for which the purge task has to be triggered. 
    Set to a positive integer (1 and above) to enable the auto purging. Defaults to 0. 
    Note in Zookeeper 3.4.5 shipped with MapR this is set by default to '24' to run auto purge once a day. 
    
    
    
    https://mapr.com/support/s/article/How-to-purge-Zookeeper-Transaction-Log-and-Snapshots?language=en_US
    
    
    
