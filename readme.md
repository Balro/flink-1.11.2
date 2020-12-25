### 分支说明  
    master & flink-1.11.2_bak # flink-1.11.2原始代码
    flink-1.11.2-cdh6.2.1 & dev # 个性化修改后的代码。

### 代码修改说明  
* flink-core:  
    添加从jvm参数中提取配置的功能。
* flink-connector-kafka:  
    添加消费kafka时限速的功能，用于初始化消费积压数据。
* flink-connector-hive:  
    集成hive-2.1.1-cdh6.2.1。
* flink-connector-hbase2:  
    新增项目，集成hbase2.1.0-cdh6.2.1。  
    修复写入hbase时乱序的问题。  
    修复delete记录时遗留脏数据的问题。  
* flink-dist  
    默认添加-d参数，启用后台模式。  
* flink-json
    # https://issues.apache.org/jira/browse/FLINK-20763
    修复canal在读取update记录，当旧记录中存在null值，-U记录的null值以外被新值覆盖，导致retract计数错误的bug。  
        org.apache.flink.formats.json.canal.CanalJsonDeserializationSchema  
        org.apache.flink.formats.json.JsonRowDataDeserializationSchema  
