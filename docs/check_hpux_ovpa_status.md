## Plugin configuration

### Syntax

```yaml
hc_check_hpux_ovpa_status:
  scheduled: <yes|no>
  log_healthy: <yes|no>
  ovpa_deamons: <list_daemons>
```

Default values (non-null):
* *scheduled*: `no`
* *log_healthy*: `no`
* *ovpa_deamons:* `oacore,midaemon,perfalarm,ttd,ovcd,ovbbccb,perfd`

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
hc_check_hpux_ovpa_status:
  scheduled: "yes"    
  log_healthy: "no"
```

### Further reading

See the plugin configuration file `check_hpux_ovpa_status.conf` for more explanation on the parameters and options.
