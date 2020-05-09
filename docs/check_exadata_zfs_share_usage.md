## Plugin configuration

### Syntax

```yaml
hc_check_exadata_zfs_share_usage:
  scheduled: <yes|no>
  log_healthy: <yes|no>
  ssh_user: <user>
  ssh_key_file: <ssh_private_key_file>
  ssh_opts: <ssh_options>
  max_space_usage: <threshold>
  hosts:
    - name: <server>
      shares:
        - name: <share>
          project: <project>
          max_space_usage: <threshold>
```

Default values (non-null):
* *scheduled*: `no`
* *log_healthy*: `no`
* *ssh_user*: `root`
* *ssh_key_file*: `~root/.ssh/id_rsa`
* *max_space_usage*: `90` (only general threshold)

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
hc_check_exadata_zfs_share_usage:
  scheduled: "yes"
  log_healthy: "yes"
  hosts:
    - name: "zfs1.acme.com"
      shares:
        - name: "share1"
          project: "project1"
          max_space_usage: 80
    - name: "zfs.acme.com"
      shares:
        - name: "share2"
          project: "project2"
        - name: "share3"
          project: "project2"
          max_space_usage: 70
    - name: "zfs3.acme.com"
      shares:
        - name: "*"
          project: "*"
          max_space_usage: 95
```

### Further reading

See the plugin configuration file `check_exadata_zfs_share_usage.conf` for more explanation on the parameters and options.
