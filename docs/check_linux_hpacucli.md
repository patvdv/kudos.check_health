## Plugin configuration

### Syntax

```yaml
hc_check_linux_hpacucli:
  scheduled: <yes|no>
  log_healthy: <yes|no>
  hpacucli_bin: <file_path>
  do_acu_controller: <0|1>
  do_acu_enclosure: <0|1>
  do_acu_physical: <0|1>
  do_acu_logical: <0|1>
```

Default values (non-null):
* *scheduled*: `no`
* *log_healthy*: `no`
* *hpacucli_bin*: `/usr/sbin/hpacucli`
* *do_acu_controller*: `1`
* *do_acu_enclosure*: `1`
* *do_acu_physical*: `1`
* *do_acu_logical*: `1`

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
hc_check_linux_hpacucli:
  scheduled: "yes"    
  log_healthy: "yes"
  do_acu_controller: 0
  do_acu_enclosure: 0
  do_acu_physical: 1
  do_acu_logical: 1
```

### Further reading

See the plugin configuration file `check_linux_hpacucli.conf` for more explanation on the parameters and options.
