# some-interview-question

Linux 
1. Remove all file under certain path with certain date range: older than 30 day
find /var/log -name "*.log" -type f -mtime +30 -exec rm -f {}  

Rename all file with pattern 
for f in *.jpg; do mv "$f" "$(echo "$f" | sed s/IMG/VACATION/)"; done

Find distinct value from a file 
cut -d' ' -f2 list.txt | sort -u | wc -l
| sort | uniq
uniq -d gives only the duplicates, uniq -u gives only the unique ones (strips duplicates).

Remove all file recursively 
rm - R

Linux command to check resource 
free - m
Vmstat -s 
top	
htop
Check running process
ps -a /  ps -aux | less 		 ps aux | grep firefox


Spark
What is spark lineage graph?
logical execution that log all RDD operation, and link each RDD transformation to its parent RDD
In case of task failure, spark is able to reexecute the task using lineage graph in DAG. This is how spark achivev fault tolerance/resiliant 
What is DAG?
Change delimiter in a RDD
data.write.option(delimiter = ‘’)
Use UDF, with regular expression 
val regex = "[0-9]".r
val regex = "[0-9]".r
Use string.replaceAllIn(
val address = "123 Main Street".replaceAll("[0-9]", "x")
https://www.oreilly.com/library/view/scala-cookbook/9781449340292/ch01s08.html


DAG is more high level, DAG show different stage of a spark job, tranformation, join etc



Python:  string.join() 
	List[124] 	list.sum       list.max 

SQL, find top 3 paying employee from each department 
	Select dept_id, employee_id, rank() over (partition by dept_id, order by salary desc) rnk from table where rnk < 3

	Select alternative row
	Select name, row_number() over (partition by id) row from xx where row_num %2 = 0


Hive, complex data type : map   is similar to a dictionary in Python.
	What is ‘Explode’ function 


Spark -client mode and cluster mode 
	Client mode run on local and cluster mode utilize cluster
