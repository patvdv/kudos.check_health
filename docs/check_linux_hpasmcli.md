## Plugin configuration

### Syntax

```yaml
hc_check_linux_hpasmcli:
  scheduled: <yes|no>
  log_healthy: <yes|no>
  hpasmcli_bin: <file_path>
  do_asm_fans: <0|1>
  do_asm_dimm: <0|1>
  do_asm_powersupply: <0|1>
  do_asm_server: <0|1>
  do_asm_temperature: <0|1>
```

Default values (non-null):
* *scheduled*: `no`
* *log_healthy*: `no`
* *hpasmcli_bin*: `/sbin/hpasmcli`
* *do_asm_fans*: `1`
* *do_asm_dimm*: `1`
* *do_asm_powersupply*: `1`
* *do_asm_server*: `1`
* *do_asm_temperature*: `1`

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
hc_check_linux_hpasmcli:
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
