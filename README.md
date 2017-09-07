Execution steps:

- Start hadoop cluster
- Start apache spark on master and slaves as per previous phases
- Load the yellow cab data file in HDFS
- Note down the location of the file in HDFS
- You can either build the JAR from the source code or use the jar provided in submission for execution by copying it to “../hadoop/jars/“ directory
- Now run mvn clean install in the root directory of the project to build the jar (to be done only if you are building a new JAR)
- You can find the jar in target folder in root folder of the project (to be done only if you are building a new JAR)
- Copy the newly built JAR to “../hadoop/jars/“ directory (to be done only if you are building a new JAR)
- Execute the following command :
	
	spark-submit --class AllSpark.HotspotDetector <jar location> <hdfs path to the input file> <local(NOT HDFS) directory where the output csv can be written>
	
	Sample command:
	/usr/local/spark/bin/spark-submit --class AllSpark.HotspotDetector /usr/local/spark/jars/AllSpark_phase3.jar hdfs://master:54310/dataset/yellow_tripdata_2015-01.csv /usr/local

- You can now find the file "output.csv" at the provided output location

NOTE: Output location must have access right in order to create a csv and write data to it.