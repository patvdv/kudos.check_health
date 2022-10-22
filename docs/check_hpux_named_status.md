## Plugin configuration

### Syntax

```yaml
hc_check_hpux_named_status:
  installed: <yes|no>    
  enabled: <yes|no>
  scheduled: <yes|no>
```

Default values (non-null):
* *installed*: `no`
* *enabled*: `yes`
* *scheduled*: `no`

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
hc_check_hpux_named_status:
  enabled: "yes"
  scheduled: "yes"
```
