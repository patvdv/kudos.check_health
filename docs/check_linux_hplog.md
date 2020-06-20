## Plugin configuration

### Syntax

```yaml
hc_check_linux_hplog:
  enabled: <yes|no>
  scheduled: <yes|no>
  log_healthy: <yes|no>
  hplog_bin: <file_path>
  hplog_severities: <list_severities>
```

Default values (non-null):
* *enabled*: `yes`
* *scheduled*: `no`
* *log_healthy*: `no`
* *hplog_bin*: `/sbin/hplog`
* *hplog_severities*: `CRITICAL,CAUTION`

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
hc_check_linux_hplog:
  enabled: "yes"
  scheduled: "yes"    
  log_healthy: "no"
  hplog_severities*: "CRITICAL"
```

### Further reading

See the plugin configuration file `check_linux_hplog.conf` for more explanation on the parameters and options.
