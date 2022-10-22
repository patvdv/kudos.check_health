## Plugin configuration

### Syntax

```yaml
hc_check_hpux_ntp_status:
  installed: <yes|no>    
  enabled: <yes|no>
  scheduled: <yes|no>
  log_healthy: <yes|no>
  max_offset: <millisecond>
  ntpq_use_ipv4: <yes|no>
```

Default values (non-null):
* *installed*: `no`
* *enabled*: `yes`
* *scheduled*: `no`
* *log_healthy*: `no`
* *max_offset*: `500`
* *ntpq_use_ipv4*: `yes`

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
hc_check_hpux_ntp_status:
  enabled: "yes"
  scheduled: "yes"    
  log_healthy: "yes"
  max_offset: 1000
```

### Further reading

See the plugin configuration file `check_hpux_ntp_status.conf` for more explanation on the parameters and options.
