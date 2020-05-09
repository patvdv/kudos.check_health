## Plugin configuration

### Syntax

```yaml
hc_check_hpux_ioscan:
  scheduled: <yes|no>
  log_healthy: <yes|no>
  ioscan_classes: <list_classes>
  kernel_mode: <yes|no>
  agile_view: <yes|no>
```

Default values (non-null):
* *scheduled*: `no`
* *log_healthy*: `no`
* *ioscan_classes:* `ctl,diag,disk,ext_bus,fc,fcp,i2o,ipmi,lan,lvm,olar,vxvm`
* *kernel_mode*: `yes`
* *agile_view*: `yes`

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
hc_check_hpux_ioscan:
  scheduled: "no"
  log_healthy: "no"
  check_host:
    active: "yes"
    timeout: 300
  kernel_mode: "no"
  agile_view: "yes"
```

### Further reading

See the plugin configuration file `check_hpux_ioscan.conf` for more explanation on the parameters and options.
