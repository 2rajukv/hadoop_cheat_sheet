# hadoop_cheat_sheet
hdfs

hdfs dfs -setfacl -m group:group1:r-x /apps/
hdfs dfs -setfacl -m default:group:group1:r-x /apps/

yarn

yarn jar /usr/hdp/2.3.2.0-2950/hadoop-mapreduce/hadoop-mapreduce-examples.jar pi -Dmapred.job.queue.name=hdp01_be_edw 8 10

yarn logs -applicationId application_1495335214022_90116 > /hadoop/application_1495335214022_90116.log

hive

CREATE DATABASE IF NOT EXISTS acltest;
use acltest;

CREATE TABLE IF NOT EXISTS employee ( eid int, name String,
salary String, destination String)
COMMENT 'Employee Details'
ROW FORMAT DELIMITED
FIELDS TERMINATED BY '\t'
LINES TERMINATED BY '\n'
STORED AS TEXTFILE;

DataFile
cat /tmp/employee.tsv
1001    employee1   10001   dest1
1002    employee2   10002   dest2
1003    employee3   10003   dest3
1004    employee4   10004   dest4

beeline

sqoop

beeline> !connect jdbc:hive2://< zookeeper Server1>:2181,< zookeeper Server2>:2181,< zookeeper Server3>:2181/;serviceDiscoveryMode=zooKeeper;zooKeeperNamespace=hiveserver2;
