# Mid Submission

## Data Ingestion

### Create Database

```HQL
hive> CREATE DATABASE IF NOT EXISTS telecom;
OK
Time taken: 0.925 seconds
hive> SHOW DATABASES;
OK
default
telecom
Time taken: 0.132 seconds, Fetched: 2 row(s)
```

### Download Data from S3

```shell
hdfs dfs -mkdir -p /user/hdfs/data

wget https://capstone-project-mlc-metadata.s3.amazonaws.com/app_labels_new.txt
wget https://capstone-project-mlc-metadata.s3.amazonaws.com/label_categories.csv
	
hdfs dfs -put app_labels_new.txt /user/hdfs/data/
hdfs dfs -put label_categories.csv /user/hdfs/data/

hdfs dfs -ls /user/hdfs/data/
```

```shell
Found 2 items
-rw-r--r--   1 hadoop hdfsadmingroup   11190003 2022-12-24 17:11 /user/hdfs/data/app_labels_new.txt
-rw-r--r--   1 hadoop hdfsadmingroup      16450 2022-12-24 17:11 /user/hdfs/data/label_categories.csv
```

### Ingesting Data from RDS

```shell
sudo yum install mysql-connector-java*

sqoop import --connect jdbc:mysql://mlc-testcapstone.cyaielc9bmnf.us-east-1.rds.amazonaws.com/mlctest --table events  --username student --password STUDENT123 -m 1 --hive-import --create-hive-table --hive-table telecom.events

sqoop import --connect jdbc:mysql://mlc-testcapstone.cyaielc9bmnf.us-east-1.rds.amazonaws.com/mlctest --table app_events  --username student --password STUDENT123 -m 1 --hive-import --create-hive-table --hive-table telecom.app_events

sqoop import --connect jdbc:mysql://mlc-testcapstone.cyaielc9bmnf.us-east-1.rds.amazonaws.com/mlctest --table brand_device  --username student --password STUDENT123 -m 1 --hive-import --create-hive-table --hive-table telecom.brand_device

sqoop import --connect jdbc:mysql://mlc-testcapstone.cyaielc9bmnf.us-east-1.rds.amazonaws.com/mlctest --table train  --username student --password STUDENT123 -m 1 --hive-import --create-hive-table --hive-table telecom.train
```


### Creating Tables and Loading Data Downloaded from S3

```HQL
hive> use telecom;
OK
Time taken: 0.027 seconds
hive> CREATE EXTERNAL TABLE IF NOT EXISTS app_labels (app_id string, label_id string) ROW FORMAT DELIMITED FIELDS TERMINATED BY "," LINES TERMINATED BY "\n" STORED AS textfile;
OK
Time taken: 0.578 seconds
hive> CREATE EXTERNAL TABLE IF NOT EXISTS label_categories (label_id string, category string) ROW FORMAT DELIMITED FIELDS TERMINATED BY "," LINES TERMINATED BY "\n" STORED AS textfile;
OK
Time taken: 0.086 seconds
```

```HQL
hive> SHOW TABLES;
OK
app_events
app_labels
brand_device
events
label_categories
train
Time taken: 0.036 seconds, Fetched: 6 row(s)
```

```HQL
hive> LOAD DATA INPATH '/user/hdfs/data/app_labels_new.txt' INTO TABLE app_labels;
Loading data to table telecom.app_labels
OK
Time taken: 0.726 seconds
hive> LOAD DATA INPATH '/user/hdfs/data/label_categories.csv' INTO TABLE label_categories;
Loading data to table telecom.label_categories
OK
Time taken: 0.261 seconds
```

```HQL
hive> set hive.cli.print.header=true;
hive> set hive.strict.checks.cartesian.product=false;
hive> set hive.mapred.mode=nonstrict;
hive> SELECT * FROM events LIMIT 5;
OK
events.event_id	events.device_id	events.timestamp	events.longitude	events.latitude
1	29182687948017100	2016-05-01 00:55:25.0	121.38	31.24
2	-6401643145415150000	2016-05-01 00:54:12.0	103.65	30.97
3	-4833982096941400000	2016-05-01 00:08:05.0	106.6	29.7
4	-6815121365017310000	2016-05-01 00:06:40.0	104.27	23.28
5	-5373797595892510000	2016-05-01 00:07:18.0	115.88	28.66
Time taken: 0.091 seconds, Fetched: 5 row(s)
hive> SELECT * FROM app_events LIMIT 5;
OK
app_events.event_id	app_events.app_id	app_events.is_installed	app_events.is_active
2	5927333115845830913	1	1
2	-5720078949152207372	1	0
2	-1633887856876571208	1	0
2	-653184325010919369	1	1
2	8693964245073640147	1	1
Time taken: 0.081 seconds, Fetched: 5 row(s)
hive> SELECT * FROM brand_device LIMIT 5;
OK
brand_device.device_id	brand_device.phone_brand	brand_device.device_model
-1000146476441210000	Meizu	menote1
-1000369272589010000	vivo	Y17T
-1000572055892390000	OPPO	R819T
-1000633257325350000	samsung	Galaxy Note 2
-1000643208750510000	Gionee	GN137
Time taken: 0.087 seconds, Fetched: 5 row(s)
hive> SELECT * FROM train LIMIT 5;
OK
train.device_id	train.gender	train.age	train.group_train
-7548291590301750000	M	33	M32+
6943568600617760000	M	37	M32+
5441349705980020000	M	40	M32+
-5393876656119450000	M	33	M32+
4543988487649880000	M	53	M32+
Time taken: 0.101 seconds, Fetched: 5 row(s)
hive> SELECT * FROM app_labels LIMIT 5;
OK
app_labels.app_id	app_labels.label_id
app_id	label_id
7324884708820027918	251
-4494216993218550286	251
6058196446775239644	406
6058196446775239644	407
Time taken: 0.074 seconds, Fetched: 5 row(s)
hive> SELECT * FROM label_categories LIMIT 5;
OK
label_categories.label_id	label_categories.category
label_id	category
1	
2	game-game type
3	game-Game themes
4	game-Art Style
Time taken: 0.071 seconds, Fetched: 5 row(s)
```

## Data Analysis using SQL

```SQL
MySQL [(none)]> SHOW DATABASES;
+--------------------+
| Database           |
+--------------------+
| information_schema |
| mlctest            |
+--------------------+
2 rows in set (0.00 sec)

MySQL [(none)]> USE mlctest;
Reading table information for completion of table and column names
You can turn off this feature to get a quicker startup with -A

Database changed
```

### 1. Count of unique device ids in the train table

```SQL
MySQL [mlctest]> SELECT COUNT(DISTINCT device_id) FROM train;
+---------------------------+
| COUNT(DISTINCT device_id) |
+---------------------------+
|                     74645 |
+---------------------------+
1 row in set (0.12 sec)
```

### 2. Check whether there are any duplicate device ids present in the brand_device table. If yes, how many duplicates

```SQL
MySQL [mlctest]> SELECT COUNT(DISTINCT device_id) FROM brand_device WHERE device_id IN (SELECT device_id FROM brand_device GROUP BY device_id having COUNT(device_id) > 1);
+---------------------------+
| COUNT(DISTINCT device_id) |
+---------------------------+
|                       532 |
+---------------------------+
1 row in set (1.19 sec)
```

### 3. Number of unique phone brands from the brand_device table

```SQL
MySQL [mlctest]> SELECT COUNT(DISTINCT phone_brand) FROM brand_device;
+-----------------------------+
| COUNT(DISTINCT phone_brand) |
+-----------------------------+
|                          97 |
+-----------------------------+
1 row in set (0.07 sec)
```

### 4. Count of device ids WHERE the latitude and longitude detail are zero, FROM the events table

```SQL
MySQL [mlctest]> SELECT COUNT(DISTINCT device_id) FROM events WHERE longitude = 0 AND latitude = 0;
+---------------------------+
| COUNT(DISTINCT device_id) |
+---------------------------+
|                     49861 |
+---------------------------+
1 row in set (3.79 sec)
```

## Data Analysis using HQL

### Removing duplicates in `brand_device` table

```HQL
hive> INSERT OVERWRITE TABLE brand_device SELECT * FROM brand_device WHERE device_id IN (SELECT device_id FROM brand_device GROUP BY device_id);
Query ID = hadoop_20230112153926_a9ab1956-f3d3-402d-a431-44d6538c35fc
Total jobs = 1
Launching Job 1 out of 1
Status: Running (Executing on YARN cluster with App id application_1673536903115_0010)

----------------------------------------------------------------------------------------------
        VERTICES      MODE        STATUS  TOTAL  COMPLETED  RUNNING  PENDING  FAILED  KILLED
----------------------------------------------------------------------------------------------
Map 1 .......... container     SUCCEEDED      1          1        0        0       0       0
Map 2 .......... container     SUCCEEDED      1          1        0        0       0       0
Reducer 3 ...... container     SUCCEEDED      2          2        0        0       0       0
----------------------------------------------------------------------------------------------
VERTICES: 03/03  [==========================>>] 100%  ELAPSED TIME: 7.48 s
----------------------------------------------------------------------------------------------
Loading data to table telecom.brand_device
OK
brand_device.device_id	brand_device.phone_brand	brand_device.device_model
Time taken: 10.193 seconds
```

```HQL
hive> INSERT OVERWRITE TABLE brand_device SELECT DISTINCT * FROM brand_device WHERE device_id NOT IN (SELECT device_id FROM brand_device GROUP BY device_id having COUNT(device_id) > 1);
Warning: Map Join MAPJOIN[41][bigTable=?] in task 'Reducer 4' is a cross product
Query ID = hadoop_20230112153958_1dfc3846-fa0c-4a19-99b5-84ce7c3135ad
Total jobs = 1
Launching Job 1 out of 1
Status: Running (Executing on YARN cluster with App id application_1673536903115_0010)

----------------------------------------------------------------------------------------------
        VERTICES      MODE        STATUS  TOTAL  COMPLETED  RUNNING  PENDING  FAILED  KILLED
----------------------------------------------------------------------------------------------
Map 1 .......... container     SUCCEEDED      1          1        0        0       0       0
Map 2 .......... container     SUCCEEDED      1          1        0        0       0       0
Map 6 .......... container     SUCCEEDED      1          1        0        0       0       0
Reducer 3 ...... container     SUCCEEDED      2          2        0        0       0       0
Reducer 4 ...... container     SUCCEEDED      1          1        0        0       0       0
Reducer 5 ...... container     SUCCEEDED      2          2        0        0       0       0
Reducer 7 ...... container     SUCCEEDED      2          2        0        0       0       0
----------------------------------------------------------------------------------------------
VERTICES: 07/07  [==========================>>] 100%  ELAPSED TIME: 10.24 s
----------------------------------------------------------------------------------------------
Loading data to table telecom.brand_device
OK
brand_device.device_id	brand_device.phone_brand	brand_device.device_model
Time taken: 11.296 seconds
```

### 1. The 10 most popular brands and the percentage of the respective Male and Female owners of these brands? \[Handle the device id duplicates from brand_device  table.\]

```HQL
hive> WITH A AS (SELECT phone_brand, COUNT(device_id) AS cdid FROM brand_device GROUP BY phone_brand ORDER BY cdid DESC LIMIT 10), B AS (SELECT A.phone_brand, bd.device_id FROM brand_device bd INNER JOIN A ON A.phone_brand = bd.phone_brand) SELECT B.phone_brand as phone_brand, SUM(CASE WHEN gender='M' then 1 else 0 end)/(0.01*count(gender)) AS Percentage_male, SUM(CASE WHEN gender = 'F' then 1 else 0 end)/(0.01*count(gender)) AS Percentage_female FROM train INNER JOIN B ON train.device_id = B.device_id GROUP BY phone_brand;
No Stats for telecom@train, Columns: device_id, gender
No Stats for telecom@brand_device, Columns: device_id, phone_brand
No Stats for telecom@brand_device, Columns: device_id, phone_brand
Query ID = hadoop_20230112154511_1092bd4c-15bf-4ea8-887b-04b6465545cd
Total jobs = 1
Launching Job 1 out of 1
Status: Running (Executing on YARN cluster with App id application_1673536903115_0010)

----------------------------------------------------------------------------------------------
        VERTICES      MODE        STATUS  TOTAL  COMPLETED  RUNNING  PENDING  FAILED  KILLED
----------------------------------------------------------------------------------------------
Map 1 .......... container     SUCCEEDED      1          1        0        0       0       0
Map 2 .......... container     SUCCEEDED      1          1        0        0       0       0
Map 3 .......... container     SUCCEEDED      1          1        0        0       0       0
Reducer 4 ...... container     SUCCEEDED      2          2        0        0       0       0
Reducer 5 ...... container     SUCCEEDED      1          1        0        0       0       0
Reducer 6 ...... container     SUCCEEDED      2          2        0        0       0       0
----------------------------------------------------------------------------------------------
VERTICES: 06/06  [==========================>>] 100%  ELAPSED TIME: 7.72 s
----------------------------------------------------------------------------------------------
OK
phone_brand	percentage_male	percentage_female
Coolpad	67.58786422349053770	32.41213577650946230
HTC	68.44708209693372898	31.55291790306627102
Meizu	72.30637934713036057	27.69362065286963943
OPPO	55.56904927133934768	44.43095072866065232
Xiaomi	65.78611980071834086	34.21388019928165914
lenovo	66.80312616300707108	33.19687383699292892
vivo	52.95584045584045584	47.04415954415954416
Gionee	64.26024955436720143	35.73975044563279857
Huawei	67.24978713522718477	32.75021286477281523
samsung	60.24794600938967136	39.75205399061032864
Time taken: 8.569 seconds, Fetched: 10 row(s)
```

### 2. The 10 most popular brands for Male and Female? \[Handle the device id duplicates from the brand_device data set.\]

#### Query for Males
```HQL
hive> WITH A AS (SELECT device_id, gender FROM train where gender = 'M') SELECT phone_brand, COUNT(A.device_id) AS count_device_id FROM brand_device bd INNER JOIN A ON A.device_id = bd.device_id GROUP BY phone_brand ORDER BY count_device_id DESC LIMIT 10;
Query ID = hadoop_20230112155057_57e866c1-d9d8-45f3-a130-53100a2f7164
Total jobs = 1
Launching Job 1 out of 1
Status: Running (Executing on YARN cluster with App id application_1673536903115_0010)

----------------------------------------------------------------------------------------------
        VERTICES      MODE        STATUS  TOTAL  COMPLETED  RUNNING  PENDING  FAILED  KILLED
----------------------------------------------------------------------------------------------
Map 1 .......... container     SUCCEEDED      1          1        0        0       0       0
Map 4 .......... container     SUCCEEDED      1          1        0        0       0       0
Reducer 2 ...... container     SUCCEEDED      2          2        0        0       0       0
Reducer 3 ...... container     SUCCEEDED      1          1        0        0       0       0
----------------------------------------------------------------------------------------------
VERTICES: 04/04  [==========================>>] 100%  ELAPSED TIME: 6.13 s
----------------------------------------------------------------------------------------------
OK
phone_brand	count_device_id
Xiaomi	11356
Huawei	8688
samsung	8213
Meizu	3389
OPPO	3203
vivo	2974
Coolpad	2250
lenovo	1795
Gionee	721
HTC	692
Time taken: 6.674 seconds, Fetched: 10 row(s)
```

#### Query for Females
```HQL
hive> WITH A AS (SELECT device_id, gender FROM train where gender = 'F') SELECT phone_brand, COUNT(A.device_id) AS count_device_id FROM brand_device bd INNER JOIN A ON A.device_id = bd.device_id GROUP BY phone_brand ORDER BY count_device_id DESC LIMIT 10;
Query ID = hadoop_20230112155023_52e2fcf1-f418-4377-a0d2-28974c2bf3dc
Total jobs = 1
Launching Job 1 out of 1
Status: Running (Executing on YARN cluster with App id application_1673536903115_0010)

----------------------------------------------------------------------------------------------
        VERTICES      MODE        STATUS  TOTAL  COMPLETED  RUNNING  PENDING  FAILED  KILLED
----------------------------------------------------------------------------------------------
Map 1 .......... container     SUCCEEDED      1          1        0        0       0       0
Map 4 .......... container     SUCCEEDED      1          1        0        0       0       0
Reducer 2 ...... container     SUCCEEDED      2          2        0        0       0       0
Reducer 3 ...... container     SUCCEEDED      1          1        0        0       0       0
----------------------------------------------------------------------------------------------
VERTICES: 04/04  [==========================>>] 100%  ELAPSED TIME: 6.24 s
----------------------------------------------------------------------------------------------
OK
phone_brand	count_device_id
Xiaomi	5906
samsung	5419
Huawei	4231
vivo	2642
OPPO	2561
Meizu	1298
Coolpad	1079
lenovo	892
Gionee	401
HTC	319
Time taken: 6.747 seconds, Fetched: 10 row(s)
```

### 3. The count and percentage analysis of the Gender in the train data set

```HQL
hive> SELECT gender, COUNT(1) AS gender_COUNT, SUM(pct) AS gender_pct FROM train CROSS JOIN (SELECT 100 / CAST(COUNT(1) AS DECIMAL(10,2)) AS pct FROM train) C GROUP BY gender;
Warning: Map Join MAPJOIN[19][bigTable=?] in task 'Map 1' is a cross product
Query ID = hadoop_20230112155248_11736545-aa9e-4dbb-9746-1c73d02efb47
Total jobs = 1
Launching Job 1 out of 1
Status: Running (Executing on YARN cluster with App id application_1673536903115_0010)

----------------------------------------------------------------------------------------------
        VERTICES      MODE        STATUS  TOTAL  COMPLETED  RUNNING  PENDING  FAILED  KILLED
----------------------------------------------------------------------------------------------
Map 1 .......... container     SUCCEEDED      1          1        0        0       0       0
Map 3 .......... container     SUCCEEDED      1          1        0        0       0       0
Reducer 2 ...... container     SUCCEEDED      2          2        0        0       0       0
Reducer 4 ...... container     SUCCEEDED      1          1        0        0       0       0
----------------------------------------------------------------------------------------------
VERTICES: 04/04  [==========================>>] 100%  ELAPSED TIME: 6.35 s
----------------------------------------------------------------------------------------------
OK
gender	gender_count	gender_pct
F	26741	35.82423473486
M	47904	64.17576533184
Time taken: 6.853 seconds, Fetched: 2 row(s)
```

### 4. The top mobile phone brands offering the highest number of models \[Provide details about the top three brands.\]

```HQL
hive> SELECT phone_brand, COUNT(distinct(device_model)) AS model_count FROM brand_device GROUP BY phone_brand ORDER BY model_count DESC LIMIT 3;
Query ID = hadoop_20230112155453_6191e3eb-045d-4c93-8189-7833053e9114
Total jobs = 1
Launching Job 1 out of 1
Status: Running (Executing on YARN cluster with App id application_1673536903115_0010)

----------------------------------------------------------------------------------------------
        VERTICES      MODE        STATUS  TOTAL  COMPLETED  RUNNING  PENDING  FAILED  KILLED
----------------------------------------------------------------------------------------------
Map 1 .......... container     SUCCEEDED      1          1        0        0       0       0
Reducer 2 ...... container     SUCCEEDED      2          2        0        0       0       0
Reducer 3 ...... container     SUCCEEDED      1          1        0        0       0       0
----------------------------------------------------------------------------------------------
VERTICES: 03/03  [==========================>>] 100%  ELAPSED TIME: 4.58 s
----------------------------------------------------------------------------------------------
OK
phone_brand	model_count
lenovo	194
samsung	163
Huawei	145
Time taken: 5.044 seconds, Fetched: 3 row(s)
```

### 5. The average number of events per device id \[Applicable to the device_id column from the train table, which has at least one associated event in the event table\]

```HQL
hive> SELECT COUNT(*) AS events_count, COUNT( distinct train.device_id) AS device_count, COUNT(*)/COUNT(distinct train.device_id) AS avg_events FROM events INNER JOIN train ON train.device_id = events.device_id;
Query ID = hadoop_20230112155606_0d6ca926-6576-4561-b3ff-6f319d731cb0
Total jobs = 1
Launching Job 1 out of 1
Status: Running (Executing on YARN cluster with App id application_1673536903115_0010)

----------------------------------------------------------------------------------------------
        VERTICES      MODE        STATUS  TOTAL  COMPLETED  RUNNING  PENDING  FAILED  KILLED
----------------------------------------------------------------------------------------------
Map 1 .......... container     SUCCEEDED     12         12        0        0       0       0
Map 3 .......... container     SUCCEEDED      1          1        0        0       0       0
Reducer 2 ...... container     SUCCEEDED      1          1        0        0       0       0
----------------------------------------------------------------------------------------------
VERTICES: 03/03  [==========================>>] 100%  ELAPSED TIME: 28.38 s
----------------------------------------------------------------------------------------------
OK
events_count	device_count	avg_events
1215598	23310	52.14920634920635
Time taken: 28.862 seconds, Fetched: 1 row(s)
```

### 6. Whether the count and percentage of the device_id column in the train table have corresponding events data available

```HQL
hive> SELECT train.device_id, COUNT(events.event_id) AS event_count, SUM(pct) AS event_pct FROM train LEFT JOIN events ON train.device_id = events.device_id CROSS JOIN (SELECT 100 / CAST(COUNT(1) AS DECIMAL(10,2)) AS pct FROM events) e GROUP BY train.device_id ORDER BY event_count DESC LIMIT 20;
No Stats for telecom@train, Columns: device_id
No Stats for telecom@events, Columns: event_id, device_id
Warning: Map Join MAPJOIN[29][bigTable=?] in task 'Map 1' is a cross product
Query ID = hadoop_20230112160530_ddc5e4b2-da4e-48ec-9cdd-55de8a46bb66
Total jobs = 1
Launching Job 1 out of 1
Status: Running (Executing on YARN cluster with App id application_1673536903115_0010)

----------------------------------------------------------------------------------------------
        VERTICES      MODE        STATUS  TOTAL  COMPLETED  RUNNING  PENDING  FAILED  KILLED
----------------------------------------------------------------------------------------------
Map 1 .......... container     SUCCEEDED      1          1        0        0       0       0
Map 4 .......... container     SUCCEEDED     12         12        0        0       0       0
Map 5 .......... container     SUCCEEDED     12         12        0        0       0       0
Reducer 2 ...... container     SUCCEEDED      4          4        0        0       0       0
Reducer 3 ...... container     SUCCEEDED      1          1        0        0       0       0
Reducer 6 ...... container     SUCCEEDED      1          1        0        0       0       0
----------------------------------------------------------------------------------------------
VERTICES: 06/06  [==========================>>] 100%  ELAPSED TIME: 32.60 s
----------------------------------------------------------------------------------------------
OK
train.device_id	event_count	event_pct
-6242501228649110000	4150	0.12757651950
-8340098378141150000	3973	0.12213530409
-3746248670824150000	3907	0.12010637631
5375599021847300000	3128	0.09615888024
4782582047729160000	2899	0.08911911567
1779631023439400000	2757	0.08475384681
5098778421671830000	2722	0.08367790026
3724654925765150000	2347	0.07214990151
-6875585507485880000	2310	0.07101247230
6356179019102870000	2023	0.06218971059
-1516688507910540000	1915	0.05886964695
-3230567043058250000	1749	0.05376658617
-3926780516486000000	1686	0.05182988238
-2241630667689900000	1519	0.04669608027
3074308677943390000	1511	0.04645014963
1057289835566390000	1493	0.04589680569
2334568628287620000	1444	0.04439048052
-1448078833416770000	1368	0.04205413944
2297498661011100000	1364	0.04193117412
-4912313799611450000	1363	0.04190043279
Time taken: 33.24 seconds, Fetched: 20 row(s)
```

```HQL
hive> SELECT train.device_id, COUNT(events.event_id) AS event_count, SUM(pct) AS event_pct FROM train LEFT JOIN events ON train.device_id = events.device_id CROSS JOIN (SELECT 100 / CAST(COUNT(1) AS DECIMAL(10,2)) AS pct FROM events) e GROUP BY train.device_id ORDER BY event_count ASC LIMIT 5;
No Stats for telecom@train, Columns: device_id
No Stats for telecom@events, Columns: event_id, device_id
Warning: Map Join MAPJOIN[29][bigTable=?] in task 'Map 1' is a cross product
Query ID = hadoop_20230112160810_2850ec9c-b497-4b14-9cb0-70101584a4fd
Total jobs = 1
Launching Job 1 out of 1
Status: Running (Executing on YARN cluster with App id application_1673536903115_0010)

----------------------------------------------------------------------------------------------
        VERTICES      MODE        STATUS  TOTAL  COMPLETED  RUNNING  PENDING  FAILED  KILLED
----------------------------------------------------------------------------------------------
Map 1 .......... container     SUCCEEDED      1          1        0        0       0       0
Map 4 .......... container     SUCCEEDED     12         12        0        0       0       0
Map 5 .......... container     SUCCEEDED     12         12        0        0       0       0
Reducer 2 ...... container     SUCCEEDED      4          4        0        0       0       0
Reducer 3 ...... container     SUCCEEDED      1          1        0        0       0       0
Reducer 6 ...... container     SUCCEEDED      1          1        0        0       0       0
----------------------------------------------------------------------------------------------
VERTICES: 06/06  [==========================>>] 100%  ELAPSED TIME: 32.99 s
----------------------------------------------------------------------------------------------
OK
train.device_id	event_count	event_pct
-1000369272589010000	0	0.00003074133
999942881634637000	0	0.00003074133
-1008485807774290000	0	0.00003074133
-1004665990003060000	0	0.00003074133
-1003040252653180000	0	0.00003074133
Time taken: 33.635 seconds, Fetched: 5 row(s)
```

## Data Preparation

### Non-Event Data
```HQL
hive> CREATE EXTERNAL TABLE non_event_data (device_id STRING, gender STRING, age INT, group_train STRING, phone_brand STRING, device_model STRING) ROW FORMAT DELIMITED FIELDS TERMINATED BY ',' LINES TERMINATED BY '\n' STORED AS textfile LOCATION 's3://capstone-test-bucket/Data/EventData';
OK
Time taken: 8.917 seconds

hive> INSERT OVERWRITE TABLE non_event_data SELECT train.device_id, train.gender, train.age, train.group_train, bd.phone_brand, bd.device_model FROM train LEFT JOIN brand_device bd ON train.device_id = bd.device_id;
Query ID = hadoop_20230112183746_2dc76191-d1b0-4279-9615-68b17463118a
Total jobs = 1
Launching Job 1 out of 1
Status: Running (Executing on YARN cluster with App id application_1673546956249_0011)

----------------------------------------------------------------------------------------------
        VERTICES      MODE        STATUS  TOTAL  COMPLETED  RUNNING  PENDING  FAILED  KILLED
----------------------------------------------------------------------------------------------
Map 1 .......... container     SUCCEEDED      1          1        0        0       0       0
Map 2 .......... container     SUCCEEDED      1          1        0        0       0       0
----------------------------------------------------------------------------------------------
VERTICES: 02/02  [==========================>>] 100%  ELAPSED TIME: 10.41 s
----------------------------------------------------------------------------------------------
Loading data to table telecom.non_event_data
OK
train.device_id	train.gender	train.age	train.group_train	bd.phone_brand	bd.device_model
Time taken: 14.501 seconds

hive> SHOW TBLPROPERTIES non_event_data;
OK
prpt_name	prpt_value
COLUMN_STATS_ACCURATE	{"BASIC_STATS":"true"}
EXTERNAL	TRUE
numFiles	1
numRows	74645
rawDataSize	3462382
totalSize	3537027
transient_lastDdlTime	1673548680
Time taken: 0.034 seconds, Fetched: 7 row(s)
```

### Event Data
```HQL
hive> ALTER TABLE events CHANGE `timestamp` time_stamp string;
OK
Time taken: 0.055 seconds

hive> CREATE EXTERNAL TABLE event_data (device_id STRING, gender STRING, age INT, group_train STRING, event_id INT, time_stamp timestamp, longitude FLOAT, latitude FLOAT) ROW FORMAT DELIMITED FIELDS TERMINATED BY ',' LINES TERMINATED BY '\n' STORED AS textfile LOCATION 's3://capstone-test-bucket/Data/EventData';
OK
Time taken: 0.497 seconds

hive> INSERT OVERWRITE TABLE event_data SELECT train.device_id, train.gender, train.age, train.group_train, events.event_id, events.time_stamp, events.longitude, events.latitude FROM train LEFT JOIN events ON train.device_id = events.device_id;
Query ID = hadoop_20230113171504_91a24770-0bac-44bb-80bd-cefd2669f10d
Total jobs = 1
Launching Job 1 out of 1
Tez session was closed. Reopening...
Session re-established.
Status: Running (Executing on YARN cluster with App id application_1673626719230_0018)

----------------------------------------------------------------------------------------------
        VERTICES      MODE        STATUS  TOTAL  COMPLETED  RUNNING  PENDING  FAILED  KILLED
----------------------------------------------------------------------------------------------
Map 1 .......... container     SUCCEEDED      1          1        0        0       0       0
Map 2 .......... container     SUCCEEDED     12         12        0        0       0       0
----------------------------------------------------------------------------------------------
VERTICES: 02/02  [==========================>>] 100%  ELAPSED TIME: 21.29 s
----------------------------------------------------------------------------------------------
Loading data to table telecom.event_data
OK
_col0	_col1	_col2	_col3	_col4	_col5	_col6	_col7
Time taken: 27.403 seconds

hive> SHOW TBLPROPERTIES event_data;
OK
prpt_name	prpt_value
COLUMN_STATS_ACCURATE	{"BASIC_STATS":"true"}
EXTERNAL	TRUE
numFiles	1
numRows	1266933
rawDataSize	65711150
totalSize	66978083
transient_lastDdlTime	1673548891
Time taken: 0.033 seconds, Fetched: 7 row(s)
```

### App Data

```HQL
hive> CREATE EXTERNAL TABLE app_data (event_id INT, app_id STRING, is_installed INT, is_active INT, label_id STRING, category STRING) ROW FORMAT DELIMITED FIELDS TERMINATED BY ',' LINES TERMINATED BY '\n' STORED AS textfile LOCATION 's3://capstone-test-bucket/Data/EventData';
OK
Time taken: 0.503 seconds

hive> INSERT OVERWRITE TABLE app_data SELECT app_events.event_id, app_events.app_id, app_events.is_installed, app_events.is_active, app_labels.label_id, label_categories.category FROM app_events LEFT JOIN app_labels ON app_events.app_id = app_labels.app_id LEFT JOIN label_categories ON app_labels.label_id = label_categories.label_id;
No Stats for telecom@app_events, Columns: is_installed, event_id, is_active, app_id
No Stats for telecom@app_labels, Columns: app_id, label_id
No Stats for telecom@label_categories, Columns: category, label_id
Query ID = hadoop_20230112184219_c2648806-7330-4479-8c1e-45e1f282caa3
Total jobs = 1
Launching Job 1 out of 1
Status: Running (Executing on YARN cluster with App id application_1673546956249_0011)

----------------------------------------------------------------------------------------------
        VERTICES      MODE        STATUS  TOTAL  COMPLETED  RUNNING  PENDING  FAILED  KILLED
----------------------------------------------------------------------------------------------
Map 1 .......... container     SUCCEEDED     25         25        0        0       0       0
Map 2 .......... container     SUCCEEDED      1          1        0        0       0       0
Map 3 .......... container     SUCCEEDED      1          1        0        0       0       0
----------------------------------------------------------------------------------------------
VERTICES: 03/03  [==========================>>] 100%  ELAPSED TIME: 244.75 s
----------------------------------------------------------------------------------------------
Loading data to table telecom.app_data
OK
_col0	_col1	_col2	_col3	_col4	_col5
Time taken: 267.327 seconds

hive> SHOW TBLPROPERTIES app_data;
OK
prpt_name	prpt_value
COLUMN_STATS_ACCURATE	{"BASIC_STATS":"true"}
EXTERNAL	TRUE
numFiles	25
numRows	209355710
rawDataSize	10190722916
totalSize	10400078626
transient_lastDdlTime	1673549206
Time taken: 0.034 seconds, Fetched: 7 row(s)
```

