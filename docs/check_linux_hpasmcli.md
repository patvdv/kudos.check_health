## Plugin configuration

### Syntax

```yaml
hc_check_linux_hpasmcli:
  enabled: <yes|no>
  scheduled: <yes|no>
  log_healthy: <yes|no>
  hpasmcli_bin: <file_path>
  do_asm_fans: <0|1>
  do_asm_dimm: <0|1>
  do_asm_powersupply: <0|1>
  do_asm_server: <0|1>
  do_asm_temperature: <0|1>
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
* *hpasmcli_bin*: `/sbin/hpasmcli`
* *do_asm_fans*: `1`
* *do_asm_dimm*: `1`
* *do_asm_powersupply*: `1`
* *do_asm_server*: `1`
* *do_asm_temperature*: `1`
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
hc_check_linux_hpasmcli:
  enabled: "yes"
  scheduled: "yes"    
  log_healthy: "no"
  do_asm_fans: 0
  do_asm_dimm: 0
  do_asm_powersupply: 1
  do_asm_server: 1
  do_asm_temperature: 1  
```

### Further reading

See the plugin configuration file `check_linux_hpasmcli.conf` for more explanation on the parameters and options.
