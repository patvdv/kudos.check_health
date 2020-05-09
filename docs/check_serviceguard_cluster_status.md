## Plugin configuration

### Syntax

```yaml
hc_check_serviceguard_cluster_status:
  scheduled: <yes|no>
  log_healthy: <yes|no>
  params:
    - name: <name>
      value: <value>
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
hc_check_serviceguard_cluster_status:
  scheduled: "yes"    
  log_healthy: "yes"
  params:
    - name: "status"
      value: "up"
    - name: "node:acme1.server.com|subnet:10.10.10.0|status"
      value: "up"
    - name: "node:acme2.server.com|subnet:10.10.10.0|status"
      value: "up"
```

### Further reading

See the plugin configuration file `check_serviceguard_cluster_status.conf` for more explanation on the parameters and options.
