## Plugin configuration

### Syntax

```yaml
hc_check_clusterware_resource_config:
  scheduled: <yes|no>
  crsctl_bin: <file_path>
  resources:
    - name: <resource>
      params:
        - <PARAMATER1>: <value>
        - <PARAMETER2>: <value>
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
hc_check_clusterware_resource_config:
  scheduled: "no"
  log_healthy: "yes"
  check_host:
    active: "yes"
    title: "CRS resources?"
  resources:
    - name: "resource1"
      params:
        - TYPE: "cluster_resource"
        - ACL: "ACL=owner:root:rwx,pgrp:root:r-x,other::r--,user:oracle:r-x"
```

### Further reading

See the plugin configuration file `check_clusterware_resource_config.conf` for more explanation on the parameters and options.
