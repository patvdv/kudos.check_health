## Plugin configuration

### Syntax

```yaml
hc_check_aix_sysbackup:
  enabled: <yes|no>
  log_healthy: <yes|no>
  backup_path: <dir_path>
  mksysb_log: <file_path>
  backup_age: <days>
```

Default values (non-null):
* *enabled*: `yes`
* *scheduled*: `no`
* *log_healthy*: `no`
* *backup_path*: `mksysb.log`
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
hc_check_aix_sysbackup:
  enabled: "yes"
  log_healthy: "yes"
  backup_path: "/export/images"
  mksysb_log: "mksysb.log"
  backup_age: 14
```

### Further reading

See the plugin configuration file `check_aix_sysbackup.conf` for more explanation on the parameters and options.
