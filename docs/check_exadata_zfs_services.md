## Plugin configuration

### Syntax

```yaml
hc_check_exadata_zfs_services:
  scheduled: <yes|no>
  log_healthy: <yes|no>
  ssh_user: <user>
  ssh_key_file: <ssh_private_key_file>
  ssh_opts: <ssh_options>
  hosts:
    - name: <server>
      services:
        - name: <service>
          state: <online|disabled>
```

Default values (non-null):
* *scheduled*: `no`
* *log_healthy*: `no`
* *ssh_user*: `root`
* *ssh_key_file*: `~root/.ssh/id_rsa`

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
hc_check_exadata_zfs_services:
  scheduled: "yes"
  log_healthy: "yes"
  hosts:
    - name: "zfs1.acme.com"
      services:
        - name: "svc1"
          state: "online"
        - name: "svc2"
          state: "disabled"
    - name: "zfs2.acme.com"
      services:
        - name: "svc3"
          state: "online"
```

### Further reading

See the plugin configuration file `check_exadata_zfs_services.conf` for more explanation on the parameters and options.
