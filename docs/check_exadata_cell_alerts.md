## Plugin configuration

### Syntax

```yaml
hc_check_exadata_cell_alerts:
  scheduled: <yes|no>
  log_healthy: <yes|no>
  dcli_user: <user>
  cell_servers: <list_of_servers>
  alert_severities: <list_of_severities>
```

Default values (non-null):
* *scheduled*: `no`
* *log_healthy*: `no`
* *dcli_user*: `root`
* *alert_severities*: `critical`

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
hc_check_exadata_cell_alerts:
  scheduled: "no"
  log_healthy: "yes"
  cell_servers: "cell1,cell2,cell3"
  alert_severities: "critical,major"
```

### Further reading

See the plugin configuration file `hc_check_exadata_cell_alerts.conf` for more explanation on the parameters and options.
