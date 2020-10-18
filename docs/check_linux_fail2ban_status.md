## Plugin configuration

### Syntax

```yaml
hc_check_linux_fail2ban_status:
  enabled: <yes|no>
  scheduled: <yes|no>
  log_healthy: <yes|no>
  check_type: <type>
  check_jails:
    - <jail1>
    - <jail2>
```

Default values (non-null):
* *enabled*: `yes`
* *scheduled*: `no`
* *log_healthy*: `no`
* *check_type*: `auto`

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
hc_check_linux_fail2ban_status:
  enabled: "no"
  scheduled: "yes"    
  log_healthy: "yes"
  check_type: "auto"
  check_jails:
    - "sshd"
    - "apache"
```

### Further reading

See the plugin configuration file `check_linux_fail2ban_status.conf` for more explanation on the parameters and options.
