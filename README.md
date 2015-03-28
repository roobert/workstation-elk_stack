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

* http://head.elasticsearch.localhost/
* http://hq.elasticsearch.localhost/

## Kibana

Open `http://kibana.localhost/` in a web browser then:
* select: Index contains time-based events
* deselect: Use event time to create index names
* pick `@timestamp` from: Time-field name
* click `create`
* confirm data is visible under 'Discover' tab

## About the Deployment
### DNS

DNS is configured by adding files containing virtual hosts to `/etc/NetworkManager/dnsmasq.d`.

During the deployment `NetworkManager` is restarted which may cause momentary loss of network connectivity.

### Nginx

`nginx` virtual hosts have been configured for each component but also allow some flexibility if an alternate DNS scheme is to be used. For each component the following `server_names` exist:

* `<component>.localhost`
* `<component>.*`
* `<component>`

## TODO

* add elasticsearch-curator

## FAQ(!)
### What is ELK?

See [here](https://www.elastic.co/webinars/elk-stack-devops-environment/).
