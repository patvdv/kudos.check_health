## Plugin configuration

### Syntax

```yaml
hc_check_exadata_zfs_share_replication:
  enabled: <yes|no>
  scheduled: <yes|no>
  log_healthy: <yes|no>
  ssh_user: <user>
  ssh_key_file: <ssh_private_key_file>
  ssh_opts: <ssh_options>
  max_replication_lag: 300
  hosts:
    - name: <server>
      shares:
        - name: <share>
          replicated: <true|false>
          state: <success|failed>
          max_replication_lag: 900
          days: <day_specification>
          hours: <hours_specification>
```

Default values (non-null):
* *enabled*: `yes`
* *scheduled*: `no`
* *log_healthy*: `no`
* *ssh_user*: `root`
* *ssh_key_file*: `~root/.ssh/id_rsa`
* *max_replication_lag*: `300` (only general threshold)

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
hc_check_exadata_zfs_share_replication:
  enabled: "yes"
  scheduled: "yes"
  log_healthy: "yes"
  hosts:
    - name: "zfs1.acme.com"
      shares:
        - name: "share1"
          replicated: true
          state: "success"
          max_replication_lag: 900
          days: "*"
          hours: "09-12"
        - name: "share2"
          replicated: true
          state: "failed"
          max_replication_lag: 0
          days: "mon,tue"
    - name: "zfs2.acme.com"
      shares:
        - name: "share2"
          replicated: false
```

### Further reading

See the plugin configuration file `check_exadata_zfs_share_replication.conf` for more explanation on the parameters and options.
