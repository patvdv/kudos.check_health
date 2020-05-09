## Plugin configuration

### Syntax

```yaml
hc_check_exadata_cell_physicaldisks:
  scheduled: <yes|no>
  log_healthy: <yes|no>
  dcli_user: <user>
  cell_servers: <list_of_servers>
  excluded_disks: <list_of_disks>
```

Default values (non-null):
* *scheduled*: `no`
* *log_healthy*: `no`
* *dcli_user*: `root`

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
hc_check_exadata_cell_physicaldisks:
  scheduled: "no"
  log_healthy: "no"
  check_host:
    active: "yes"
    title: "Cell physical disks"
  cell_servers: "cell1,cell2,cell3"
```

### Further reading

See the plugin configuration file `hc_check_exadata_cell_physicaldisks.conf` for more explanation on the parameters and options.
