# Apache Mahout for Market Basket Analysis (Apriori Algorithm)

## Set up 
Hadoop 2.8.4 and Mahout 0.7 has been used.
(Hadoop is downgraded due to compatibility issues with the latest version of Mahout)

This set up can be performed on Google Colaboratory notebooks as well as Linux based systems.

## Useful Links
* Apache Mahout Official Site (download):
https://mahout.apache.org/

* Distributed Machine Learning with Apache Mahout:
https://dzone.com/refcardz/distributed-machine-learning?chapter=3

* Mahout tutorial
https://www.tutorialspoint.com/mahout/index.htm

* Apache Mahout Tutorial for Beginners at Edureka (2014):
https://www.youtube.com/watch?v=zvfKH9Yb0s0

## Installation of Apache Mahout:
Below are the steps to download Mahout 0.7 on Cloudera/Linux environment:
a. Download Mahout using command wget and unzip its contents:
```
wget http://archive.apache.org/dist/mahout/0.7/mahout-distribution-0.7-src.tar.gz
tar -xzf mahout-distribution-0.7-src.tar.gz
```
b. Go to the installation directory and use maven command to install all dependencies and
libraries like utils, math, etc.
```
cd mahout-distribution-0.7
mvn install –DskipTests
```
c. Set the Mahout Home path in the /etc/profile file on the virtual machine as shown below using
below commands:
```
sudo vim /etc/profile
source /etc/profile
```

## Steps to install Maven

1. Download Maven 3.8.5 from https://maven.apache.org/download.cgi
2. Unzip the archive using the following command:
```
tar -xvf apache-maven-3.8.5-bin.tar.gz
```
3. Set the path for your Maven directory in the ~/.bashrc file
Add the following lines:
```
export MAVEN_HOME = ~/maven
export PATH=$PATH:$MAVEN_HOME/bin
```
4. Execute ```maven -v```

## Frequent Pattern Mining algorithm
1. For running a program to get frequent item sets, Mahout has command –fpg which stands for
FPGrowth algorithm. This algorithm is an optimized version on Apriori Algorithm for mining
frequent itemset.
2. The input is the retail data set in the .dat format
3. The output directory will be generated on HDFS
4. Internally, this implementation runs by having a series of multiple MapReduce programs.
5. The number of top items with most frequent pattern is by default 50. 
6. Copy the retail data set into HDFS
```
hadoop fs –put /Downloads/retail.dat /user/input/
mahout fpg -i /user/input/retail.dat -o patternone -method mapreduce
```
