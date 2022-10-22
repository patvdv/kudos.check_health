## Plugin configuration

### Syntax

```yaml
hc_check_linux_ntp_status:
  enabled: <yes|no>
  scheduled: <yes|no>
  log_healthy: <yes|no>
  force_chrony: <yes|no>
  force_ntp: <yes|no>
  force_systemd: <yes|no>
  max_offset: <millisecond>
  ntpq_use_ipv4: <yes|no>
  cron:
    when: <time_date_definition>
    user: <text>
    action: <text>
    no_lock: <yes|no>
    timeout: <number_seconds>
    options: <text>  
```

Default values (non-null):
* *enabled*: `yes`
* *scheduled*: `no`
* *log_healthy*: `no`
* *max_offset*: `500`
* *force_chrony*: `no`
* *force_ntp*: `no`
* *force_systemd*: `no`
* *ntpq_use_ipv4*: `yes`
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
hc_check_linux_ntp_status:
  enabled: "yes"
  scheduled: "yes"    
  log_healthy: "yes"
  force_ntp: "yes"
  max_offset: 1000
  ntpq_use_ipv4: "yes"
  cron:
    when: "05 1 * * *"  
```

### Further reading

See the plugin configuration file `check_linux_ntp_status.conf` for more explanation on the parameters and options.
