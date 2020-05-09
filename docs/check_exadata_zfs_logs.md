## Plugin configuration

### Syntax

```yaml
hc_check_exadata_zfs_logs:
  scheduled: <yes|no>
  log_healthy: <yes|no>
  ssh_user: <user>
  ssh_key_file: <ssh_private_key_file>
  ssh_opts: <ssh_options>
  hosts:
    - name: <server>
      alert: <log_levels>
      fltlog: <log_levels>      
      audit: <log_levels>
      scrk: <log_levels>
      system: <log_levels>
```

Default values (non-null):
* *scheduled*: `no`
* *log_healthy*: `no`
* *ssh_user*: `root`
* *ssh_key_file*: `~root/.ssh/id_rsa`
* `log_levels`: `critical`

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
hc_check_exadata_zfs_logs:
  log_healthy: "yes"
  hosts:
    - name: "zfs1.acme.com"
      audit: "major,critical"
      fltlog: "critical"
    - name: "zfs2.acme.com"
      alert: "major"
      fltlog: "critical"
```

### Further reading

See the plugin configuration file `check_exadata_zfs_logs.conf` for more explanation on the parameters and options.
