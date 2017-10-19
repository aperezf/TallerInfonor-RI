# TallerInfonor-RI
Material para presentar en el taller de RI en la INFONOR 2017



# [Tutorial SolR](http://lucene.apache.org/solr/)



  

# ELK

## ElasticSearch

### iniciar ElasticSearch
+ `$ bin/elasticsearch`

### estado cluster
+ `$ curl -XGET '<ip>:9200/_cat/health?v&pretty'`
  
### ver nodos del cluster
+ `$ curl -XGET '<ip>:9200/_cat/nodes?v&pretty'`

### ver indices
+ `$ curl -XGET '<ip>:9200/_cat/indices?v&pretty'`

### crear indice
+ `$ curl -XPUT '<ip>:9200/<nombre_indice>?pretty&pretty'`
  
### indexar ingreso de datos manual

+ `$ curl -XPUT '<ip>:9200/<nombre_indice>/external/<id>?pretty&pretty' -H 'Content-Type: application/json' -d'{ "<clave>": "<valor>" }'`

### indexar archivo json
+ `$ curl -XPOST '<ip>:9200/<nombre_indice>/<tipo>/_bulk?pretty&refresh' --data-binary "@<nombre_archivo>.json"`
  
### busqueda 
+ `$ curl -XGET '<ip>:9200/nombre_indice/_search?<parametro>=<valor>&pretty&pretty'`



