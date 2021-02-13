# kudos.check_health

Deployment and configuration of the KUDOS **Health Checker** framework (http://www.kudos.be/Projects/Health_checker.html)


## Requirements

Ansible v2.8+


## Role Variables

### Core configuration

```yaml
hc_core:
  time_out: <seconds>
  log_healthy: <yes|no>
  will_fix: <yes|no>
  report_last_cache: <yes|no>
  report_today_cache: <yes|no>
  count_archives: <yes|no>
```

Default values (non-null):
* *time_out*: `60`
* *log_healthy*: `no`
* *will_fix*: `no`
* *report_last_cache* `no`
* *report_today_cache* `no`
* *count_archives* `yes`

### Plugin configuration (checks)

#### Platform AIX

* [check_aix_errpt](docs/check_aix_errpt.md)
* [check_aix_fs_mounts](docs/check_aix_fs_mounts.md)
* [check_aix_lppchk](docs/check_aix_lppchk.md)
* [check_aix_file_age](docs/check_aix_file_age.md)
* [check_aix_file_change](docs/check_aix_file_change.md)
* [check_aix_paths](docs/check_aix_paths.md)
* [check_aix_root_crontab](docs/check_aix_root_crontab.md)
* [check_aix_subsystems](docs/check_aix_subsystems.md)
* [check_aix_sysbackup](docs/check_aix_sysbackup.md)
* [check_aix_topasrec](docs/check_aix_topasrec.md)
* [check_aix_uptime](docs/check_aix_uptime.md)

#### Platform Clusterware

* [check_clusterware_resource_config](docs/check_clusterware_resource_config.md)
* [check_clusterware_resource_status](docs/check_clusterware_resource_status.md)

#### Platform Exadata

* [check_exadata_cell_alerts](docs/check_exadata_cell_alerts.md)
* [check_exadata_cell_celldisks](docs/check_exadata_cell_celldisks.md)
* [check_exadata_cell_flash](docs/check_exadata_cell_flash.md)
* [check_exadata_cell_griddisks](docs/check_exadata_cell_griddisks.md)
* [check_exadata_cell_luns](docs/check_exadata_cell_luns.md)
* [check_exadata_cell_megaraid](docs/check_exadata_cell_megaraid.md)
* [check_exadata_cell_physicaldisks](docs/check_exadata_cell_physicaldisks.md)
* [check_exadata_megaraid](docs/check_exadata_megaraid.md)
* [check_exadata_zfs_cluster](docs/check_exadata_zfs_cluster.md)
* [check_exadata_zfs_logs](docs/check_exadata_zfs_logs.md)
* [check_exadata_zfs_pool_usage](docs/check_exadata_zfs_pool_usage.md)
* [check_exadata_zfs_services](docs/check_exadata_zfs_services.md)
* [check_exadata_zfs_share_replication](docs/check_exadata_zfs_share_replication.md)
* [check_exadata_zfs_share_usage](docs/check_exadata_zfs_share_usage.md)

#### Platform HP-UX

* [check_hpux_autofs](docs/check_hpux_autofs.md)
* [check_hpux_autopath](docs/check_hpux_autopath.md)
* [check_hpux_cdsf_cluster](docs/check_hpux_cdsf_cluster.md)
* [check_hpux_cron_status](docs/check_hpux_cron_status.md)
* [check_hpux_drd_status](docs/check_hpux_drd_status.md)
* [check_hpux_file_age](docs/check_hpux_file_age.md)
* [check_hpux_file_change](docs/check_hpux_file_change.md)
* [check_hpux_fs_mounts](docs/check_hpux_fs_mounts.md)
* [check_hpux_fs_mounts_options](docs/check_hpux_fs_mounts_options.md)
* [check_hpux_fs_usage](docs/check_hpux_fs_usage.md)
* [check_hpux_guid_status](docs/check_hpux_guid_status.md)
* [check_hpux_httpd_status](docs/check_hpux_httpd_status.md)
* [check_hpux_ignite_backup](docs/check_hpux_ignite_backup.md)
* [check_hpux_ioscan](docs/check_hpux_ioscan.md)
* [check_hpux_hpvm_vpar_status](docs/check_hpux_hpvm_vpar_status.md)
* [check_hpux_kernel_params](docs/check_hpux_kernel_params.md)
* [check_hpux_kernel_usage](docs/check_hpux_kernel_usage.md)
* [check_hpux_lunpaths](docs/check_hpux_lunpaths.md)
* [check_hpux_named_status](docs/check_hpux_named_status.md)
* [check_hpux_ntp_status](docs/check_hpux_ntp_status.md)
* [check_hpux_ovpa_status](docs/check_hpux_ovpa_status.md)
* [check_hpux_patch_version](docs/check_hpux_patch_version.md)
* [check_hpux_postfix_status](docs/check_hpux_postfix_status.md)
* [check_hpux_root_crontab](docs/check_hpux_root_crontab.md)
* [check_hpux_sfm_status](docs/check_hpux_sfm_status.md)
* [check_hpux_sshd_status](docs/check_hpux_sshd_status.md)
* [check_hpux_syslog](docs/check_hpux_syslog.md)
* [check_hpux_syslogd_status](docs/check_hpux_syslogd_status.md)
* [check_hpux_uptime](docs/check_hpux_uptime.md)
* [check_hpux_vg_minor_number](docs/check_hpux_vg_minor_number.md)

#### Platform Linux

* [check_linux_autofs](docs/check_linux_autofs.md)
* [check_linux_burp_backup](docs/check_linux_burp_backup.md)
* [check_linux_burp_status](docs/check_linux_burp_status.md)
* [check_linux_dovecot_status](docs/check_linux_dovecot_status.md)
* [check_linux_es_status](docs/check_linux_es_status.md)
* [check_linux_fail2ban_status](docs/check_linux_fail2ban_status.md)
* [check_linux_fetchmail_status](docs/check_linux_fetchmail_status.md)
* [check_linux_file_age](docs/check_linux_file_age.md)
* [check_linux_file_change](docs/check_linux_file_change.md)
* [check_linux_fs_mounts](docs/check_linux_fs_mounts.md)
* [check_linux_fs_usage](docs/check_linux_fs_usage.md)
* [check_linux_hpacucli](docs/check_linux_hpacucli.md)
* [check_linux_hpasmcli](docs/check_linux_hpasmcli.md)
* [check_linux_hplog](docs/check_linux_hplog.md)
* [check_linux_hpssacli](docs/check_linux_hpssacli.md)
* [check_linux_httpd_status](docs/check_linux_httpd_status.md)
* [check_linux_mysqld_status](docs/check_linux_mysqld_status.md)
* [check_linux_named_status](docs/check_linux_named_status.md)
* [check_linux_ntp_status](docs/check_linux_ntp_status.md)
* [check_linux_postfix_status](docs/check_linux_postfix_status.md)
* [check_linux_process_limits](docs/check_linux_process_limits.md)
* [check_linux_root_crontab](docs/check_linux_root_crontab.md)
* [check_linux_samba_status](docs/check_linux_samba_status.md)
* [check_linux_shorewall_status](docs/check_linux_shorewall_status.md)
* [check_linux_sshd_status](docs/check_linux_sshd_status.md)
* [check_linux_uptime](docs/check_linux_uptime.md)
* [check_linux_vz_ct_counters](docs/check_linux_vz_ct_counters.md)
* [check_linux_vz_ct_status](docs/check_linux_vz_ct_status.md)
* [check_linux_winbind_status](docs/check_linux_winbind_status.md)

#### Platform Serviceguard

* [check_serviceguard_cluster_config](docs/check_serviceguard_cluster_config.md)
* [check_serviceguard_cluster_status](docs/check_serviceguard_cluster_status.md)
* [check_serviceguard_package_config](docs/check_serviceguard_package_config.md)
* [check_serviceguard_package_status](docs/check_serviceguard_package_status.md)
* [check_serviceguard_qs_status](docs/check_serviceguard_qs_status.md)

### Plugin configuration (display)

* [hc_display_csv](docs/hc_display_csv.md)
* [hc_display_init](docs/hc_display_init.md)
* [hc_display_json](docs/hc_display_json.md)
* [hc_display_terse](docs/hc_display_terse.md)
* [hc_display_zenoss](docs/hc_display_zenoss.md)

### Plugin configuration (notify)
check_linux_es_status
* [hc_notify_eif](docs/hc_notify_eif.md)
* [hc_notify_sms](docs/hc_notify_sms.md)

### Static definitions

Following variables must be available in the role vars:
- `hc_display_plugins`: list of display plugins
- `hc_notify_plugins`: list of notify plugins
- `hc_configs`: list of plugins that require a configuration file
- `hc_packages`: map plugin -> package
- `hc_cron_packages`: map plugin -> cron package

*Note:* do not change these definitions unless you know what you are doing!

Additionally, following static vars may be defined to configure custom plugins:

- `hc_extra_configs`: list of plugins that require a configuration file
- `hc_extra_packages`: map plugin -> package
- `hc_extra_cron_packages`: map plugin -> cron package


## Dependencies

No dependencies


## Example Playbook

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

```yaml
    - hosts: all:!windows
      remote_user: root
      become: yes
      roles:
        - kudos.check_health
```


## License

GPL v3


## Author Information

Patrick Van der Veken - KUDOS BVBA (http://www.kudos.be)
