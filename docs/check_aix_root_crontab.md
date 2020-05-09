## Plugin configuration

### Syntax

```yaml
hc_check_aix_root_crontab:
  scheduled: <yes|no>
  log_healthy: <yes|no>
  jobs:
    - <entry1>
    - <entry2>
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
hc_check_aix_root_crontab:
  scheduled: "no"
  log_healthy: "yes"
  jobs:
    - "/usr/bin/myjob1"
    - "/root/bin/myjob2"  
```

### Further reading

See the plugin configuration file `check_aix_root_crontab.conf` for more explanation on the parameters and options.
