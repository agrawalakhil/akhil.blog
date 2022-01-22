---
layout: post
title: Lambda Architecture On Elasticsearch
---

<div class="message">
  This is a blog post was written in the past and brought here with minor changes only. There will be a newer version with more insights coming out soon.
</div>

Elasticsearch provides an extremely robust platform for building custom analytics application through flexible aggregations. Although, as data goes into 100gb range, the query performance starts to degrade, so a mechanism like lambda architecture is needed to ensure the queries are running fast (especially on fields with high cardinality) without increasing the infrastructure cost.

We have used similar architecture and design for a mobile advertising product, Adatrix. The raw data and batch views (created through background jobs) were both stored in elasticsearch in different indexes. UI was using only the batch views and the speed layer was not implemented as the requirement for real time statistics was not so much there, although as were using an in-memory database Aerospike, the speed layer could be implemented whenever a requirement comes up.

Cardinality is important factor in elasticsearch query performance and the fields with high cardinality seems to have higher performance degradation. In raw data, there is very high possibility of id field (like session id or message id) having high cardinality and statistics would have to be built on those fields.

#### Few important considerations for creating batch views

1. breaking batch views by time (like hourly, daily, weekly etc) helps in keeping the cardinality of these fields reasonable for queries which run on raw data
 
2. breaking batch views by dimension (master dimensions included for creating the batch view, for example if your data has attributes like location, device, advertiser, publisher, you can select some of those to create batch views and rest of the dimensions will be flattened)

#### Few important considerations for queries

* Direct queries on raw data (should not be done of very large data)

* Rolling up of summaries or batch views

* Batch views limits the kind of queries that can be done (as dimensions are flattened, cross dimension is not possible)

#### Also, for storing raw data on elasticsearch, few important optimizations are required

* only keeping reverse indexed data and not raw data (removing _source storage)
 
* keyed fields instead of raw text fields
 
* optimizing elasticsearch storage (removing _all, keeping cardinality of fields reasonable, if possible)

Lastly, one important consideration is with finding unique values for high cardinality fields like audience. The unique value cannot be rolled up, for example, the unique audience per day can't be added to find unique per week. So for this, some approximate algorithm like HyperLogLog has to be used to find unique statistics for high cardinality fields.

## Background - Lambda Architecture

In case the data generation per day goes above 3gb, your data generation is going into the big-data use case and now the most popular architecture for this kind of data generation is Lambda Architecture defined by Nathan Marz of Apache Storm (contributed by Twitter), more details provided in the end. Briefly, lambda architecture is layered architecture with speed layer (creating real time views for recent data), batch layer (raw data and creating batch views on older data) and serving layer (which combines queries through the batch views and realtime views).

Interesting video from Yieldbot (an advertising company)
- https://www.elastic.co/videos/building-lambda-architecture-elasticsearch-yieldbot
- https://www.elastic.co/guide/en/elasticsearch/guide/current/doc-values.html

Other important links
- http://lambda-architecture.net/
- http://voltdb.com/products/alternatives
- https://www.mapr.com/developercentral/lambda-architecture
- https://2014.nosql-matters.org/cgn/wp-content/uploads/2013/02/ArealtimeLambdaArchitectureusingHadoopStormNoSQL14-Nathan-B.pdf
