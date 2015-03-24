# workstation-ubuntu-elk

## Deploy

```
sudo ansible-playbook elk.yml
```

## Configure Kibana

Goto `localhost:5601` in a web browser and select:
* Index contains time-based events
* Use event time to create index names
* Index pattern interval: daily
