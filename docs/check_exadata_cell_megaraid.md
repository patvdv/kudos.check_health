## Plugin configuration

### Syntax

```yaml
hc_check_exadata_cell_megaraid:
  enabled: <yes|no>
  scheduled: <yes|no>
  log_healthy: <yes|no>
  dcli_user: <user>
  cell_servers: <list_of_servers>
  check_controller: <yes|no>
  check_bbu: <yes|no>
  check_supercap: <yes|no>
  check_physical: <yes|no>
  check_virtual: <yes|no>
  cell_exclude:
    - cell_server: <server>
      disable_check: <controller|bbu|supercap|physical|virtual>
```

Default values (non-null):
* *enabled*: `yes`
* *scheduled*: `no`
* *log_healthy*: `no`
* *dcli_user*: `root`
* *check_controller*: `yes`
* *check_bbu*: `yes`
* *check_supercap*: `yes`
* *check_physical*: `yes`
* *check_virtual*: `yes`

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
hc_check_exadata_cell_megaraid:
  enabled: "yes"
  scheduled: "yes"
  log_healthy: "yes"
  cell_servers: "cell1,cell2,cell3"
  check_controller: "no"
  check_bbu: "no"
  check_supercap: "no"
  check_physical: "yes"
  check_virtual: "yes"
  cell_exclude:
    - cell_server: "cell1"
      disable_check: "virtual"
    - cell_server: "cell2"
      disable_check: "virtual"      
```

### Further reading

See the plugin configuration file `hc_check_exadata_cell_megaraid.conf` for more explanation on the parameters and options.
