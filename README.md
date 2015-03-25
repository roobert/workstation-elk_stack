# workstation-elk-stack

## Deploy

```
ansible-playbook --ask-sudo-pass elk.yml
```

## Logstash-forwarder

Logstash-forwarder is configured to write the following to logstash:

* /var/log/syslog
* /var/log/auth.log

## Logstash

Logstash is configured to:

* accept json udp input (port: 5555)
* accept logstash-forwarder input
* filter and tag syslog messages
* write output to elasticsearch

## ElasticSearch

Two plugins are installed by ansible:

* http://localhost:9200/_plugin/head/
* http://localhost:9200/_plugin/HQ/

## Kibana

Open `http://localhost:5601` in a web browser then:
* select: Index contains time-based events
* deselect: Use event time to create index names
* pick `@timestamp` from: Time-field name
* click `create`
* confirm data is visible under 'Discover' tab

## TODO

* add elasticsearch-curator

## FAQ(!)
### What is ELK?

See: [here](https://www.elastic.co/webinars/elk-stack-devops-environment/).
