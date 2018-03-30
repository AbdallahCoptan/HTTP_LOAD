# Installing Yahoo! Cloud Serving Benchmark(YCSB)  #

**Yahoo! Cloud Serving Benchmark:** With the many new serving databases available including Sherpa, BigTable, Azure and many more, it can be difficult to decide which system is right for your application, partially because the features differ between systems, and partially because there is not an easy way to compare the performance of one system versus another.
The flow of operations is as follows : 

The goal of the Yahoo Cloud Serving Benchmark (YCSB) project is to develop a framework and common set of workloads for evaluating the performance of different "key-value" and "cloud" serving stores. The project comprises two areas:

    The YCSB Client, an extensible workload generator
    The Core workloads, a set of workload scenarios to be executed by the generator

A common use of the tool is to benchmark multiple systems and compare them. For example, you can install multiple systems on the same hardware configuration, and run the same workloads against each system. Then you can plot the performance of each system (for example, as latency versus throughput curves) to see when one system does better than another.

There are many cloud data base servers and nosql system like: 

		Sherpa/PNUTS 
		BigTable 
			HBase, Hypertable, HTable 
		Megastore 
		Azure 
		Cassandra 
		Amazon Web Services 
			S3, SimpleDB, EBS and DynamoDB 
		CouchDB 
		Voldemort 
		Dynomite 
		Etc: Tokyo, Redis, MongoDB and Memcached

We will use the YCSB to test the behaviour of the **Redis, Memcahced, MongoDB and DynamoDB** servers under a different workload and stress !! There are many workloads in the tool such as: workloada, workloadb, workloadc, workloadd, workloade and workloadf, all of them are located in the [source code](https://github.com/AbdallahCoptan/YCSB) in folder called workloads

 
For more detailes please have a look at [YCSB](https://research.yahoo.com/news/yahoo-cloud-serving-benchmark/).

There is an original [Yahoo! Cloud Serving Benchmark(YCSB)](https://github.com/AbdallahCoptan/YCSB) on the github.

For additional background please read : visit [WIKI page on GitHub](https://github.com/brianfrankcooper/YCSB/wiki), and the [YCSB V4.pdf](https://s.yimg.com/ge/labs/v1/files/ycsb-v4.pdf)


## Pre-Requests before Installation of Yahoo! Cloud Serving Benchmarks ##

Befor installing Yahoo **Cloud Serving Benchmark** you need to install the following:

1. The Server you will test e.g. Redis, Memcached, MongoDB or DynamoDB
2. Java jdk
3. Apache Maven

### 1. Installing Servers to Test ###
You need to install the servers you want to test by YCSB and also configure them if you will test remotely:

1) **Redis:** to install Redis please follow the instruction for installing  and configuring Redis under [All about Redis Server](https://gitlab.uni.lu/aibrahim/cloud-perf/blob/master/docs/tools/Redis-Server.md).

2) **Memchached:** to install Memchached please follow the instruction for installing  and configuring Memcached under [All about Memchached Server](https://gitlab.uni.lu/aibrahim/cloud-perf/blob/master/docs/tools/Memcached.md)

3) **MongoDB:** to install MongoBD please follow the instruction for installing  and configuring MongoBD under [All about MongoBD Server](https://gitlab.uni.lu/aibrahim/cloud-perf/blob/master/docs/tools/MongoBD.md)

4) **DynamoDB:** to install DynamoDB please get account on AWS and follwo their [instructions](http://docs.aws.amazon.com/amazondynamodb/latest/developerguide/DynamoDBLocal.html).  

### 2. Installing Java jdk ###

In the begining you need to update, as following:

		$ sudo apt-get update

To install **Java jdk** you need to search for the last one and then install it by the following commands: 

		$ apt-cache search jdk
		$ sudo apt-get install openjdk-7-jdk

### 3. Installing Apache Maven ###

To install **Maven** you should do the following:

		$ apt-cache search maven
		$ sudo apt-get update
		$ sudo apt-get install maven

To check if **Maven** installed correctly by checking the maven version:

		$ mvn -version


Note: For more infromation about Maven see [Downloading Maven](https://maven.apache.org/download.cgi) and [Installing Apache Maven](https://maven.apache.org/install.html) !!

## Now, Installing the Yahoo Cloud Serving Benchmark  ##

We need to clone the **Yahoo Cloud Serving Benchmark** git repository by:  

		$ git clone https://github.com/AbdallahCoptan/YCSB.git 
		$ cd YCSB

### Check the servers you can test and YCSB if Working ###

By issuing the follwwing command in the folder **/YCSB/** :

		$ ./bin/ycsb load
		usage: ./bin/ycsb command database [options]

		Commands:
		    load           Execute the load phase
		    run            Execute the transaction phase
		    shell          Interactive mode

		Databases:
		    accumulo       https://github.com/brianfrankcooper/YCSB/tree/master/accumulo
		    aerospike      https://github.com/brianfrankcooper/YCSB/tree/master/aerospike
		    arangodb       https://github.com/brianfrankcooper/YCSB/tree/master/arangodb
		    asynchbase     https://github.com/brianfrankcooper/YCSB/tree/master/asynchbase
		    azuredocumentdb https://github.com/brianfrankcooper/YCSB/tree/master/azuredocumentdb
		    basic          https://github.com/brianfrankcooper/YCSB/tree/master/basic
		    cassandra-cql  https://github.com/brianfrankcooper/YCSB/tree/master/cassandra
		    cassandra2-cql https://github.com/brianfrankcooper/YCSB/tree/master/cassandra2
		    couchbase      https://github.com/brianfrankcooper/YCSB/tree/master/couchbase
		    couchbase2     https://github.com/brianfrankcooper/YCSB/tree/master/couchbase2
		    dynamodb       https://github.com/brianfrankcooper/YCSB/tree/master/dynamodb
		    elasticsearch  https://github.com/brianfrankcooper/YCSB/tree/master/elasticsearch
		    geode          https://github.com/brianfrankcooper/YCSB/tree/master/geode
		    googlebigtable https://github.com/brianfrankcooper/YCSB/tree/master/googlebigtable
		    googledatastore https://github.com/brianfrankcooper/YCSB/tree/master/googledatastore
		    hbase094       https://github.com/brianfrankcooper/YCSB/tree/master/hbase094
		    hbase098       https://github.com/brianfrankcooper/YCSB/tree/master/hbase098
		    hbase10        https://github.com/brianfrankcooper/YCSB/tree/master/hbase10
		    hypertable     https://github.com/brianfrankcooper/YCSB/tree/master/hypertable
		    infinispan     https://github.com/brianfrankcooper/YCSB/tree/master/infinispan
		    infinispan-cs  https://github.com/brianfrankcooper/YCSB/tree/master/infinispan
		    jdbc           https://github.com/brianfrankcooper/YCSB/tree/master/jdbc
		    kudu           https://github.com/brianfrankcooper/YCSB/tree/master/kudu
		    mapkeeper      https://github.com/brianfrankcooper/YCSB/tree/master/mapkeeper
		    memcached      https://github.com/brianfrankcooper/YCSB/tree/master/memcached
		    mongodb        https://github.com/brianfrankcooper/YCSB/tree/master/mongodb
		    mongodb-async  https://github.com/brianfrankcooper/YCSB/tree/master/mongodb
		    nosqldb        https://github.com/brianfrankcooper/YCSB/tree/master/nosqldb
		    orientdb       https://github.com/brianfrankcooper/YCSB/tree/master/orientdb
		    rados          https://github.com/brianfrankcooper/YCSB/tree/master/rados
		    redis          https://github.com/brianfrankcooper/YCSB/tree/master/redis
		    rest           https://github.com/brianfrankcooper/YCSB/tree/master/rest
		    riak           https://github.com/brianfrankcooper/YCSB/tree/master/riak
		    s3             https://github.com/brianfrankcooper/YCSB/tree/master/s3
		    solr           https://github.com/brianfrankcooper/YCSB/tree/master/solr
		    solr6          https://github.com/brianfrankcooper/YCSB/tree/master/solr6
		    tarantool      https://github.com/brianfrankcooper/YCSB/tree/master/tarantool
		    voldemort      https://github.com/brianfrankcooper/YCSB/tree/master/voldemort

		Options:
		    -P file        Specify workload file
		    -cp path       Additional Java classpath entries
		    -jvm-args args Additional arguments to the JVM
		    -p key=value   Override workload property
		    -s             Print status to stderr
		    -target n      Target ops/sec (default: unthrottled)
		    -threads n     Number of client threads (default: 1)

		Workload Files:
		    There are various predefined workloads under workloads/ directory.
		    See https://github.com/brianfrankcooper/YCSB/wiki/Core-Properties
		    for the list of workload properties.

#### The small p option (-p key=value) ####

Here are the options could come after this arguemet **-p**:

		$ ./bin/ycsb load [server name] -s -P workloads/workloada -p
		Usage: java com.yahoo.ycsb.Client [options]
		Options:
		  -threads n: execute using n threads (default: 1) - can also be specified as the 
			"threadcount" property using -p
		  -target n: attempt to do n operations per second (default: unlimited) - can also
		       be specified as the "target" property using -p
		  -load:  run the loading phase of the workload
		  -t:  run the transactions phase of the workload (default)
		  -db dbname: specify the name of the DB to use (default: com.yahoo.ycsb.BasicDB) - 
			can also be specified as the "db" property using -p
		  -P propertyfile: load properties from the given file. Multiple files can
			   be specified, and will be processed in the order specified
		  -p name=value:  specify a property to be passed to the DB and workloads;
			  multiple properties can be specified, and override any
			  values in the propertyfile
		  -s:  show status during run (default: no status)
		  -l label:  use label for status (e.g. to label one experiment out of a whole batch)

		Required properties:
		  workload: the name of the workload class to use (e.g. com.yahoo.ycsb.workloads.CoreWorkload)

		To run the transaction phase from multiple servers, start a separate client on each.
		To run the load phase from multiple servers, start a separate client on each; additionally,
		use the "insertcount" and "insertstart" properties to divide up the records to be inserted
		Argument '-p' expected to be in key=value format (e.g., -p operationcount=99999)


### Getting Started with YCSB ###

After Cloning the YCSB repository from git, you will find a folder for each server you can test. You should change the directory to this folder and start your server test. I willl show this for each of our servers. 


#### 1. Redis Server Testing By YCSB ####

After Configuraing [redis](https://github.com/AbdallahCoptan/YCSB/tree/master/redis), Start it and do the follwoing:

		$ cd YCSB
		$ mvn -pl com.yahoo.ycsb:redis-binding -am clean package

**To load the data for testing:**

		$ ./bin/ycsb load redis -s -P workloads/workloada -p "redis.host=127.0.0.1" -p "redis.port=6379" -p "threadcount=10"

Note: the redis server could be remote, if so, change the **"redis.host= IP.address"** !! FOR more oprions for **-p** check the [pageRedis_Parameters](https://github.com/AbdallahCoptan/YCSB/tree/master/redis#4-provide-redis-connection-parameters).

**Run the workload test:**

		$ ./bin/ycsb run redis -s -P workloads/workloada -p "redis.host=127.0.0.1" -p "redis.port=6379" -p "threadcount=10"

Here it is the output of the test:

		[OVERALL], RunTime(ms), 332.0
		[OVERALL], Throughput(ops/sec), 3012.0481927710844
		[TOTAL_GCS_MarkSweepCompact], Count, 0.0
		[TOTAL_GC_TIME_MarkSweepCompact], Time(ms), 0.0
		[TOTAL_GC_TIME_%_MarkSweepCompact], Time(%), 0.0
		[TOTAL_GCS_Copy], Count, 3.0
		[TOTAL_GC_TIME_Copy], Time(ms), 8.0
		[TOTAL_GC_TIME_%_Copy], Time(%), 2.4096385542168677
		[TOTAL_GCs], Count, 3.0
		[TOTAL_GC_TIME], Time(ms), 8.0
		[TOTAL_GC_TIME_%], Time(%), 2.4096385542168677
		[CLEANUP], Operations, 10.0
		[CLEANUP], AverageLatency(us), 767.4
		[CLEANUP], MinLatency(us), 29.0
		[CLEANUP], MaxLatency(us), 3481.0
		[CLEANUP], 95thPercentileLatency(us), 3481.0
		[CLEANUP], 99thPercentileLatency(us), 3481.0
		[READ], Operations, 492.0
		[READ], AverageLatency(us), 1936.2215447154472
		[READ], MinLatency(us), 0.0
		[READ], MaxLatency(us), 56447.0
		[READ], 95thPercentileLatency(us), 5675.0
		[READ], 99thPercentileLatency(us), 12831.0
		[READ], Return=OK, 492
		[UPDATE], Operations, 508.0
		[UPDATE], AverageLatency(us), 2454.5452755905512
		[UPDATE], MinLatency(us), 0.0
		[UPDATE], MaxLatency(us), 19615.0
		[UPDATE], 95thPercentileLatency(us), 8391.0
		[UPDATE], 99thPercentileLatency(us), 17999.0
		[UPDATE], Return=OK, 508


#### 2. Memcached Server Testing By YCSB ####

After Configuraing [memcached](https://github.com/AbdallahCoptan/YCSB/tree/master/memcached), Start it and do the follwoing:

		$ cd YCSB
		$ mvn -pl com.yahoo.ycsb:memcached-binding -am clean package

**To load the data for testing:**

		$ ./bin/ycsb load memchached -s -P workloads/workloada -p "memcached.hosts=127.0.0.1" -p "memcached.port=11211" -p "threadcount=10"

Note: the redis server could be remote, if so, change the **"memcaached.hosts= IP.address"** !! FOR more oprions for **-p** check the [pageMemc_Parameters](https://github.com/AbdallahCoptan/YCSB/tree/master/memcached#5-memcached-connection-parameters).

**Run the workload test:**

		$ ./bin/ycsb run memchached -s -P workloads/workloada -p "memcached.hosts=127.0.0.1" -p "memcached.port=11211" -p "threadcount=10"


#### 3. MongoDB Server Testing By YCSB ####

After Configuraing [mongodb](https://github.com/AbdallahCoptan/YCSB/tree/master/mongodb), Start it and do the follwoing:
https://github.com/AbdallahCoptan/YCSB/tree/master/redis#4-provide-redis-connection-parameters
		$ cd YCSB
		$ mvn -pl com.yahoo.ycsb:mongodb-binding -am clean package  **!!!Optional!!!**

**To load the data for testing:**

--- As asynchronous Driver ---

		$ ./bin/ycsb load mongodb-async -s -P workloads/workloada -p "mongodb.url=mongodb://localhost:27017/ycsb?w=0"

--- As synchronous Driver ---

		$ ./bin/ycsb load mongodb -s -P workloads/workloada -p "mongodb.url=mongodb://localhost:27017/ycsb?w=0"

Note: the redis server could be remote, if so, change the **"mongodb.url=mongodb://ip.address:27017/ycsb?w=0"** !! FOR more oprions for **-p** check the [pageMongo_Parameters](https://github.com/AbdallahCoptan/YCSB/tree/master/mongodb#mongodb-configuration-parameters).

**Run the workload test:**

--- As asynchronous Driver ---

		$ ./bin/ycsb run mongodb-async -s -P workloads/workloada -p "mongodb.url=mongodb://localhost:27017/ycsb?w=0"

--- As synchronous Driver ---

		$ ./bin/ycsb run mongodb -s -P workloads/workloada -p "mongodb.url=mongodb://localhost:27017/ycsb?w=0"

