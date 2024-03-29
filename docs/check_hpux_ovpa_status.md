## Plugin configuration

### Syntax

```yaml
hc_check_hpux_ovpa_status:
  installed: <yes|no>    
  enabled: <yes|no>
  scheduled: <yes|no>
  log_healthy: <yes|no>
  ovpa_deamons: <list_daemons>
```

Default values (non-null):
* *installed*: `no`
* *enabled*: `yes`
* *scheduled*: `no`
* *log_healthy*: `no`
* *ovpa_daemons:* `oacore,midaemon,perfalarm,ttd,ovcd,ovbbccb,perfd`

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
hc_check_hpux_ovpa_status:
  enabled: "yes"
  scheduled: "yes"    
  log_healthy: "no"
```

### Further reading

See the plugin configuration file `check_hpux_ovpa_status.conf` for more explanation on the parameters and options.
