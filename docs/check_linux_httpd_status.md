## Plugin configuration

### Syntax

```yaml
hc_check_linux_httpd_status:
  scheduled: <yes|no>
  log_healthy: <yes|no>
  check_type: <type>
  httpd_bin: <file_name>
  httpd_path: <file_path>
```

Default values (non-null):
* *scheduled*: `no`
* *log_healthy*: `no`
* *check_type*: `auto`

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
hc_check_linux_httpd_status:
  scheduled: "yes"    
  log_healthy: "yes"
  check_type: "systemd"
```

### Further reading

See the plugin configuration file `check_linux_httpd_status.conf` for more explanation on the parameters and options.
