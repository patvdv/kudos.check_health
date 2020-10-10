## Plugin configuration

### Syntax

```yaml
hc_check_exadata_cell_luns:
  enabled: <yes|no>
  scheduled: <yes|no>
  log_healthy: <yes|no>
  dcli_user: <user>
  cell_servers: <list_of_servers>
  excluded_luns: <list_of_luns>
```

Default values (non-null):
* *enabled*: `yes`
* *scheduled*: `no`
* *log_healthy*: `no`
* *dcli_user*: `root`

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
hc_check_exadata_cell_luns:
  enabled: "yes"
  scheduled: "yes"
  log_healthy: "yes"
  cell_servers: "cell1,cell2,cell3"
```

### Further reading

See the plugin configuration file `hc_check_exadata_cell_luns.conf` for more explanation on the parameters and options.
