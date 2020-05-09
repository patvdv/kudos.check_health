## Plugin configuration

### Syntax

```yaml
hc_check_aix_fs_mounts:
  scheduled: <yes|no>
```

Default values (non-null):
* *scheduled*: `no`

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
hc_check_aix_fs_mounts:
  scheduled: "yes"
```
