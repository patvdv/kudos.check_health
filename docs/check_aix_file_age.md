## Plugin configuration

### Syntax

```yaml
hc_check_aix_file_age:
  enabled: <yes|no>
  scheduled: <yes|no>
  log_healthy: <yes|no>
  file:
    - name: <file_name>
      max_age: <max_age>
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
hc_check_aix_file_age:
  enabled: "yes"
  scheduled: "no"
  log_healthy: "yes"
  check_host:
    active: "yes"
    title: "Check file age"
  file:
    - name: "/tmp/myfile1"
      max_age: 90
    - name: "/tmp/myfile2"
      max_age: 30
```

### Further reading

See the plugin configuration file `check_aix_file_age.conf` for more explanation on the parameters and options.
