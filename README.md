## SPARK SQL RDF BENCHMARKING

Recently, a wide range of Web applications (e.g. DBPedia,Uniprot, and Probase) are built on top of vast RDF knowledge bases and using the SPARQL query language. The continuous growth of these knowledge bases led to the investigation of new paradigms and technologies for storing, accessing, and querying RDF data. In practice, modern big data systems (e.g. Hadoop, Spark) can handle vast relational repositories, however, their application in the Semantic Web context is still limited. One possible reason is that such frameworks rely on distributed systems, which are good for relational data, however, their performance on dealing with graph data models like RDF have not been well-studied yet. 

This repository contains the [code](https://github.com/EyvazovSadiq/SPARKSQLRDFBenchmarking/tree/master/ProjectSourceCode/src/main/scala/ee/ut/cs/bigdata/sp2bench) and [result figures](https://github.com/EyvazovSadiq/SPARKSQLRDFBenchmarking/tree/master/figures) related to the paper _SPARKSQLRDFBenchmarking_.

In this paper, we drove our experiments using a representative query workloads from theSP2Benchbenchmark scenario. The results of our experiments show many interesting insights about the impact of the **relational encoding scheme**, **relational data partitioning**, **storage backends** and **storage formats** on the performance of the query execution process in the distributed environment of _Spark_.

#### RDF Relational schemas
-----
We present a systematic comparison of three relevant RDF relational schemas such as _Single Statement Table_, _Property Tables_, and _Vertically-Partitioned Tables_  queried using Apache Spark. 


**Single Statement Table** requires  storing RDF datasets in a single triples table of three columns that represent the three components of the RDF triple,i.e., Subject, Predicate, and Object.

<img src="https://github.com/EyvazovSadiq/SPARKSQLRDFBenchmarking/blob/master/figures/Partitioning_100M_ST.png" alt="spark" width="250" height="150">


**Vertically-Partitioned Tables** is an alterna-tive schema storage in which the RDF triples table is decomposed into a table of two columns (Subject, Object) for each unique property  in  the  RDF  dataset  such  that  the  first  (subject) column contains all subject URIs of that unique property, and the second (object) contains all the object values (URIs and Literals) for those subjects


**Property Tables** is proposed to cluster multiple RDF properties as n-ary table columns for the same subject to group entities that are similar instructure.




#### Storage backends and storage formats
-----
We evaluate the performance of SparkSQL querying engine for processing SPARQLqueries using two different storage backends, namely, Hive, and HDFS. For the latter one, we compare four different data formats(CSV, ORC, Avro, and Parquet). 

#### Partitioning techniques
-----
In addition, we show the impact of using three different RDF-based partitioning techniques with our relational scenario which are Subject-based, Predicate-based, and Horizontal partitioning. 


### RDFBenchmarking Results for Partitioning Techniques Comparison
---
<img src="https://github.com/EyvazovSadiq/SPARKSQLRDFBenchmarking/blob/master/figures/Partitioning_100M_ST.png" alt="spark" width="250" height="150">       <img src="https://github.com/EyvazovSadiq/SPARKSQLRDFBenchmarking/blob/master/figures/Partitioning_100M_VT.png" alt="spark" width="250" height="150">       <img src="https://github.com/EyvazovSadiq/SPARKSQLRDFBenchmarking/blob/master/figures/Partitioning_100M_PT.png" alt="spark" width="250" height="150">

<img src="https://github.com/EyvazovSadiq/SPARKSQLRDFBenchmarking/blob/master/figures/Partitioning_500M_ST.png" alt="spark" width="250" height="150">       <img src="https://github.com/EyvazovSadiq/SPARKSQLRDFBenchmarking/blob/master/figures/Partitioning_500M_VT.png" alt="spark" width="250" height="150">       <img src="https://github.com/EyvazovSadiq/SPARKSQLRDFBenchmarking/blob/master/figures/Partitioning_500M_PT.png" alt="spark" width="250" height="150">


### Installation
#


### Publication
#
Benchmarking Spark-SQL under alliterative RDF Relational Storage Backends have been published in [Researchgate](https://www.researchgate.net/publication/335378928_Benchmarking_Spark-SQL_under_alliterative_RDF_Relational_Storage_Backends) 

    M. Ragab, R. Tommasini and S. Sakr, Benchmarking SparkSQL under Alliterative RDF Relational Storage Backends (2019).
