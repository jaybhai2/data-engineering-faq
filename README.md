## some-interview-question

# DataEngineering
### 1) Data modelling: define entity, relationship and rules
### 2) design schema of datawarehouse:  Snowflake and Star schema
### 3) structured data, unstructured data example
### 4) Hadoop Component: HDFS, MapRed, Yard
### 5) explain map, shuffle, and reduce
### 6) Spark Component: Master, Worker, resource manager
### 7) Spark cluster mode and client mode
### 8) Spark Narrow and wide transformation
### 9) what database you worked with?
### 10) what are some of the hive complex data type, Map,Struct,Array,Union,   what explode function do?
### 11) UDF?
### 12) external table, and internal table/ managed table?
### 13) what is schema on read?
### 14) what are the biggest challent in you previou project, and how you solve?
### 15) what are you hoping to Develop in your next project?
### 16) arvo and parquet,
### 17) what are some of the complex sql/transformation you written?


# Linux 
### 1) Remove all file under certain path with certain date range: older than 30 day
find /var/log -name "*.log" -type f -mtime +30 -exec rm -f {}  

### 2) Rename all file with pattern 
for f in *.jpg; 
	do mv "$f" "$(echo "$f" | sed s/IMG/VACATION/)"; 
	done

### 3) Find distinct value from a file 
cut -d' ' -f2 list.txt | sort -u | wc -l
| sort | uniq
uniq -d gives only the duplicates, uniq -u gives only the unique ones (strips duplicates).

### 4) Remove all file recursively 
rm - R

### 5) Linux command to check resource 
```
free - m
Vmstat -s 
top	
htop
Check running process
ps -a /  ps -aux | less 		 ps aux | grep firefox
```
## Spark
### 1) What is spark lineage graph?
	logical execution that log all RDD operation, and link each RDD transformation to its parent RDD
	In case of task failure, spark is able to reexecute the task using lineage graph in DAG. This is how spark achivev fault tolerance/resiliant 
	What is DAG?
	DAG is more high level, DAG show different stage of a spark job, tranformation, join etc

Python:  string.join() 
	List[124] 	list.sum       list.max 

### 2) Spark -client mode and cluster mode 
	Client mode run on local and cluster mode utilize cluster

### 3) wide transformation narrow transformation
	wide - shuffle occur/ data move across the note -> groupby , reduceby, collect
	narrow - map 
### 4) RDD vs DataFrame vs Datasets

### 5) Partitioning and Bucketing

### 6) spark run out of memory:  driver out of memory on collect action, or executor our of memory on big partition

### 7) How to turn a spark executor

### 8) broadcast join?

### 9) what are transformation, what are actions?


## SQL/Hive 
### 1) find top 3 paying employee from each department 
	Select dept_id, employee_id, rank() over (partition by dept_id, order by salary desc) rnk from table where rnk < 3
	Select alternative row
	Select name, row_number() over (partition by id) row from xx where row_num %2 = 0
### Rank and dense rank
### 2) Hive, complex data type : map   is similar to a dictionary in Python.
	What is ‘Explode’ function 

### 3) SQL vs no SQL 
	when you data is sturctured and you need ACID compliance which apply to most transaction opertion ->SQL
	if you data is unstructured -> noSQL
	noSql, you dont need to predefined schema, data can be column stored, document stored, key-value stored
		can scale horizontally 
	use case noSQL:  article content, social media post, sensor data, other unsturctured data that wont fit neatly in sql db
	
### 4) ACID
	atomicity. one transaction either happen or not happen.
	
### 5) find duplicate at row level: select every column group by every column having count(*) >1

### 6) compare two tables: select every column from (tables unioned) group by every column having count(*) >1


## Kafka
### 1) why do you need a publish and subscriber system?
	to decouple, to isolate the write and process capability of source and consumption. 
	producer and consumer can work at different speed
	
	
