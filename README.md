# Introduction to Cassandra

In this project, we will develop  applications  using  Apache Cassandra on VMs (Virtual machine). To analyze a real anonymous logs to answer several questions based on the log.

## Setting up Cassandra:

The  first  task  is  to  configure  a  Cassandra  distribution  in  your  cluster  of  VMs.  The  entire Cassandra setup should be configured on top of a two-node or three-node cluster. As Cassandra has a “master-less” architecture, all of the Cassandra nodes can be configured in the same way. Here are some documents for Cassandra (http://cassandra.apache.org/doc/latest/). You can check here to install Cassandra (http://cassandra.apache.org/download/). On Ubuntu, you can install Cassandra easily from the Debian packages. Then, you need to configure Cassandra nodes to make them work together (http://cassandra.apache.org/doc/latest/getting_started/configuring.html). Finally, you can start your Cassandra nodes on all the VMs (make sure the previous Hadoop and Spark services are all shut down to empty the memory and use –R parameter if you run Cassandra with root user). 

## Import Data into Cassandra:

As part of the project, you will be working with the log data set which has been provided in access_log.zip. You need to use CQL (Cassandra Query Language: http://cassandra.apache.org/doc/latest/cql/index.html) or JAVA driver of Cassandra (https://github.com/datastax/java-driver ) to import the access logs into Cassandra. You need to create one keyspace and one table at least in Cassandra to store all the logs. You  can  check (https://docs.datastax.com/en/cql/3.3/cql/cql_reference/cqlshCopy.html)    for  some help of the COPY commands or use the bulk loader to import the data: (https://docs.datastax.com/en/archived/cassandra/2.0/cassandra/tools/toolsBulkloader_t.html). In addition, for creating the table, you can check here (http://cassandra.apache.org/doc/latest/cql/ddl.html#create-table).

## Operate Data in Cassandra:

As  part  of  the  project  you  will  be  working  with  the  log  data  set  which  has  been  stored  in Cassandra. You need to use CQL (Cassandra Query Language: (http://cassandra.apache.org/doc/latest/cql/index.html) or JAVA driver of Cassandra (https://github.com/datastax/java-driver ) to operate the access logs in Cassandra. You need to get the result for the questions below:

Problems:
1. How many hits were made to the website item “/assets/img/release-schedule-logo.png”?
2. How many hits were made from the IP: 10.207.188.188
3. Which path in the website has been hit most? How many hits were made to the path?
4. Which IP accesses the website most? How many accesses were made by it?

The first two questions can be answered by SELECT in CQL. You can check (http://cassandra.apache.org/doc/latest/cql/dml.html#select) if you have any difficulties. 

The last two questions need one more step to get: you can either use the java-driver to insert the counts of the items into a new table and use another CQL to get the answer or just use one  user-defined  function  to  get  the  answer  of  the  group-max  query,  you  can  refer: (http://christopher-batey.blogspot.com/2015/05/cassandra-aggregates-min-max-avg-group.html).

