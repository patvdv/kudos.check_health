## Plugin configuration

### Syntax

```yaml
hc_check_clusterware_resource_status:
  enabled: <yes|no>
  scheduled: <yes|no>
  log_healthy: <yes|no>
  crsctl_bin: <file_path>
  resources:
    - name: <resource>
      state: <state_definition>
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
hc_check_clusterware_resource_status:
  scheduled: "no"
  log_healthy: "yes"
  resources:
    - name: "resource1"
      state: "crs1.acme.com=ONLINE,crs2.acme.com=OFFLINE"
    - name: "resource2"
      state: "crs1.acme.com=ONLINE,crs2.acme.com=ONLINE"
    - name: "resource3"
      state: "*=ONLINE"
```

### Further reading

See the plugin configuration file `check_clusterware_resource_status.conf` for more explanation on the parameters and options.
