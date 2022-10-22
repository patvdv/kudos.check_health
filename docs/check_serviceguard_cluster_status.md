## Plugin configuration

### Syntax

```yaml
hc_check_serviceguard_cluster_status:
  enabled: <yes|no>
  scheduled: <yes|no>
  log_healthy: <yes|no>
  params:
    - name: <name>
      value: <value>
  cron:
    when: <time_date_definition>
    user: <text>
    action: <text>
    no_lock: <yes|no>
    timeout: <number_seconds>
    options: <text>
```

Default values (non-null):
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
hc_check_serviceguard_cluster_status:
  enabled: "yes"
  scheduled: "yes"    
  log_healthy: "yes"
  params:
    - name: "status"
      value: "up"
    - name: "node:acme1.server.com|subnet:10.10.10.0|status"
      value: "up"
    - name: "node:acme2.server.com|subnet:10.10.10.0|status"
      value: "up"
  cron:
   when: "00 9 * * *"        
```

### Further reading

See the plugin configuration file `check_serviceguard_cluster_status.conf` for more explanation on the parameters and options.
