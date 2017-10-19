# TallerInfonor-RI
Material para presentar en el taller de RI en la INFONOR 2017

# SolR

## Iniciar SolR
+ `bin/solr start`

## Crear core
+ `bin/solr -c <nombre_core>`

## Indexar archivo
+ `bin/post -c <nombre_core> <ruta_archivo>`

## Busqueda 
+ `cURL -XGET 'http://localhost:8983/solr/<nombre_core>/select?<parametro>=<valor>&..'`

## Parametros:

1.	**q**: Aquí es posible ingresar los parámetros principales de la consulta, donde es posible buscar por campo o por el valor de un campo. Algunas variantes de estas son las siguientes:
      + `*:*: Buscar en cualquier campo, cualquier valor.`
      + `[Nombre Campo].*: Buscar todos los valores de un campo específico.`
      + `*.[valor] : Busca un valor especifico en todos los campos.`
      + `[Nombre Campo]*[valor]*: Busca en Campo especificado los valores que contengan el valor especificado.`
      + `[valor] [valor] ~ [distancia] : Busca un registro que contenga un distancia no mayor al número especificado entre ellas.`
      + `[Nombre Campo]: [valor] to [valor]: Busca para el campo especificado los registros que están dentro de los valores específicos.`
2.	**sort**: asc|desc
3.	**start**,**row** : Cantidad de resultados a mostrar y desde que resultado mostrar.
4.	**fl**: Define los campos que se desean mostrar en el resultado de la consulta.
5.	**wt**: Formato de salida del resultado de la consulta (JSON, XML, etc).

## AdminUI
+ `<IP>:<port>/solr`



# ELK

## ElasticSearch

### iniciar ElasticSearch
+ `bin/elasticsearch`

### estado cluster
+ `curl -XGET '<ip>:9200/_cat/health?v&pretty'`
  
### ver nodos del cluster
+ `curl -XGET '<ip>:9200/_cat/nodes?v&pretty'`

### ver indices
+ `curl -XGET '<ip>:9200/_cat/indices?v&pretty'`

### crear indice
+ `curl -XPUT '<ip>:9200/<nombre_indice>?pretty&pretty'`
  
### indexar ingreso de datos manual

+ `curl -XPUT '<ip>:9200/<nombre_indice>/external/<id>?pretty&pretty' -H 'Content-Type: application/json' -d'{ "<clave>": "<valor>" }'`

### indexar archivo json
+ `curl -XPOST '<ip>:9200/<nombre_indice>/<tipo>/_bulk?pretty&refresh' --data-binary "@<nombre_archivo>.json"`
  
### busqueda 
+ `curl -XGET '<ip>:9200/nombre_indice/_search?<parametro>=<valor>&pretty&pretty'`



