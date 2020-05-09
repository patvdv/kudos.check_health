## Plugin configuration

### Syntax

```yaml
hc_check_linux_process_limits:
  scheduled: <yes|no>
  log_healthy: <yes|no>
  limits:
    - user:
      name: <limit_name>
      values:
        - soft: <threshold>
        - hard: <threshold>
    - process:
      name: <limit_name>
      values:
        - soft: <threshold>
        - hard: <threshold>        
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
hc_check_linux_process_limits:
  log_healthy: "yes"
  limits:
    - user: root
      name: "Max open files"
      values:
        soft: 75
        hard: 90
    - process: postfix
      name: "Max open files"
      values:
        soft: 70
        hard: 80  
```

### Further reading

See the plugin configuration file `check_linux_process_limits.conf` for more explanation on the parameters and options.
