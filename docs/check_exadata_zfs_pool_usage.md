## Plugin configuration

### Syntax

```yaml
hc_check_exadata_zfs_pool_usage:
  enabled: <yes|no>
  scheduled: <yes|no>
  log_healthy: <yes|no>
  ssh_user: <user>
  ssh_key_file: <ssh_private_key_file>
  ssh_opts: <ssh_options>
  max_space_usage: <threshold>
  hosts:
    - name: <server>
      pools:
        - name: <pool>
          max_space_usage: <threshold>
```

Default values (non-null):
* *enabled*: `yes`
* *scheduled*: `no`
* *log_healthy*: `no`
* *ssh_user*: `root`
* *ssh_key_file*: `~root/.ssh/id_rsa`
* *max_space_usage*: `90` (only general threshold)

Setting the option *scheduled=yes* will result in the corresponding **cron** bundle to be installed (if available).

Setting the option *enabled=no* will disable the health check and will emulate a monitoring blackout or maintenance

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
hc_check_exadata_zfs_pool_usage:
  enabled: "yes"
  log_healthy: "yes"
  max_space_usage: 75
  hosts:
    - name: "zfs1.acme.com"
      pools:
        - name: "pool_01"
          max_space_usage: 50
        - name: "pool_02"
          max_space_usage: 50
    - name: "zfs2.acme.com"
      pools:
        - name: "*"
          max_space_usage: 90
```

### Further reading

See the plugin configuration file `check_exadata_zfs_pool_usage.conf` for more explanation on the parameters and options.
