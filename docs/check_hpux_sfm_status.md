## Plugin configuration

### Syntax

```yaml
hc_check_hpux_sfm_status:
  scheduled: <yes|no>
  log_healthy: <yes|no>
  check_events: <yes|no>
  events_age: <day_string>
  events_security: <list_severities>
  send_test_event: <yes|no>
  wait_test_event: <seconds>
  event_subscriber_wbem: <url>
  event_subscriber_cimom: <url>
```

Default values (non-null):
* *scheduled*: `no`
* *log_healthy*: `no`
* *events_events*: `yes`
* *events_age*: `1:dd`
* *events_security*: `CRITICAL`
* *send_test_event*: `no`
* *wait_test_event*: 60

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
hc_check_hpux_sfm_status:
  scheduled: "yes"    
  log_healthy: "yes"
  events_age: "'3:dd"
  events_security: "CRITICAL,ERROR"
  send_test_event: "no"
```

### Further reading

See the plugin configuration file `check_hpux_sfm_status.conf` for more explanation on the parameters and options.
