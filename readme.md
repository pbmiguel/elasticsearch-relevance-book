# Elastic Search Uses Cases From The Relevant Search Book #
This repo is a collection of uses cases inspired by the book The Relevant Search.


Collection of use-cases:
- Chapter 3 Use Case - searching and optimizing the "Space Jam" movie search (chapter-3-space-jam.ipynb)  


# How to setup locally
https://www.elastic.co/guide/en/elasticsearch/reference/current/run-elasticsearch-locally.html
1. Start an Elasticsearch container:
```
docker network create elastic
docker pull docker.elastic.co/elasticsearch/elasticsearch:8.5.2
docker run --name elasticsearch --net elastic -p 9200:9200 -p 9300:9300 -e "discovery.type=single-node" -t docker.elastic.co/elasticsearch/elasticsearch:8.5.2
```
When you start Elasticsearch for the first time, the generated elastic user password and Kibana enrollment token are output to the terminal.

2. Copy the generated password and enrollment token and save them in a secure location. These values are shown only when you start Elasticsearch for the first time. You’ll use these to enroll Kibana with your Elasticsearch cluster and log in.

4. Start Kibana
Kibana enables you to easily send requests to Elasticsearch and analyze, visualize, and manage data interactively.
In a new terminal session, start Kibana and connect it to your Elasticsearch container:
```
docker pull docker.elastic.co/kibana/kibana:8.5.2
docker run --name kibana --net elastic -p 5601:5601 docker.elastic.co/kibana/kibana:8.5.2
```
When you start Kibana, a unique URL is output to your terminal.

5. To access Kibana, open the generated URL in your browser.

Paste the enrollment token that you copied when starting Elasticsearch and click the button to connect your Kibana instance with Elasticsearch.
Log in to Kibana as the elastic user with the password that was generated when you started Elasticsearch.
