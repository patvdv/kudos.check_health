## Plugin configuration

### Syntax

```yaml
hc_notify_eif:
  installed: <yes|no>
  EIF_BIN: <file_path>
  EIF_ETC: <file_path>
  EIF_SEVERITY: <severity>
```

Default values (non-null):
* *installed*: `yes`
* *EIF_BIN*: `/opt/eif/bin/posteifmsg`
* *EIF_ETC*: `/etc/opt/eif/posteifmsg.conf`
* *EIF_SEVERITY*: `MINOR`

### Example

```yaml
hc_notify_eif:
  installed: "yes"
```
