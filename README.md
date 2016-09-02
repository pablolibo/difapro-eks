# kibana-sense-docker

Antes de correr docker-compose up:

docker ps -a | awk '{print $1}' | while read line; do docker stop $line; done
docker ps -a | awk '{print $1}' | while read line; do docker rm $line; done


--- Kibana ---

Para ver si levanto Kibana de buena manera: http://localhost:5601/status, tiene que estar todo en GREEN

--- ElasticSearch ---

Para ver los indices: http://localhost:9200/_cat/indices?v

un ejemplo para crear un indice:
'''
curl -XPUT localhost:9200/test -d '{
    "warmers" : {
        "warmer_1" : {
            "source" : {
                "query" : {
                    ...
                }
            }
        }
    }
}'
'''
