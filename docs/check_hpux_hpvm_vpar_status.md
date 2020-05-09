## Plugin configuration

### Syntax

```yaml
hc_check_hpux_hpvm_vpar_status:
  scheduled: <yes|no>
  log_healthy: <yes|no>
  vpar:
    - name: <vpar_name>
      runtime_status: <on|off>
      boot_status: <auto|manual>
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
hc_check_hpux_hpvm_vpar_status:
  scheduled: "yes"    
  log_healthy: "yes"
  vpar:
    - name: "vpar1"
      runtime_status: "off"
      boot_status: "off"
```

### Further reading

See the plugin configuration file `check_hpux_hpvm_vpar_status.conf` for more explanation on the parameters and options.
