### Iniciar ElasticSearch
+ `$ bin/elasticsearch`

### Estado cluster
+ `$ curl -XGET '<ip>:9200/_cat/health?v&pretty'`
  
### Nodos del cluster
+ `$ curl -XGET '<ip>:9200/_cat/nodes?v&pretty'`

### Indices
+ `$ curl -XGET '<ip>:9200/_cat/indices?v&pretty'`

### Crear indice
+ `$ curl -XPUT '<ip>:9200/<nombre_indice>?pretty&pretty'`
  
### Indexar ingreso de datos manual

+ `$ curl -XPUT '<ip>:9200/<nombre_indice>/external/<id>?pretty&pretty' -H 'Content-Type: application/json' -d'{ "<clave>": "<valor>" }'`

### Indexar archivo json
+ `$ curl -XPOST '<ip>:9200/<nombre_indice>/<tipo>/_bulk?pretty&refresh' --data-binary "@<nombre_archivo>.json"`
  
### Busqueda
+ `$ curl -XGET '<ip>:9200/nombre_indice/_search?<parametro>=<valor>&pretty&pretty'`
