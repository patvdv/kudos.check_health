## Plugin configuration

### Syntax

```yaml
hc_check_serviceguard_package_status:
  enabled: <yes|no>
  scheduled: <yes|no>
  log_healthy: <yes|no>
  packages:
      - name: <package>
        params:
          - name: <name>
            value: <value>
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
hc_check_serviceguard_package_status:
  enabled: "yes"
  scheduled: "yes"    
  log_healthy: "yes"
  packages:
    - name: "mypkg1"
      params:
        - name: "status"
          value: "up"
        - name: "autorun"
          value: "enabled"
    - name: "mypkg2"
      params:
        - name: "status"
          value: "down"
        - name: "autorun"
          value: "disabled"
```

### Further reading

See the plugin configuration file `check_serviceguard_package_status.conf` for more explanation on the parameters and options.
