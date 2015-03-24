# workstation-elk-stack

## Deploy

```
ansible-playbook --ask-sudo-pass elk.yml
```

## Kibana

Open `http://localhost:5601` in a web browser and do the following:
* select: Index contains time-based events
* deselect: Use event time to create index names
* pick `@timestamp` from: Time-field name
* click `create`
* confirm data is visible under 'Discover' tab

## ElasticSearch

Two plugins are installed by ansible:

* http://localhost:9200/_plugin/head/
* http://localhost:9200/_plugin/HQ/
