## Plugin configuration

### Syntax

```yaml
hc_check_linux_fs_usage:
  installed: <yes|no>    
  enabled: <yes|no>
  scheduled: <yes|no>
  log_healthy: <yes|no>
  check_inodes_usage: <yes|no>
  max_inodes_usage: <threshold>
  check_space_usage: <yes|no>
  max_space_usage: <threshold>
  fs:
    - name: <fs_name>
      max_inodes_usage: <threshold>
      max_space_usage: <threshold>
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
* *check_inodes_usage*: `yes`
* *max_inodes_usage*: `90` (only general threshold)
* *check_space_usage*: `yes`
* *max_space_usage*: `90` (only general threshold)
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
hc_check_linux_fs_usage:
  enabled: "yes"
  scheduled: "yes"    
  log_healthy: "yes"
  check_host:
    active: "yes"
  fs:
    - name: "/usr"
      max_inodes_usage: 80
      max_space_usage: 95
    - name: "/var"
      max_inodes_usage: 92
      max_space_usage: 95
```

### Further reading

See the plugin configuration file `check_linux_fs_usage.conf` for more explanation on the parameters and options.
