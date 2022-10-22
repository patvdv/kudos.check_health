## Plugin configuration

### Syntax

```yaml
hc_check_serviceguard_cluster_config:
  installed: <yes|no>    
  enabled: <yes|no>
  scheduled: <yes|no>
  log_healthy: <yes|no>
  cluster:
    - name: <cluster>
      params:
        - <parameter1>: <value>
        - <parameter2>: <value>
  cron:
    when: <time_date_definition>
    user: <text>
    action: <text>
    no_lock: <yes|no>
    timeout: <number_seconds>
    options: <text>        
```

Default values (non-null):
* *installed*: `no`
* *enabled*: `yes`
* *scheduled*: `no`
* *log_healthy*: `no`
* *cron/when*: `00 * * * *`
* *cron/user*: `root`
* *cron/action*: `--run`
* *cron/no_lock*: `no`

Setting the option *scheduled=yes* will result in the corresponding **cron** file to be created.

Setting the option *enabled=no* will disable the health check and will emulate a monitoring blackout or maintenance.

Following **check host** parameters are considered optional within the plugin parameter block:

```yaml
  check_host:
    active: <yes|no>
    config_file: <file_path>
    title: <text>
    timeout: <seconds>
```

### Example

```yaml
hc_check_serviceguard_cluster_config:
  enabled: "yes"
  scheduled: "yes"    
  log_healthy: "no"
  cluster:
    - name: "mycluster"
      params:
        - CLUSTER_NAME: "mycluster"
        - MAX_CONFIGURED_PACKAGES: 10
        - NODE_NAME: "acme1.server.com"
        - NETWORK_INTERFACE: "lan1"
        - HEARTBEAT_IP: "10.10.10.21"
        - NODE_NAME: "acme2.server.com"
        - NETWORK_INTERFACE: "lan1"
        - HEARTBEAT_IP: "10.10.10.22"
```

### Further reading

See the plugin configuration file `check_serviceguard_cluster_config.conf` for more explanation on the parameters and options.
