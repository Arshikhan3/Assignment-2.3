# Assignment-2.3
Explain in detail:
● All components of Hadoop 1.x

Ans - Hadoop 1.x Major Components are: 
HDFS and MapReduce. They are also know as “Two Pillars” of Hadoop 1.x.

HDFS:
HDFS is a Hadoop Distributed FileSystem, where our BigData is stored using Commodity Hardware. It is designed to work with Large DataSets with default block size is 64MB (We can change it as per our Project requirements).

HDFS component is again divided into two sub-components:

Name Node
Name Node is placed in Master Node. It used to store Meta Data about Data Nodes like “How many blocks are stored in Data Nodes, Which Data Nodes have data, Slave Node Details, Data Nodes locations, timestamps etc” .

Secondary NameNode
• Performs house-keeping activities for NameNodes, like the periodic merging of namespace and edits.
• This is not a back up for a NameNode.

DataNode
Data Nodes are places in Slave Nodes. It is used to store our Application Actual Data. It stores data in Data Slots of size 64MB by default.
• Stores actual data blocks of files in HDFS on its own local disk.
• Sends signals to the NameNode periodically (called as Heartbeat) to verify whether it is active.
• Sends block reporting to the NameNode on the cluster startup as well as periodically at every 10th Heartbeat.
• The DataNodes are the workhorses of a system.
• They perform all the block operations including periodic checksum. They receive instructions from the name node of
where to put the blocks and how to put them. 


MapReduce:
MapReduce is a Distributed Data Processing or Batch Processing Programming Model. Like HDFS, MapReduce component also uses Commodity Hardware to process “High Volume of Variety of Data at High Velocity Rate” in a reliable and fault-tolerant manner.

MapReduce component is again divided into two sub-components:

Job Tracker
Job Tracker is used to assign MapReduce Tasks to Task Trackers in the Cluster of Nodes. Sometimes, it reassigns same tasks to other Task Trackers as previous Task Trackers are failed or shutdown scenarios.

Job Tracker maintains all the Task Trackers status like Up/running, Failed, Recovered etc.

Task Tracker
Task Tracker executes the Tasks which are assigned by Job Tracker and sends the status of those tasks to Job Tracker.

