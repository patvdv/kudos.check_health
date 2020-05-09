## Plugin configuration

### Syntax

```yaml
hc_check_hpux_kernel_usage:
  scheduled: <yes|no>
  log_healthy: <yes|no>
  max_kcusage: <threshold>
  exclude_params: <exclude_list>
  params:
    - name: <parameter_name>
      value: <parameter_value>
```

Default values (non-null):
* *scheduled*: `no`
* *log_healthy*: `no`
* *max_kcusage*: `90`

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
hc_check_hpux_kernel_usage:
  scheduled: "yes"    
  log_healthy: "yes"
  max_kcusage: 95
  exclude_params: "max_files"
  params:
    - name: "nproc"
      value: 85
```

### Further reading

See the plugin configuration file `check_hpux_kernel_usage.conf` for more explanation on the parameters and options.