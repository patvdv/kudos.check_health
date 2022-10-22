## Plugin configuration

### Syntax

```yaml
hc_check_linux_autofs:
  installed: <yes|no>    
  enabled: <yes|no>
  scheduled: <yes|no>
  log_healthy: <yes|no>
  fix_autofs: <yes|no>
  retry_start: <number_tries>
  sleep_time: <number_seconds>
  cron:
    when: <time_date_definition>
    user: <text>
    action: <text>
    no_lock: <yes|no>
    timeout: <number_seconds>
    options: <text>
```

Default values (non-null):
* *installed*: `no`
* *enabled*: `yes`
* *scheduled*: `no`
* *log_healthy*: `no`
* *fix_autofs*: `no`
* *retry_start*: `3`
* *sleep_time*: `5`
* *cron/when*: `00 * * * *`
* *cron/user*: `root`
* *cron/action*: `--run`
* *cron/no_lock*: `no`

Setting the option *scheduled=yes* will result in the corresponding **cron** file to be created.

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
hc_check_linux_autofs:
  enabled: "yes"
  scheduled: "yes"    
  log_healthy: "yes"
  fix_autofs: "yes"
  retry_start: 5
  cron:
    when: "27 * * * *"
    options: "--notify=mail --mail-to=monitoring@acme.com --no-lock >/dev/null 2>/dev/null"
```

### Further reading

See the plugin configuration file `check_linux_autofs.conf` for more explanation on the parameters and options.
