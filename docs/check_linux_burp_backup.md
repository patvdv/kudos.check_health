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
