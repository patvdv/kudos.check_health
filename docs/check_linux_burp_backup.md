## Plugin configuration

### Syntax

```yaml
hc_check_linux_burp_backup:
  enabled: <yes|no>
  scheduled: <yes|no>
  log_healthy: <yes|no>
  client:
   - name: <client>
     max_warnings_allowed: <count>
     max_backup_age: <age_string>
```

Default values (non-null):
* *enabled*: `yes`
* *scheduled*: `no`
* *log_healthy*: `no`

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
hc_check_linux_burp_backup:
  enabled: "yes"
  scheduled: "no"
  log_healthy: "yes"
  client:
    - name: "client1.acme.com"
      max_warnings_allowed: 3
      max_backup_age: "3d"
    - name: "client2.acme.com"
      max_warnings_allowed: 0
      max_backup_age: "10d"
```

### Further reading

See the plugin configuration file `check_linux_burp_backup.conf` for more explanation on the parameters and options.
