## Plugin configuration

### Syntax

```yaml
hc_check_linux_file_change:
  enabled: <yes|no>
  scheduled: <yes|no>
  log_healthy: <yes|no>
  incl:
    - <entry1>
    - <entry2>
  excl:
    - <entry1>
    - <entry2>
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
hc_check_linux_file_change:
  enabled: "yes"
  scheduled: "no"    
  log_healthy: "yes"
  incl:
    - "/tmp/mydir1"
    - "/tmp/myfile1"
  excl:
    - "/tmp/mydir1/myfile1"
  cron:
    when: "00 00 * * *"
    timeout: 3600  
```

### Further reading

See the plugin configuration file `check_linux_file_change.conf` for more explanation on the parameters and options.
