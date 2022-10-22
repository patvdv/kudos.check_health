## Plugin configuration

### Syntax

```yaml
hc_check_hpux_root_crontab:
  installed: <yes|no>    
  enabled: <yes|no>
  scheduled: <yes|no>
  log_healthy: <yes|no>
  jobs:
    - <entry1>
    - <entry2>
```

Default values (non-null):
* *installed*: `no`
* *enabled*: `yes`
* *scheduled*: `no`
* *log_healthy*: `no`

Setting the option *scheduled=yes* will result in the corresponding **cron** bundle to be installed (if available).

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
hc_check_hpux_root_crontab:
  enabled: "yes"
  scheduled: "no"
  log_healthy: "yes"
  jobs:
    - "/usr/bin/myjob1"
    - "/root/bin/myjob2"  
```

### Further reading

See the plugin configuration file `check_hpux_root_crontab.conf` for more explanation on the parameters and options.
