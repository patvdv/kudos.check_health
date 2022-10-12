## Plugin configuration

### Syntax

```yaml
hc_notify_sms:
  installed: <yes|no>
  sms_providers: <list_providers>
  sms_kapow_send_url: <url>
  sms_kapow_user: <user>
  sms_kapow_pass: <password>
```

Default values (non-null):
* *installed*: `yes`
* *sms_providers*: `kapow`

Parameter names are case-sensitive!

Use Ansible vault to the set password values!

The `sms_kapow_` parameters are specific for the KAPOW SMS service (https://www.kapow.co.uk). More service providers may be supported in the future in which case other provider-specific parameters will be added.


### Example

```yaml
hc_notify_sms:
  installed: "yes"
```
