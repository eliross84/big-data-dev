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

**Pig**
Data flow language

- Developed at Yahoo!
- Can operate on complex, nested data structures
- Relationally complete
- Running Pig
    - Script `pig scriptfile.pig`
    - Grunt `pig`
    - Call in to Pig from Java

**Hive**
Declarative language (SQL dialect)

- Developed at Facebook
- Relationally complete
- Running Hive
    - Interactive `hive`
    - Script `hive -f myscript`
    - Inline `hive -e 'SELECT * FROM mytable'`

**Flume**
Service for moving large amounts of data around a cluster soon after the data is produced.

- Building chains of logical nodes that have a source and a sink

**Oozie**
Manages Hadoop jobs

**Sqoop**
Transfers data between Hadoop and relational databases and uses MapReduce to import and export the data.


#### Monday, 18 May, 2020

##### Maven
- Yiddish for "Accumulator of Knowledge"
    - Manages builds, dependencies/versions,and documentation
    - Universal build system (Ant, C, xml)
    - Easy build process
    - Make new features easy
- Checking for the version `mvn --version`
- For creating a project be sure to make a storage directory and then on that directory run a command similar to:
``mvn archetype:generate -DgroupId=com.mycompany.app -DartifactId=my-app -DarchetypeArtifactId=maven-archetype-quickstart -DarchetypeVersion=1.4 -DinteractiveMode=false``

- *POM.xml*: the core of a maven project's coniguration. Contains the majority of the information required to build a project in just the way you want. 
    - These can be inherited if the child uses the <parent> tag in their pom.xml file.
- To build the project you may run `mvn package`
- Key directories of maven will be 
    - `src/main/java` : contains code for namespace
    - `src/main/resources`: contains non-code 
    - `POM.xml`: uses XML to hold information about the project, its dependencies, etc. 


##### Zookeeper
- A centralized service used to maintain naming and configuration data to provide flexible and robust synchronization within distributed systems. 
- Performs instant failover migration, due to redundancy. 

**Types of Zookeeper Nodes within ensembles (clusters)**
- *Leader*: All write's go through here and are distributed to the follower's.
- *Follower*: there to read/write data to the requests given, and are there just in case the leader node fails and one has to step up as the leader node. 
- *Observer*: addresses scale problem, used to improve the scalibility of the followers and their storage.

- Topics: a particular stream of data
    - Similar to a table in a database
    - You can have as many topics as you want
    - A topic is identified by its name
- Partitions: within a Topic
    - Indexed starting at zero
    - Each message within a partition gets an id called an offset (also indexed starting at zero)
    - All partitions are independent

- Data in Kafka is kept for a limited time
- Data is immutable once written to a partition in an offset


#### Wednesday 20 May, 2020

##### Python Basics
- Hashtags are used for commenting
- print() is used to print to the console.
- Types
    - Integers are int
    - Decimal numbers are float
    - Strings are str
    - Boolean bool (must be a True or a False [capitalized])

- Typecasting example
    - `float(2):2.0` integer to a float

- String operations:
    - Ways to manipulate `Name = "Michael Jackson"`
        - `Name[0:4]` is Mich
        - `Name[::2]` is McalJcsn (Every even indice)
        - `Name[0:5:2]` is Mca (Every even indice up to 5)
        - `len(Name)` is 15
        - `~.upper()` is MICHAEL JACKSON
        - `~.lower()` is michael jackson
        - `Name.replace('Jackson','Jordon')` is Michael Jordan
        - `Name.find('el')` is 5

- Tuples
    - Example tuple: `Ratings = (10,9,6,5,10,8,9,6,2)`
    - All elements can be different types and they are immutable
    - Tuples may be concatenated together
    - Slicing `tuple = ("disco", 10, 1.2, "hard rock", 10)`
        - `tuple[0:3]` is ("disco", 10, 1.2)

- Lists
    - Example list: `L = ["Michael", 10.1, 1982]`
    - Lists are Mutable
    - Ways to manipulate `L = ["Michael", 10.1, 1982]`
        - `L.extend(["pop", 10])` is ["Michael", 10.1, 1982,"pop", 10]
        - `L.append(["pop", 10])` is ["Michael", 10.1, 1982,["pop", 10]]
        - `del(L[0])` is [10.1, 1982]
        - `.split()` can split a string via the spaces.
            - Also specific characters to split at can be passed as a parameter
        - `M = L[:]` makes a copy of L and makes a new list, not using the reference

- Sets
    - A type of collection, different Python types can be used in one set
    - Unordered (no indexing)
    - Example set = `Set1 = {"pop", "rock", "soul", "hard rock", "rock", "R&B", "rock", "disco"}` will turn into `Set1 = {"rock" "R&B", "disco", "hard rock", "pop", "soul"}`
        - *There cannot be duplicate values*
    - Making a list into a set
        - `newSet = set(list)`
    - Operations
        - `.add(*some value*)` adds a value to the set, if duplicate it will be dropped
        - `.remove(*some value*)` removes a value from a set
        - `*some value* in set` returns true or false if inside of set
        - `set3 = *set 1* & *set 2*` takes the like items in both sets 1 and 2 and assigns them to set 3
        - `set1.union(set2)` takes sets 1 and 2 and unions them into a single set
        - `set1.issubset(set2)` checks to see if set1 is a subset of set2

- Dictionaries
    - Key value pairs
    - dictionary = {"key1": 1, "key2": "hello", "key3": [1,2,3]}
    - Key is used to lookup the value
        - Lookup example: `dictionary["key2"] = "hello"`
    - `... in ...` is used for basic lookup of keys
    - `del(dictionary["key3"])` can be used to delete a key value pair
    - `dictionary.keys()` returns a list of the keys
        - Likewise for values with `.values()`

- Comparison Operators
    - `== or !=` produces True or False
    - `>, <, >=, or <=` produces True or False

- Branching
    ``if(age > 18):``
    ``  print("You can enter")``
    ``elif(age == 18):``
    ``  print("go to a different place")``
    ``else:``
    ``  print("You cannot enter")``

- Logic Operators
    - `not(*some value*)` returns the opposite of its contents
    - `or(value1, value2)` returns false only if both are false, the rest are true
    - `and(value1, value2)` returns true only if both are true, the rest are false