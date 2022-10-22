## Plugin configuration

### Syntax

```yaml
hc_check_serviceguard_package_config:
  enabled: <yes|no>
  scheduled: <yes|no>
  log_healthy: <yes|no>
  packages:
    - name: <package>
      params:
        - <parameter1>: <value>
        - <parameter2>: <value>
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
hc_check_serviceguard_package_config:
  enabled: "yes"
  scheduled: "yes"    
  log_healthy: "yes"
  packages:
    - name: "mypkg1"
      params:
        - ip_subnet: "10.10.10.0"
        - ip_address: "10.10.10.21"
        - vg: "/dev/vgdata1"
        - fs_name: "/dev/vgdata1/lvol1"
        - fs_directory: "/data1"
    - name: "mypkg2"
      params:
        - ip_subnet: "10.10.10.0"
        - ip_address: "10.10.10.22"
        - vg: "/dev/vgdata2"
        - fs_name: "/dev/vgdata2/lvol1"
        - fs_directory: "/data2"
```

### Further reading

See the plugin configuration file `check_serviceguard_package_config.conf` for more explanation on the parameters and options.
