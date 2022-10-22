## Plugin configuration

### Syntax

```yaml
hc_check_hpux_ignite_backup:
  installed: <yes|no>    
  enabled: <yes|no>
  scheduled: <yes|no>
  log_healthy: <yes|no>
  backup_age: <days>
  exclude_hosts: <server_list>
```

Default values (non-null):
* *installed*: `no`
* *enabled*: `yes`
* *scheduled*: `no`
* *log_healthy*: `no`
* *backup_age:* `14`

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
hc_check_hpux_ignite_backup:
  enabled: "yes"
  scheduled: "yes"    
  log_healthy: "yes"
  backup_age: 30
  exclude_hosts: "hpux1.acme.com,hpux2.acme.com"
```

### Further reading

See the plugin configuration file `check_hpux_ignite_backup.conf` for more explanation on the parameters and options.
