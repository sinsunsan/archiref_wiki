### Elastic search  doc
* http://www.elasticsearchtutorial.com/elasticsearch-in-5-minutes.html
* https://www.elastic.co/
* Une video en français
https://www.elastic.co/webinars/demarrez-avec-elasticsearch
* The official guide 
https://www.elastic.co/guide/en/elasticsearch/guide/current/
* The chapter on how to communicate with the elastic search API
https://www.elastic.co/guide/en/elasticsearch/guide/current/data-in-data-out.html


### Install 
Unoficial to study ..
* https://gist.github.com/ondrej-kvasnovsky/9363975


### The elastic search project
* https://github.com/elastic/elasticsearch

### Config

### Customize the configuration file
elastic.yml 

* Change the cluster name
```
cluster.name
```
* Change the node name 
```
node.name 
```
* Desactivate the swap 

// uncomment 
```
bootstrap.unlockall: true 
```
* change network.host (for security)
// use only localhost 
```
network.host: 127.0.0.1 
```

### Launch elastic search 

To launch the process 
```
/bin/elasticsearch
```
* Port 9300 // Communication between node
* Port 9200 // Rest api call


### Make basic rest api calls
```
curl localhost:9200/_cluster/health?pretty
```
Where 
 
* _cluster is the name of the cluster as defined in the config file
* health is a special query to get the health (system state) of the cluster.
* ?pretty is a parameter to tell to output the json in prettified format


### Rest API call structure 

/World/people/slucas 
where slucas is the id of a json document containing information about user slucas

/Index/type/id 


#### Documents Id

in /World/people/slucas  we have used the id slucas 

If we want to have an auto generated id, we just leabe /World/people/
It will auto populate the id 

#### Document source

The document source is the plain json document not modified by elastic. 
It is available in the json object under _source

#### API verbs 

* POST to create a record 
* PUT to update a record (passing the full json object)
* DELETE to delete a record 



### Install marvel pluging

The UI to manage elastic search 
```
/bin/plugin install elasticsearch/marvel/latest
```

Marvel is a dashboard but also contain a plugin to send request to the api with a graphical ui better that just commmand line.
