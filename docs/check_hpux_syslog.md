## Plugin configuration

### Syntax

```yaml
hc_check_hpux_syslog:
  installed: <yes|no>    
  enabled: <yes|no>
  scheduled: <yes|no>
  log_healthy: <yes|no>
  syslog_file: <file_path>
  syslog_classes: <list_classes>
```

Default values (non-null):
* *installed*: `no`
* *enabled*: `yes`
* *scheduled*: `no`
* *log_healthy*: `no`
* *syslog_file*: `/var/adm/syslog/syslog.log`
* *syslog_classes*: `vmunix`

Setting the option *scheduled=yes* will result in the corresponding **cron** bundle to be installed (if available).

Setting the option *enabled=no* will disable the health check and will emulate a monitoring blackout or maintenance

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
hc_check_hpux_syslog:
  enabled: "yes"
  scheduled: "yes"    
  log_healthy: "yes"
  syslog_classes: "vmunix,mountd"
```

### Further reading

See the plugin configuration file `check_hpux_syslog.conf` for more explanation on the parameters and options.
