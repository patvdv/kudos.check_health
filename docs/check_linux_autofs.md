## Plugin configuration

### Syntax

```yaml
hc_check_linux_autofs:
  scheduled: <yes|no>
  log_healthy: <yes|no>
  fix_autofs: <yes|no>
  retry_start: <number_tries>
  sleep_time: <sumber_seconds>
```

Default values (non-null):
* *scheduled*: `no`
* *log_healthy*: `no`
* *fix_autofs*: `no`
* *retry_start*: `3`
* *sleep_time*: `5`

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
hc_check_linux_autofs:
  scheduled: "yes"    
  log_healthy: "yes"
  fix_autofs: "yes"
  retry_start: 5
```

### Further reading

See the plugin configuration file `check_linux_autofs.conf` for more explanation on the parameters and options.