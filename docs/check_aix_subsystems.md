## Plugin configuration

### Syntax

```yaml
hc_check_aix_subsystems:
  scheduled: <yes|no>
  log_healthy: <yes|no>
  subsys:
    - <entry1>
    - <entry2>
```

Default values (non-null):
* *scheduled*: `no`

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
hc_check_aix_subsystems:
  log_healthy: "yes"
  subsys:
    - nimsh
    - sshd
```

### Further reading

See the plugin configuration file `check_aix_subsystems.conf` for more explanation on the parameters and options.
