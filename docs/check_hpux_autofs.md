## Plugin configuration

### Syntax

```yaml
hc_check_hpux_autofs:
  installed: <yes|no>    
  enabled: <yes|no>
  scheduled: <yes|no>
  log_healthy: <yes|no>
  fix_autofs: <yes|no>
  retry_start: <number_tries>
  sleep_time: <sumber_seconds>
```

Default values (non-null):
* *installed*: `no`
* *enabled*: `yes`
* *scheduled*: `no`
* *log_healthy*: `no`
* *fix_autofs*: `no`
* *retry_start*: `3`
* *sleep_time*: `5`

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
hc_check_hpux_autofs:
  enabled: "yes"
  scheduled: "yes"    
  log_healthy: "yes"
  fix_autofs: "yes"
  retry_start: 5
```

### Further reading

See the plugin configuration file `check_hpux_autofs.conf` for more explanation on the parameters and options.
