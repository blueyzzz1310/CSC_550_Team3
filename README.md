 ## CSC 550 1 Big Data - Mini - Project

### Hadoop Installation command:
$ /usr/local/Cellar/hadoop/2.8.1/sbin/start-dfs.sh;<br />
/usr/local/Cellar/hadoop/2.8.1/sbin/start-yarn.sh<br />
### Verify if hadoop daemons are active.
$ jps<br />
16499 Jps<br />
73829 NodeManager<br />
24344 SecondaryNameNode<br />
24045 DataNode<br />
23822 NameNode<br />
73647 ResourceManager
### Create jar file.
Jar file can also be created from terminal by using the command:<br />
$ jar -cvf hadoop-mapreduce-graysort.jar *.*
### Browse HDFS directory
http://localhost:50070/explorer.html#/<br />
### Generate 10 GB data using TeraGen
hadoop jar hadoop-mapreduce-graysort.jar teragen 100000000 /DataGen
### Sort data using TeraSort
hadoop jar hadoop-mapreduce-graysort.jar terasort  /DataGen /DataSort
### Validate the output using TeraValidate
hadoop jar hadoop-mapreduce-graysort.jar teravalidate -D mapped.reduce.tasks=8 /DataSort /DataValidate
### The output can be viewed by browsing HDFS directory at:
http://localhost:50070/explorer.html#/
