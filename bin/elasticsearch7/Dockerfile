FROM elasticsearch:7.6.0

RUN bin/elasticsearch-plugin install https://github.com/fooger/elasticsearch-analysis-morphology/raw/master/analysis-morphology-7.6.0.zip

#ADD curl -XPUT -H "Content-Type: application/json" http://localhost:9200/_cluster/settings -d '{ "transient": { "cluster.routing.allocation.disk.threshold_enabled": false } }'
#ADD curl -XPUT -H "Content-Type: application/json" http://localhost:9200/_all/_settings -d '{"index.blocks.read_only_allow_delete": null}'

RUN mkdir -p /etc/elasticsearch/config
COPY ./config/ /usr/share/elasticsearch/config/

RUN set -ex \
    && for path in \
        /usr/share/elasticsearch/config/ \
    ; do \
        mkdir -p "$path"; \
        chown -R elasticsearch:elasticsearch "$path"; \
    done