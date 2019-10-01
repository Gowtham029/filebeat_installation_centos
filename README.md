# Install Filebeat

## Prerequisite
- CentOs
- Filebeat 7.3.x

### Steps to install
```sh
$ curl -L -O https://artifacts.elastic.co/downloads/beats/filebeat/filebeat-7.3.2-x86_64.rpm
$ sudo rpm -vi filebeat-7.3.2-x86_64.rpm
```

### Filebeat configurations
```
### Filebeat input prospects
filebeat.inputs:
- type: log
  paths:
    - /path/to/logs/*.log
  fields_under_root: true
  fields:
    type: app
  paths:
    - '/path/to/logs/*.log'
  fields_under_root: true
  fields:
    type: pm2
#----------------------------- Logstash output --------------------------------
output.logstash:
  # The Logstash hosts and port
  hosts: ["host:port"]
```
