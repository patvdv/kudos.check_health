## Plugin configuration

### Syntax

```yaml
hc_check_exadata_megaraid:
  installed: <yes|no>    
  enabled: <yes|no>
  scheduled: <yes|no>
  log_healthy: <yes|no>
  check_controller: <yes|no>
  check_bbu: <yes|no>
  check_supercap: <yes|no>
  check_physical: <yes|no>
  check_virtual: <yes|no>
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
* *check_controller*: `yes`
* *check_bbu*: `yes`
* *check_supercap*: `yes`
* *check_physical*: `yes`
* *check_virtual*: `yes`
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
hc_check_exadata_megaraid:
  enabled: "yes"
  scheduled: "no"
  log_healthy: "yes"
  check_controller: "yes"
  check_bbu: "yes"
  check_supercap: "yes"
  check_physical: "no"
  check_virtual: "no"
  cron:
    when: "02 * * * 1-5"
    no_lock: "yes"
```

### Further reading

See the plugin configuration file `hc_check_exadata_megaraid.conf` for more explanation on the parameters and options.
