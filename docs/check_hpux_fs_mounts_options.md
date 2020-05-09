## Plugin configuration

### Syntax

```yaml
hc_check_hpux_fs_mounts_options:
  scheduled: <yes|no>
  log_healthy: <yes|no>
  ignore_missing_fs: <yes|no>
  fs:
    - name: <fs_name>
      options: <mount_options>
```

Default values (non-null):
* *scheduled*: `no`
* *log_healthy*: `no`
* *ignore_missing_fs*: `yes`

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
hc_check_hpux_fs_mounts_options:
  scheduled: "yes"    
  log_healthy: "yes"
  ignore_missing_fs: "no"
  fs:
    - name: "/var"
      options: "nosuid,nodev"
```

### Further reading

See the plugin configuration file `check_hpux_fs_mounts_options.conf` for more explanation on the parameters and options.
