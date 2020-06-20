## Plugin configuration

### Syntax

```yaml
hc_check_linux_mysqld_status:
  enabled: <yes|no>
  scheduled: <yes|no>
  log_healthy: <yes|no>
  do_check: <yes|no>
  check_type: <type>
  check_databases: <list_databases>
  exclude_databases: <list_databases>
  exclude_tables: <list_tables>
  do_stats: <yes|no>
  mysql_user: <user>
  mysql_password: <password>
  mysql_host: <server>
  mysql_port: <port>
```

Default values (non-null):
* *enabled*: `yes`
* *scheduled*: `no`
* *log_healthy*: `no`
* *do_check*: `yes`
* *check_type*: `quick`
* *do_stats*: `yes`
* *mysql_user*: `root`
* *mysql_host*: `localhost`
* *mysql_port*: `3306`

Setting the option *scheduled=yes* will result in the corresponding **cron** bundle to be installed (if available).

Setting the option *enabled=no* will disable the health check and will emulate a monitoring blackout or maintenance.

Use Ansible vault to the set the `mysql_password` value!

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
hc_check_linux_mysqld_status:
  enabled: "yes"
  scheduled: "yes"    
  log_healthy: "yes"
  check_type: "quick"
  mysql_user: "monitor"
```

### Further reading

See the plugin configuration file `check_linux_mysqld_status.conf` for more explanation on the parameters and options.
