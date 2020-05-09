## Plugin configuration

### Syntax

```yaml
hc_check_hpux_drd_status:
  scheduled: <yes|no>
  log_healthy: <yes|no>
  check_clone: <yes|no>
  clone_age: <days>
  check_sync: <yes|no>
  sync_age: <days>
```

Default values (non-null):
* *scheduled*: `no`
* *log_healthy*: `no`
* *check_clone*: `yes`
* *clone_age*: `30`
* *check_sync*: `yes`
* *sync_age*: `30`

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
hc_check_hpux_drd_status:
  scheduled: "yes"    
  log_healthy: "yes"
  check_clone: "yes"
  clone_age: 15
  check_sync: "no"
  sync_age: 15
```

### Further reading

See the plugin configuration file `check_hpux_drd_status.conf` for more explanation on the parameters and options.