## Plugin configuration

### Syntax

```yaml
hc_check_hpux_patch_version:
  installed: <yes|no>    
  enabled: <yes|no>
  scheduled: <yes|no>
  log_healthy: <yes|no>
  required_oe: <version>
  required_patches: <list_patches>
  check_filesets: <list_filesets>
  exclude_filesets: <list_filesets>
```

Default values (non-null):
* *installed*: `no`
* *enabled*: `yes`
* *scheduled*: `no`
* *log_healthy*: `no`
* *check_filesets*: `yes`
* *exclude_filesets*: `yes`

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
hc_check_hpux_patch_version:
  enabled: "yes"
  scheduled: "yes"    
  log_healthy: "no"
  required_oe: "B.11.31.19.05"
  required_patches: "PHKL_44399"
  check_filesets: "yes"
```

### Further reading

See the plugin configuration file `check_hpux_patch_version.conf` for more explanation on the parameters and options.
