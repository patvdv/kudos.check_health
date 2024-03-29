## Plugin configuration

### Syntax

```yaml
hc_check_linux_es_status:
  installed: <yes|no>    
  enabled: <yes|no>
  scheduled: <yes|no>
  log_healthy: <yes|no>
  es_url: <url>
  cron:
    when: <time_date_definition>
    user: <text>
    action: <text>
    no_lock: <yes|no>
    timeout: <number_seconds>
    options: <text>
```

Default values (non-null):
* *installed*: `no`
* *enabled*: `yes`
* *scheduled*: `no`
* *log_healthy*: `no`
* *es_url*: `http://localhost:9200`
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
hc_check_linux_es_status:
  enabled: "no"
  scheduled: "yes"    
  log_healthy: "yes"
  check_host:
    active: "yes"
    title: "Elasticsearch status"
```

### Further reading

See the plugin configuration file `check_linux_es_status.conf` for more explanation on the parameters and options.
