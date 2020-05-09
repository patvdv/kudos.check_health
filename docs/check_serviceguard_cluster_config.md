## Plugin configuration

### Syntax

```yaml
hc_check_serviceguard_cluster_config:
  scheduled: <yes|no>
  log_healthy: <yes|no>
  cluster:
    - name: <cluster>
      params:
        - <parameter1>: <value>
        - <parameter2>: <value>
```

Default values (non-null):
* *scheduled*: `no`
* *log_healthy*: `no`

Setting *scheduled=yes* option will result in the corresponding **cron** bundle to be installed (if available)

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
