## Plugin configuration

### Syntax

```yaml
hc_check_aix_subsystems:
  installed: <yes|no>    
  enabled: <yes|no>
  scheduled: <yes|no>
  log_healthy: <yes|no>
  subsys:
    - <entry1>
    - <entry2>
```

Default values (non-null):
* *installed*: `no`
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
hc_check_aix_subsystems:
  log_healthy: "yes"
  subsys:
    - nimsh
    - sshd
  cron:
    when: "27 * * * *"
    no_lock: "yes"    
```

### Further reading

See the plugin configuration file `check_aix_subsystems.conf` for more explanation on the parameters and options.
