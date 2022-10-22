## Plugin configuration

### Syntax

```yaml
hc_check_linux_vz_ct_status:
  enabled: <yes|no>
  scheduled: <yes|no>
  log_healthy: <yes|no>
  exclude_counters: <list_counters>
  ct:
    - name: <id>
      runtime_status: <status>
      boot_status: <status>
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
hc_check_linux_vz_ct_status:
  enabled: "yes"
  scheduled: "no"    
  log_healthy: "yes"
  ct:
    - name: "0cc5e1a0-f986-43f8-a194-a19c077dee91"
      runtime_status: "running"
      boot_status: "on"
    - name: "621240e6-fa79-406a-a3f9-26de47b5d789"
      runtime_status: "stopped"
      boot_status: "off"
```

### Further reading

See the plugin configuration file `check_linux_vz_ct_status.conf` for more explanation on the parameters and options.
