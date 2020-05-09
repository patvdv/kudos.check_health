## Plugin configuration

### Syntax

```yaml
hc_check_hpux_syslog:
  scheduled: <yes|no>
  log_healthy: <yes|no>
  syslog_file: <file_path>
  syslog_classes: <list_classes>
```

Default values (non-null):
* *scheduled*: `no`
* *log_healthy*: `no`
* *syslog_file*: `/var/adm/syslog/syslog.log`
* *syslog_classes*: `vmunix`

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
hc_check_hpux_syslog:
  scheduled: "yes"    
  log_healthy: "yes"
  syslog_classes: "vmunix,mountd"
```

### Further reading

See the plugin configuration file `check_hpux_syslog.conf` for more explanation on the parameters and options.
