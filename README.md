# Vietnamese Elasticsearch

```docker
docker build . -t es
```

```docker
docker run --name es \
    -p 9200:9200 \
    -p 9300:9300 \
    -e "discovery.type=single-node" \
    -d es
```

```docker
docker run --name kibana \
    --link es:elasticsearch \
    -p 5601:5601 \
    -d docker.elastic.co/kibana/kibana:7.3.1
```