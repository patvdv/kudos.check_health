## Plugin configuration

### Syntax

```yaml
hc_check_linux_hpssacli:
  scheduled: <yes|no>
  log_healthy: <yes|no>
  hpssacli_bin : <file_path>
  do_ssa_controller: <0|1>
  do_ssa_enclosure: <0|1>
  do_ssa_physical: <0|1>
  do_ssa_logical: <0|1>
```

Default values (non-null):
* *scheduled*: `no`
* *log_healthy*: `no`
* *hpssacli_bin*: `/usr/sbin/hpssacli`
* *do_ssa_controller*: `1`
* *do_ssa_enclosure*: `1`
* *do_ssa_physical*: `1`
* *do_ssa_logical*: `1`

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
hc_check_linux_hpssacli:
  scheduled: "yes"    
  log_healthy: "no"
  do_ssa_controller: 1
  do_ssa_enclosure: 1
  do_ssa_physical: 0
  do_ssa_logical: 0
```

### Further reading

See the plugin configuration file `check_linux_hpssacli.conf` for more explanation on the parameters and options.
