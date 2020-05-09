## Plugin configuration

### Syntax

```yaml
hc_check_linux_vz_ct_counters:
  scheduled: <yes|no>
  log_healthy: <yes|no>
  exclude_counters: <list_counters>
  ct:
    - <id1>
    - <id2>
```

Default values (non-null):
* *scheduled*: `no`
* *log_healthy*: `no`

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
hc_check_linux_vz_ct_counters:
  scheduled: "no"    
  log_healthy: "yes"
  check_host:
    active: "yes"
    config_file: "/data/myconfig.conf"
  exclude_counters: "numpty"
  ct:
    - 100
    - 101  
```

### Further reading

See the plugin configuration file `check_linux_vz_ct_counters.conf` for more explanation on the parameters and options.
