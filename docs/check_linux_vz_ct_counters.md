## Plugin configuration

### Syntax

```yaml
hc_check_linux_vz_ct_counters:
  installed: <yes|no>    
  enabled: <yes|no>
  scheduled: <yes|no>
  log_healthy: <yes|no>
  exclude_counters: <list_counters>
  ct:
    - <id1>
    - <id2>
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
hc_check_linux_vz_ct_counters:
  enabled: "yes"
  scheduled: "no"    
  log_healthy: "yes"
  check_host:
    active: "yes"
    config_file: "/data/myconfig.conf"
  exclude_counters: "numpty"
  ct:
    - 100
    - 101  
```

### Further reading

See the plugin configuration file `check_linux_vz_ct_counters.conf` for more explanation on the parameters and options.
