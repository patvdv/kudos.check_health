## Plugin configuration

### Syntax

```yaml
hc_check_hpux_fs_mounts_options:
  installed: <yes|no>    
  enabled: <yes|no>
  scheduled: <yes|no>
  log_healthy: <yes|no>
  ignore_missing_fs: <yes|no>
  fs:
    - name: <fs_name>
      options: <mount_options>
```

Default values (non-null):
* *installed*: `no`
* *enabled*: `yes`
* *scheduled*: `no`
* *log_healthy*: `no`
* *ignore_missing_fs*: `yes`

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
hc_check_hpux_fs_mounts_options:
  enabled: "yes"
  scheduled: "yes"    
  log_healthy: "yes"
  ignore_missing_fs: "no"
  fs:
    - name: "/var"
      options: "nosuid,nodev"
```

### Further reading

See the plugin configuration file `check_hpux_fs_mounts_options.conf` for more explanation on the parameters and options.
