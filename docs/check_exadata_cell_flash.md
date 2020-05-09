## Plugin configuration

### Syntax

```yaml
hc_check_exadata_cell_flash:
  scheduled: <yes|no>
  log_healthy: <yes|no>
  dcli_user: <user>
  cell_servers: <list_of_servers>
  excluded_devices: <list_of_devices>
  check_flashcache: <yes|no>
  check_flashlog: <yes|no>
```

Default values (non-null):
* *scheduled*: `no`
* *log_healthy*: `no`
* *dcli_user*: `root`
* *check_flashcache*: `yes`
* *check_flashlog*: `yes`

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
hc_check_exadata_cell_flash:
  scheduled: "yes"
  log_healthy: "yes"
  cell_servers: "cell1,cell2,cell3"
  check_flashlog: "no"
```

### Further reading

See the plugin configuration file `check_exadata_cell_flash.conf` for more explanation on the parameters and options.
