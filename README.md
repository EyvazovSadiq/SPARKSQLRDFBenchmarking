## SPARK SQL RDF BENCHMARKING

Recently, a wide range of Web applications (e.g. DBPedia,Uniprot, and Probase) are built on top of vast RDF knowledge bases and using the SPARQL query language. The continuous growth of these knowledge bases led to the investigation of new paradigms and technologies for storing, accessing, and querying RDF data. In practice, modern big data systems (e.g. Hadoop, Spark) can handle vast relational repositories, however, their application in the Semantic Web context is still limited. One possible reason is that such frameworks rely on distributed systems, which are good for relational data, however, their performance on dealing with graph data models like RDF have not been well-studied yet. 

This repository contains the code and result figures related to the paper _SPARKSQLRDFBenchmarking_.

In this paper, we drove our experiments using a representative query workloads from theSP2Benchbenchmark scenario. The results of our experiments show many interesting insights about the impact of the **relational encoding scheme**, **relational data partitioning**, **storage backends** and **storage formats** on the performance of the query execution process in the distributed environment of _Spark_.

#### RDF relational schemas
In this paper, we present a systematiccomparison of three relevant RDF relational schemas, i.e., Single Statement Table (i.e. a single triples table), Property Tables (i.e.n-ary predicate-clustered tables), or Vertically-Partitioned Tables (i.e. a set of two-column tables resulting from predicate-basedpartitioning) queried using Apache Spark. 

#### Storage Backends and storage formats
We evaluate the performance of SparkSQL querying engine for processing SPARQLqueries using two different storage backends, namely, Hive, and HDFS. For the latter one, we compare four different data formats(CSV, ORC, Avro, and Parquet). 

#### Partitioning techniques
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
