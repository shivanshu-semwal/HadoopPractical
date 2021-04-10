# Hadoop Practical

- [Mapper Class](./MyMapper.java)
- [Reducer Class](./MyReducer.java)
- [Driver](./Driver.java)
- [Input File](./input.txt)
- [Output File](./output/part-r-00000)

### Execution

```sh
# storing class path for hadoop imports file
H_PATH=$(hadoop classpath)

# compiling
javac -cp $H_PATH *.java

# creating jar file
jar -cvf count.jar *.class 

# uploading the local input file to HDFS
hadoop fs -put input.txt

# executing mapReduce program
hadoop jar count.jar Driver input.txt output

# listing files in the output folder
hadoop fs -ls output

# previewing the output
hadoop fs -cat output/part-r-00000
```