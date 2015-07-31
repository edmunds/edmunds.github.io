---
layout: post
title: Hadoop as a Viable Data Warehouse Platform, and More
tags: [Big Data]
image: /public/images/hadoop-logo.jpg

bio: Philip Potloff is EVP and CIO at Edmunds

biopic: 

featured-summary:
    <p>Hadoop as a Viable Data Warehouse Platform, and More.</p>

summary: 

---
<img src="{{site.baseimagesurl}}/hadoop-logo.jpg" />

In 2011 we made an important decision to take a barely worn path and initiate a new project to replace our core data warehouse (DWH) platform with a Hadoop-based implementation.  Like many organizations we were experiencing scalability, complexity and cost issues with our traditional DWH model, and new development time and big data growth were creating a significant resource drain on the company.

With no closely comparable reference implementations or internal Hadoop experience to speak of, we charged a small team of java developers to lead this effort with the goal of leveraging Hadoop to expand the scope of our DWH to become the system of record not just for our unstructured data (clickstream and ad impressions) but also structured data like inventory and vehicle specification sets.

The first several months of this initiative were pretty slow going, with the team learning the ins and outs of HDFS, MapReduce, HBase, Oozie, Hive, and Pig.  However, once the team had leveraged the framework to ingest, process and version our existing DWH data, we brought in the Analytics and BI teams to begin porting our reporting and ad hoc query infrastructure to leverage Hadoop.  And in February of this year we actually turned off the ETL jobs for our legacy DWH, with all Edmunds.com reporting functions now operating from Hadoop-managed data.

Was it a success?  Is there an ROI?  What's the best way to get started leveraging Hadoop? Turning off our legacy ETL was the literal definition of project success, but it has exceeded our expectations by becoming a central repository for Edmunds data rather than just a reporting endpoint.  One effort alone answers the ROI question, and since February the Business Analysts have used the combined data sets and increased processing capabilities to save over $1.7M from our paid search marketing budget through keyword bidding optimization.

For more Hadoop-specific questions, I sat down with Greg Rokita, Edmunds.com's Sr. Director of Software Architecture and Hadoop team lead to get his take on the project and how Hadoop and HBase will keep the Technology and Analytics teams ahead of Edmunds.com's Big Data demands.

<h2 class="question-heading">Can you first provide a brief description of Hadoop and HBase for those that might not be familiar with this framework?</h2>

Hadoop is composed of two subsystems: Hadoop Distributed File System that provides scalable, reliable and inexpensive storage and the MapReduce processing framework that allows for processing large quantities of data in a distributed and reliable manner. If you consider a database to be an abstraction on top of a filesystem then, by analogy, HBase is an abstraction on top of HDFS that provides users with higher level functionality rather than just files.  

<h2 class="question-heading">What made Hadoop a good call for our next generation DWH platform?  What were your concerns at the time?</h2>

We had always felt a need for a better DWH that processed all relevant data in a timely manner with limited failures. We wanted to tackle computationally and data intensive projects like paid search marketing optimization that just couldn't be run on our existing platform. Hadoop provided a cost-effective, industry standard approach to fulfill our growing needs. Our concerns were mostly related to the maturity of the platform, but with time that concern was alleviated as Hadoop distributions became more robust and broadly supported.

<h2 class="question-heading">What are the primary use cases for HBase in our environment?</h2>

We use HBase to store and version all of the structured data processed by DWH including inventory, transactions, leads, dealer information and vehicle configuration. Structured data is correlated with session events (clickstream) and the resulting aggregates are stored in HBase. The aggregated data is eventually published to web applications, reporting systems (Microstrategy, Platfora) and ad-hoc query systems (Netezza, Redshift) . 

<h2 class="question-heading">What does the column-oriented structure of HBase offer that wasn't easily accomplished with out traditional RDBMS?</h2>

HBase's flexible, column-oriented structure allows us to organize all events for a particular session/visitor in a single row.  Among other benefits, such organization provides for an elegant and performant solution to the session carry-over problem. The fixed relational schema structure of the legacy DWH placed artificial limits on the session length and induced overly complex processing logic. 

<h2 class="question-heading">How effective is HBase at dealing with different data types? How is versioning used?</h2>

HBase treats all data as binary and leaves up to the user the choice of data serialization. This flexibility allows us to not only store simple data types but also complex objects represented by Thrift.  HBase's built-in versioning allows us to recreate and republish all historical Edmunds datasets. For example, we can determine what was the lot inventory of a particular dealer 2 weeks ago, even though our inventory source systems only keep track of the current state of inventory.

<h2 class="question-heading">Describe the main differences between our ETL process pre and post Hadoop</h2>

Legacy DWH ETL processes were implemented with Informatica workflows that operated Relational Database Management Systems (RDBMS).  Aside from RDBMS intrinsic scalability and cost issues, the database was concurrently used by the users and reporting tools compounding the performance problems. The new DWH separates data processing (Hadoop and HBase) from user access and reporting (Netezza and Redshift). Scalability of the new system allows us to quickly and easily reprocess and test workflows. The processing speed combined with architectural and design choices we made reduced the DWH project development cycle for new requirements from months to weeks. Moreover, the scalability of the new platform allowed us to complete projects like paid search marketing optimization that was attempted several times on the legacy platform without success.  Actual data ingestion times have been reduced from 12+ hours each day to less than an hour.

<h2 class="question-heading">Do you see any limitations in this new architecture with your current line of sight into big data challenges?</h2>

One limitation of the platform is its batch oriented nature.  However, the new release of Hadoop--YARN allows other computational paradigms aside from Map-Reduce. Tools and frameworks such as Impala, Cloudera Search and DataTorrent  add powerful real-time capabilities to the platform.

<h2 class="question-heading">What were the key decisions that made this project a success?</h2>

We tried to free ourselves from DWH dogmas and approached the problem with a regular software project focus on performance, reliability and reducing complexity knowing that we have to handle a large quantity of data and numerous data sets. We made a conscious decision to eliminate dependencies on outside resources. For example, we use hash functions rather than stateful systems for ID generation.  (sequence number generation was a major performance bottleneck for the legacy DWH). We also abstracted complex vehicle classification (make, model, submodel, style) with a model that simplifies how other data sets refer to vehicle configuration.  

<h2 class="question-heading">How did your team become Hadoop experts?  What was their background?</h2>

The team had no prior Hadoop experience. Most of the team members had solid Java experience, but most importantly, everyone had a curiosity and willingness to learn new things.  We strongly encourage continuous refactoring to constantly improve the scalability and reliability of our jobs. Most refactors lead to pattern discovery that we can incorporate across different workflows. For example, the Data Provider pattern abstracts common interactions with HBase, speeds up development, simplifies and standardizes the code and asserts optimal performance across the modules.

<h2 class="question-heading">What is your advice to others considering adopting or experimenting with Hadoop? How do you recommend getting your feet wet?</h2>

Don't try to come up with perfect solution the first time around. Make all your operations idempotent and make sure that you have ability to easily rerun your workflows so that you can constantly refactor and improve. Avoid creating run-time dependencies on non-Hadoop based services. To get your feet wet, read up on basic Hadoop architecture and pick a use case that benefits from parallel execution. Once you can run the job reliably, try to optimize your code for the fastest performance with the minimum possible resource utilization. 
