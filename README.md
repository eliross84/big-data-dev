# Eli Ross

## Current
Currently I am a senior going into my last four classes as a Northwest Bearcat. I am pursuing a Bachelors of Science in Computer Science with a General emphasis. 

## Background
I am from Kansas City, Missouri and Nortwest Missouri State is the first and only university that I have attended. Some people do not know this, but I originally came to Northwest on a football scholarship. Later after my first year I decided that my future life plans \(getting married and graduating early\) did not align with the student-athlete lifestyle, and therefore made the hard decision to quit playing. I now have been actively working two jobs for the last two years, and in my free time I really enjoy going disc golfing on the full 18-hole course in the North-West corner of campus. 

## Plans
I have a passion for software engineering and I believe I have the creativity to excel in this area. This is always subject to change, for I currently work as a PC Technician at Nucor-LMP, also after taking Big Data I may have an interest in becoming a Data Engineer or Data Analyst!

## Links
[GitHub (eliross84)](https://github.com/eliross84)
<br />
[BitBucket](https://bitbucket.org/eliross84/)

## Getting Started with a Repository (for Windows)

Use the following commands to get started in making a new repo:
- In File Explorer go to the respective folder you would like your repo to be within.
- Right-click and \"Open PowerShell window as an administrator\"
- In PowerShell, one may create a new folder/directory by saying `mkdir *name of repository*`
- Use command `cd *name of repository*` to change the directory and/or go to the created directory
- Once within the directory a new file may be created by use `ni *name of file*`
    - In order to list the contents of a current folder use the command `ls`


Now you may open the folder/repository in Visual Studio Code or your respective IDE and start working!


## Notes
#### Wednesday, 13 May, 2020
What is Big Data?
The Five V's: <br />
- Velocity: the speed data accumulates
- Volume: scale of the increasing storage of data
- Variety: the diversity of data (structured and unstructured)
- Veracity: conformity to facts/accuracy
- Value: the benefits of evaluating the data

A common application of big data are Recommendation Engines, which are used for a lot of marketing purposes based upon the streamed data that is popular to a particular individual's device. Another may be Virtual assistants such as Alexa or Siri. 

Cloud computing has contributed hugely to the launch of the Big Data era. This lowers the price of storage and computing. 

Sources of Big Data: 
1. People-generated data
2. Machine-generated data
3. Business-generated data

- Structured
    - Data that is organized, labeled, and follows a strict model
    - ex: relational databases and spreadsheets
- Unstructured 
    - Makes up approximately 80% of data in the world
    - Given in a text form and does not have a predefined model
    - ex: square kilometer array, data explosion, social media
- Semi-structured
    - Combination of structured and unstructured
    - ex: XML or JSON

Data Science Process: 
1. Determine the problem
    - What is the project/business objective?
2. Collect Data
    - Which data is relevant, and are there privacy issues?
3. Explore Data
    - Plot the data, are there patterns?
4. Analyze Data
    - Build a model and validate it.
5. Storytelling: Visualization + Communication
    - Do the results make sense and are they explanatory?
6. Take Action
    - Make decisions 

Components and Ecosystems of Big Data:
- Techniques and Analyzing Data
    - A/B Testing
    - Machine Learning
    - Natural Language Processing
- Big Data Technologies (structured and unstructured)
    - Business Intelligence
    - Cloud Computing
    - Databases
- Visualization
    - Charts
    - Graphs
    - Other Displays

*Hadoop*: open-source software framework used to store and process huge amounts of data.
    - Node: any endpoint
    - Rack: a collection of nodes
    - Hadoop cluster: a collection of racks

*Data Warehouses*: deliver deep insight with advanced in-database analytics and provide online analytic processing. 

##### What is Hadoop?
- Can handle all three varieties of data
- Replicates its data across multiple computers, therefore has a failover system as a safety net. 
    - Does not support OTLP, OLAP, and DSS
- Not a replacement for an online relational database system
- Other open source projects that can be used with Hadoop
    - Eclipse (IDE)
    - Lucene (text-search engine library)
    - HBase (Hadoop database)
    - Hive (Data warehouse)
    - Pig (language that is used to analyze large datasets)
    - Spark (cluster keeping framework)
    - Zookeeper 
    - Apache Ambari
    - Avro
    - Unstructured Information Management Architecture
- Not good to process transactions
- Not good when work cannot be parallelized
- Not good for low latency data access
- Not good for processing lots of small files
- Not good for intensive calculations with with little data

##### Hadoop Architecture
*Terminology*: 
- Node: a computer and/or endpoint
- Rack: a collection of nodes that are stored close together and typically connected to the same network switch
- Cluster: a collection of racks

**Hadoop Main Components**:
1. Distributed File System (HDFS)
    - Runs on top of the existing file system
    - Designed to tolerate high component failure rate (reliable through replication)
    - Designed to handle very large files
        - Large streaming data access patterns
    - File blocks are not the same as operating system's file blocks (default to 64MB and are fixed in size)
        - These work really well with replication
2. MapReduce Engine
    - Framework for perofrming calculations on the data in the file system
    - Has a built-in resource manager and scheduler
    - NameNode: keeps all metadata and is recommended to have the maximum amount of RAM possible
    - DataNode: Manages blocks with data nd serves them to the clients
        - Reports to NameNode the list of blocks it stores
    - JobTracker: One per cluster, and schedules/monitors jobs on TaskTrackers
    - TaskTracker: executes operations/tasks and reads blocks from DataNodes. 

**Yet Another Resource Negotiator (YARN)**
- Provide generic scheduling and resource management
- More efficient schedling and workload management

*Hadoop High Availability*
- Two NameNode's (one active and one standby)
- Three (must be an odd number) of JournalNodes that keep track of which NameNode is being used and if the active fails then fall onto the standby
- Each NameNode has a Namespace and contains a pool of files that belong to it

**HDFS Command Line**
- All commands begin with `hdfs dfs <args>`
- Listing all contents `hdfs dfs -ls`
- Example of moving a file from regular file system to HDFS
```hdfs dfs -cp file:///sampleData/spark/myfile.txt hdfs://rvm.svl.ibm.com:8020/user/spark/test/myfile.txt```
*Commands*:
- copyFromLocal / put
    - Copy files from the local filesystem to HDFS
- copyToLocal / get
    - Copies files from HDFS to the local filesystem
- getMerge
    - Gets all files in the directories that match the source pattern
    - Merges and sorts them to only one file on local filesystem
- setRep
    - Sets the replication of a file
    - Can be executed recursively to change an entire tree

**Hadoop Administration**
- Adding nodes can be done from the Ambari Web Console
- Need IP address or hostname of node to add and must be reachable
- Run `hdfs dfsadmin -report` to check disk space 

**Configuration Files**
- core-site.xml: configures settings for I/O settings that are common to HDFS and MapTeduce
- hdfs-site.xml: configures settings for HDFS daemons, the NameNode, the secondary NameNode, and the DataNode's
- mapred-site.xml: configures settings for MapReduce daemons and JobTracker, and TaskTrackers

**MapReduce**
- Processes huge datasets for certain kinds of distributable problems using a large number of node
    - Map: master node partitions that input into smaller sub-problems (distributes these to the workor nodes)
    - Reduce: amster node then takes the answers to all the sub-problems (combines them in some way to get the output)
- *Distributed Mergesort Engine*: uses Map tasks to produce unstructured data into key/value pairs and lists