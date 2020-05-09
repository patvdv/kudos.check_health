## Plugin configuration

### Syntax

```yaml
hc_check_serviceguard_package_config:
  scheduled: <yes|no>
  log_healthy: <yes|no>
  packages:
    - name: <package>
      params:
        - <parameter1>: <value>
        - <parameter2>: <value>
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
hc_check_serviceguard_package_config:
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
