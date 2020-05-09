## Plugin configuration

### Syntax

```yaml
hc_check_linux_file_change:
  scheduled: <yes|no>
  log_healthy: <yes|no>
  incl:
    - <entry1>
    - <entry2>
  excl:
    - <entry1>
    - <entry2>
```

Default values (non-null):
* *scheduled*: `no`
* *log_healthy*: `no`

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
hc_check_linux_file_change:
  scheduled: "no"    
  log_healthy: "yes"
  incl:
    - "/tmp/mydir1"
    - "/tmp/myfile1"
  excl:
    - "/tmp/mydir1/myfile1"  
```

### Further reading

See the plugin configuration file `check_linux_file_change.conf` for more explanation on the parameters and options.
