# workstation-ubuntu-elk

## Deploy

```
sudo ansible-playbook elk.yml
```

## Configure Kibana

Goto `localhost:5601` in a web browser and do the following:
* select: Index contains time-based events
* deselect: Use event time to create index names
* pick @timestamp from: Time-field name
* click 'create'

## Todo:

* sort out elasticsearch sharding
* nginx configs
