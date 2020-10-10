## Plugin configuration

### Syntax

```yaml
hc_check_hpux_kernel_params:
  enabled: <yes|no>
  scheduled: <yes|no>
  log_healthy: <yes|no>
  params:
    - name: <parameter_name>
      value: <parameter_value>
```

Default values (non-null):
* *enabled*: `yes`
* *scheduled*: `no`
* *log_healthy*: `no`

Setting the option *scheduled=yes* will result in the corresponding **cron** bundle to be installed (if available).

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
hc_check_hpux_kernel_params:
  enabled: "yes"
  scheduled: "yes"    
  log_healthy: "yes"
  params:
    - name: "nproc"
      value: 5000
    - name: "max_files"
      value: 4096
```

### Further reading

See the plugin configuration file `check_hpux_kernel_params.conf` for more explanation on the parameters and options.
