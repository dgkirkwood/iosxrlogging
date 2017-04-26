# Containerised Log Management for IOSXR

Author: Dan Kirkwood

Email:  dkirkwoo@cisco.com


A pre-configured environment for collecting syslog from multiple Cisco IOSXR sources which offers an open API for searching against the syslog messages. 

This environment is built on the ELK stack, using Logstash for data ingest and pre-processing and Elasticsearch for the search and analytics engine.  
Elasticsearch can be viewed through the Kibana web front-end or can be accessed through an API - see documentation [here](https://www.elastic.co/guide/en/elasticsearch/client/python-api/current/index.html).

### Requirements
* Docker version 1.13  
* Docker Compose version 1.11  
* IOSXR source 

### Instructions
*Edit the docker-compose.yml file if you would like to change the network settings for the logging environment.  
If you would like to change the Syslog port used from the current 1514, be sure to edit both the docker-compose.yml and the logstash/logstash.conf file.*  
1. Run `docker-compose build` in the root directory to add configuration files to the logstash image.  
2. Run `docker-compose up` in the root directory to bring up the environment.  
3. You can now point your IOSXR software to the logstash container using `logging XX.XX.XX.XX severity info port 1514` with your Docker host IP address replacing XX.XX.XX.XX.



