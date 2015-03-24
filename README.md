# workstation-ubuntu-elk

## Deploy

```
ansible-playbook --ask-sudo-pass elk.yml
```

## Configure Kibana

Open `localhost:5601` in a web browser and do the following:
* select: Index contains time-based events
* deselect: Use event time to create index names
* pick `@timestamp` from: Time-field name
* click `create`

## Todo:

* sort out elasticsearch sharding
* nginx configs
