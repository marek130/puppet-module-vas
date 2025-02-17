# Reference

<!-- DO NOT EDIT: This document was generated by Puppet Strings -->

## Table of Contents

### Classes

* [`vas`](#vas): Manages Dell Authentication Services previously known as VAS / QAS.

### Functions

* [`api_fetch`](#api_fetch)

## Classes

### <a name="vas"></a>`vas`

Puppet module to manage DELL Authentication Services previously known as VAS or
Quest Authentication Services.

When using the users.allow functionality in VAS, make sure to set the following option:
pam::allowed_users:
  - 'ALL'

The module creates facts as below:
- vas_usersallow - A list of entries in /etc/opt/quest/vas/users.allow.
- vas_domain - The domain that the host belongs to.
- vas_server_type - The server types (GC, DC, PDC).
- vas_servers - List of servers that VAS is using for authentication.
- vas_site - The AD-site that the host belongs to.
- vas_version - The complete version-string for the vas-client.
- vasmajversion - The Major version of the vas-client.

#### Examples

##### Example hiera config

```puppet
vas::username: 'joinuser'
vas::keytab_source: '/net/server/join.keytab'
vas::computers_ou: 'ou=computers,dc=example,dc=com'
vas::users_ou: 'ou=users,dc=example,dc=com'
vas::nismaps_ou: 'ou=nismaps,dc=example,dc=com'
vas::realm: 'realm.example.com'
```

#### Parameters

The following parameters are available in the `vas` class:

* [`manage_nis`](#manage_nis)
* [`package_version`](#package_version)
* [`enable_group_policies`](#enable_group_policies)
* [`users_allow_entries`](#users_allow_entries)
* [`users_deny_entries`](#users_deny_entries)
* [`user_override_entries`](#user_override_entries)
* [`group_override_entries`](#group_override_entries)
* [`username`](#username)
* [`keytab_path`](#keytab_path)
* [`keytab_source`](#keytab_source)
* [`keytab_owner`](#keytab_owner)
* [`keytab_group`](#keytab_group)
* [`keytab_mode`](#keytab_mode)
* [`vas_fqdn`](#vas_fqdn)
* [`computers_ou`](#computers_ou)
* [`users_ou`](#users_ou)
* [`nismaps_ou`](#nismaps_ou)
* [`user_search_path`](#user_search_path)
* [`group_search_path`](#group_search_path)
* [`upm_search_path`](#upm_search_path)
* [`nisdomainname`](#nisdomainname)
* [`realm`](#realm)
* [`domain_change`](#domain_change)
* [`sitenameoverride`](#sitenameoverride)
* [`vas_conf_client_addrs`](#vas_conf_client_addrs)
* [`vas_conf_vasypd_update_interval`](#vas_conf_vasypd_update_interval)
* [`vas_conf_full_update_interval`](#vas_conf_full_update_interval)
* [`vas_conf_group_update_mode`](#vas_conf_group_update_mode)
* [`vas_conf_root_update_mode`](#vas_conf_root_update_mode)
* [`vas_conf_disabled_user_pwhash`](#vas_conf_disabled_user_pwhash)
* [`vas_conf_expired_account_pwhash`](#vas_conf_expired_account_pwhash)
* [`vas_conf_locked_out_pwhash`](#vas_conf_locked_out_pwhash)
* [`vas_conf_preload_nested_memberships`](#vas_conf_preload_nested_memberships)
* [`vas_conf_update_process`](#vas_conf_update_process)
* [`vas_conf_upm_computerou_attr`](#vas_conf_upm_computerou_attr)
* [`vas_conf_vasd_update_interval`](#vas_conf_vasd_update_interval)
* [`vas_conf_vasd_auto_ticket_renew_interval`](#vas_conf_vasd_auto_ticket_renew_interval)
* [`vas_conf_vasd_lazy_cache_update_interval`](#vas_conf_vasd_lazy_cache_update_interval)
* [`vas_conf_vasd_timesync_interval`](#vas_conf_vasd_timesync_interval)
* [`vas_conf_vasd_cross_domain_user_groups_member_search`](#vas_conf_vasd_cross_domain_user_groups_member_search)
* [`vas_conf_vasd_password_change_script`](#vas_conf_vasd_password_change_script)
* [`vas_conf_vasd_password_change_script_timelimit`](#vas_conf_vasd_password_change_script_timelimit)
* [`vas_conf_vasd_workstation_mode`](#vas_conf_vasd_workstation_mode)
* [`vas_conf_vasd_workstation_mode_users_preload`](#vas_conf_vasd_workstation_mode_users_preload)
* [`vas_conf_vasd_workstation_mode_group_do_member`](#vas_conf_vasd_workstation_mode_group_do_member)
* [`vas_conf_vasd_workstation_mode_groups_skip_update`](#vas_conf_vasd_workstation_mode_groups_skip_update)
* [`vas_conf_vasd_ws_resolve_uid`](#vas_conf_vasd_ws_resolve_uid)
* [`vas_conf_vasd_deluser_check_timelimit`](#vas_conf_vasd_deluser_check_timelimit)
* [`vas_conf_vasd_delusercheck_interval`](#vas_conf_vasd_delusercheck_interval)
* [`vas_conf_vasd_delusercheck_script`](#vas_conf_vasd_delusercheck_script)
* [`vas_conf_vasd_username_attr_name`](#vas_conf_vasd_username_attr_name)
* [`vas_conf_vasd_groupname_attr_name`](#vas_conf_vasd_groupname_attr_name)
* [`vas_conf_vasd_uid_number_attr_name`](#vas_conf_vasd_uid_number_attr_name)
* [`vas_conf_vasd_gid_number_attr_name`](#vas_conf_vasd_gid_number_attr_name)
* [`vas_conf_vasd_gecos_attr_name`](#vas_conf_vasd_gecos_attr_name)
* [`vas_conf_vasd_home_dir_attr_name`](#vas_conf_vasd_home_dir_attr_name)
* [`vas_conf_vasd_login_shell_attr_name`](#vas_conf_vasd_login_shell_attr_name)
* [`vas_conf_vasd_group_member_attr_name`](#vas_conf_vasd_group_member_attr_name)
* [`vas_conf_vasd_memberof_attr_name`](#vas_conf_vasd_memberof_attr_name)
* [`vas_conf_vasd_unix_password_attr_name`](#vas_conf_vasd_unix_password_attr_name)
* [`vas_conf_vasd_netgroup_mode`](#vas_conf_vasd_netgroup_mode)
* [`vas_conf_prompt_vas_ad_pw`](#vas_conf_prompt_vas_ad_pw)
* [`vas_conf_pam_vas_prompt_ad_lockout_msg`](#vas_conf_pam_vas_prompt_ad_lockout_msg)
* [`vas_conf_libdefaults_forwardable`](#vas_conf_libdefaults_forwardable)
* [`vas_conf_libdefaults_tgs_default_enctypes`](#vas_conf_libdefaults_tgs_default_enctypes)
* [`vas_conf_libdefaults_tkt_default_enctypes`](#vas_conf_libdefaults_tkt_default_enctypes)
* [`vas_conf_libdefaults_default_etypes`](#vas_conf_libdefaults_default_etypes)
* [`vas_conf_libdefaults_default_cc_name`](#vas_conf_libdefaults_default_cc_name)
* [`vas_conf_vas_auth_uid_check_limit`](#vas_conf_vas_auth_uid_check_limit)
* [`vas_conf_vas_auth_allow_disconnected_auth`](#vas_conf_vas_auth_allow_disconnected_auth)
* [`vas_conf_vas_auth_expand_ac_groups`](#vas_conf_vas_auth_expand_ac_groups)
* [`vas_conf_libvas_vascache_ipc_timeout`](#vas_conf_libvas_vascache_ipc_timeout)
* [`vas_conf_libvas_use_server_referrals`](#vas_conf_libvas_use_server_referrals)
* [`vas_conf_libvas_use_server_referrals_version_switch`](#vas_conf_libvas_use_server_referrals_version_switch)
* [`vas_conf_libvas_auth_helper_timeout`](#vas_conf_libvas_auth_helper_timeout)
* [`vas_conf_libvas_mscldap_timeout`](#vas_conf_libvas_mscldap_timeout)
* [`vas_conf_libvas_site_only_servers`](#vas_conf_libvas_site_only_servers)
* [`vas_conf_libvas_use_dns_srv`](#vas_conf_libvas_use_dns_srv)
* [`vas_conf_libvas_use_tcp_only`](#vas_conf_libvas_use_tcp_only)
* [`vas_conf_lowercase_names`](#vas_conf_lowercase_names)
* [`vas_conf_lowercase_homedirs`](#vas_conf_lowercase_homedirs)
* [`vas_config_path`](#vas_config_path)
* [`vas_config_owner`](#vas_config_owner)
* [`vas_config_group`](#vas_config_group)
* [`vas_config_mode`](#vas_config_mode)
* [`vas_user_override_path`](#vas_user_override_path)
* [`vas_user_override_owner`](#vas_user_override_owner)
* [`vas_user_override_group`](#vas_user_override_group)
* [`vas_user_override_mode`](#vas_user_override_mode)
* [`vas_group_override_path`](#vas_group_override_path)
* [`vas_group_override_owner`](#vas_group_override_owner)
* [`vas_group_override_group`](#vas_group_override_group)
* [`vas_group_override_mode`](#vas_group_override_mode)
* [`vas_users_allow_path`](#vas_users_allow_path)
* [`vas_users_allow_owner`](#vas_users_allow_owner)
* [`vas_users_allow_group`](#vas_users_allow_group)
* [`vas_users_allow_mode`](#vas_users_allow_mode)
* [`vas_users_deny_path`](#vas_users_deny_path)
* [`vas_users_deny_owner`](#vas_users_deny_owner)
* [`vas_users_deny_group`](#vas_users_deny_group)
* [`vas_users_deny_mode`](#vas_users_deny_mode)
* [`vasjoin_logfile`](#vasjoin_logfile)
* [`vastool_binary`](#vastool_binary)
* [`symlink_vastool_binary_target`](#symlink_vastool_binary_target)
* [`symlink_vastool_binary`](#symlink_vastool_binary)
* [`license_files`](#license_files)
* [`domain_realms`](#domain_realms)
* [`join_domain_controllers`](#join_domain_controllers)
* [`unjoin_vas`](#unjoin_vas)
* [`use_srv_infocache`](#use_srv_infocache)
* [`kdcs`](#kdcs)
* [`kdc_port`](#kdc_port)
* [`kpasswd_servers`](#kpasswd_servers)
* [`kpasswd_server_port`](#kpasswd_server_port)
* [`api_enable`](#api_enable)
* [`api_users_allow_url`](#api_users_allow_url)
* [`api_token`](#api_token)

##### <a name="manage_nis"></a>`manage_nis`

Data type: `Boolean`

FIXME Missing description

Default value: ``true``

##### <a name="package_version"></a>`package_version`

Data type: `String[1]`

The VAS package version. Used when upgrading.

Default value: `'installed'`

##### <a name="enable_group_policies"></a>`enable_group_policies`

Data type: `Boolean`

Boolean to control if vas should manage group policies. Manages the vasgp
package. Version is controlled by package_version.

Default value: ``true``

##### <a name="users_allow_entries"></a>`users_allow_entries`

Data type: `Array[String[1]]`

List of users.allow entries. All users are allowed by default.

Default value: `[]`

##### <a name="users_deny_entries"></a>`users_deny_entries`

Data type: `Array[String[1]]`

List of users.deny entries. No users are denied by default.

Default value: `[]`

##### <a name="user_override_entries"></a>`user_override_entries`

Data type: `Array[String[1]]`

List of user-override entries. Used to override specific user data fields;
UID, GID, GECOS, HOME_DIR and SHELL.

Default value: `[]`

##### <a name="group_override_entries"></a>`group_override_entries`

Data type: `Array[String[1]]`

List of group-override entries. Used to override specific group data fields;
GROUP_NAME, GID and GROUP_MEMBERSHIP.

Default value: `[]`

##### <a name="username"></a>`username`

Data type: `String[1]`

Name of user account used to join Active Directory.

Default value: `'username'`

##### <a name="keytab_path"></a>`keytab_path`

Data type: `Stdlib::Absolutepath`

The path to the keytab file used together with <username> to join Active Directory.

Default value: `'/etc/vasinst.key'`

##### <a name="keytab_source"></a>`keytab_source`

Data type: `Optional[String[1]]`

File source for the keytab file used to join Active Directory.

Default value: ``undef``

##### <a name="keytab_owner"></a>`keytab_owner`

Data type: `String[1]`

keytab file owner.

Default value: `'root'`

##### <a name="keytab_group"></a>`keytab_group`

Data type: `String[1]`

keytab file group.

Default value: `'root'`

##### <a name="keytab_mode"></a>`keytab_mode`

Data type: `Stdlib::Filemode`

keytab file mode.

Default value: `'0400'`

##### <a name="vas_fqdn"></a>`vas_fqdn`

Data type: `Stdlib::Fqdn`

FQDN to join to VAS as.

Default value: `$facts['networking']['fqdn']`

##### <a name="computers_ou"></a>`computers_ou`

Data type: `Optional[String[1]]`

Path to OU where to store computer object.

Default value: ``undef``

##### <a name="users_ou"></a>`users_ou`

Data type: `Optional[String[1]]`

Deprecated, this parameter is the same as upm_search_path. Path to OU where
to load UPM user profiles.

Default value: ``undef``

##### <a name="nismaps_ou"></a>`nismaps_ou`

Data type: `String[1]`

Path to OU where to load nismaps initially.

Default value: `'ou=nismaps,dc=example,dc=com'`

##### <a name="user_search_path"></a>`user_search_path`

Data type: `Optional[String[1]]`

LDAP search path for user profiles. This will limit the scope where QAS will
search for users when operating in RFC2307 mode.

Default value: ``undef``

##### <a name="group_search_path"></a>`group_search_path`

Data type: `Optional[String[1]]`

LDAP search path for groups. This will limit the scope where QAS will search
for groups when operating in RFC2307 mode.

Default value: ``undef``

##### <a name="upm_search_path"></a>`upm_search_path`

Data type: `Optional[String[1]]`

LDAP search path for UPM user profiles. Setting this parameter will cause
QAS to run in UPM mode.

Default value: ``undef``

##### <a name="nisdomainname"></a>`nisdomainname`

Data type: `Optional[String[1]]`

Name of the NIS domain.

Default value: ``undef``

##### <a name="realm"></a>`realm`

Data type: `Stdlib::Host`

Name of the realm.

Default value: `'realm.example.com'`

##### <a name="domain_change"></a>`domain_change`

Data type: `Boolean`

FIXME Missing description

Default value: ``false``

##### <a name="sitenameoverride"></a>`sitenameoverride`

Data type: `Optional[String[1]]`

Name of AD site to join. The AD site is determined automatically in AD by
default.

Default value: ``undef``

##### <a name="vas_conf_client_addrs"></a>`vas_conf_client_addrs`

Data type: `Optional[String[1,1024]]`

client-addrs option in vas.conf. See VAS.CONF(5) for more info.

Default value: ``undef``

##### <a name="vas_conf_vasypd_update_interval"></a>`vas_conf_vasypd_update_interval`

Data type: `Integer[0]`

Integer for number of seconds vasypd will wait between checks for updated
NIS Map information in Active Directory. See VAS.CONF(5).

Default value: `1800`

##### <a name="vas_conf_full_update_interval"></a>`vas_conf_full_update_interval`

Data type: `Optional[Integer]`

Integer for number of seconds vasypd will wait until it fully reloads all
the NIS maps. See VAS.CONF(5)

Default value: ``undef``

##### <a name="vas_conf_group_update_mode"></a>`vas_conf_group_update_mode`

Data type: `String[1]`

The value of group-update-mode in the [nss_vas] configuration section.
This controls how directory searches will be handeled for group nss
functions. See VAS.CONF(5) for more info.
Possible values: force | force-if-missing | none

Default value: `'none'`

##### <a name="vas_conf_root_update_mode"></a>`vas_conf_root_update_mode`

Data type: `String[1]`

The value of root-update-mode in the [nss_vas] configuration section.
This controls how directory searches will be performed when calling nss
functions. See VAS.CONF(5) for more info.
Possible values: force | force-if-missing | none

Default value: `'none'`

##### <a name="vas_conf_disabled_user_pwhash"></a>`vas_conf_disabled_user_pwhash`

Data type: `Optional[String[1]]`

String to be used for disabled-user-pwhash option in vas.conf. If undef,
line will be suppressed.

Default value: ``undef``

##### <a name="vas_conf_expired_account_pwhash"></a>`vas_conf_expired_account_pwhash`

Data type: `Optional[String[1]]`

String to be used for expired-account-pwhash option in vas.conf.
If undef, line will be suppressed.

Default value: ``undef``

##### <a name="vas_conf_locked_out_pwhash"></a>`vas_conf_locked_out_pwhash`

Data type: `Optional[String[1]]`

String to be used for locked-out-pwhash option in vas.conf.
If undef, line will be suppressed.

Default value: ``undef``

##### <a name="vas_conf_preload_nested_memberships"></a>`vas_conf_preload_nested_memberships`

Data type: `Optional[Boolean]`

preload-nested-membership option in vas.conf. Set this to 'false' to speed
up flush (and join) operations in VAS version 4.0.3-206 and later.

Default value: ``undef``

##### <a name="vas_conf_update_process"></a>`vas_conf_update_process`

Data type: `Stdlib::Absolutepath`

update-process option in vas.conf. See VAS.CONF(5) for more info.

Default value: `'/opt/quest/libexec/vas/mapupdate_2307'`

##### <a name="vas_conf_upm_computerou_attr"></a>`vas_conf_upm_computerou_attr`

Data type: `Optional[String[1]]`

upm-computerou-attr option in vas.conf. Changed to 'department' to work in
a multi-AD-domain setup. See VAS.CONF(5) for more info.

Default value: ``undef``

##### <a name="vas_conf_vasd_update_interval"></a>`vas_conf_vasd_update_interval`

Data type: `Integer[0]`

Integer for number of seconds to set value of update-interval in [vasd]
section of vas.conf. See VAS.CONF(5) for more info.

Default value: `600`

##### <a name="vas_conf_vasd_auto_ticket_renew_interval"></a>`vas_conf_vasd_auto_ticket_renew_interval`

Data type: `Integer[0]`

Integer for number of seconds to set value of auto-ticket-renew-interval
in [vasd] section of vas.conf. See VAS.CONF(5) for more info.

Default value: `32400`

##### <a name="vas_conf_vasd_lazy_cache_update_interval"></a>`vas_conf_vasd_lazy_cache_update_interval`

Data type: `Integer[0]`

Integer for number of minutes for the value of lazy-cache-update-interval
in [vasd] section of vas.conf. See VAS.CONF(5) for more info.

Default value: `10`

##### <a name="vas_conf_vasd_timesync_interval"></a>`vas_conf_vasd_timesync_interval`

Data type: `Optional[Integer]`

Integer for number of seconds to set value of timesync-interval in
[vasd] section of vas.conf. See VAS.CONF(5) for more info.
If $::virtual is "zone" this value is set to 0

Default value: ``undef``

##### <a name="vas_conf_vasd_cross_domain_user_groups_member_search"></a>`vas_conf_vasd_cross_domain_user_groups_member_search`

Data type: `Optional[Boolean]`

Boolean to set value of cross-domain-user-groups-member-search in
[vasd] section of vas.conf. See VAS.CONF(5) for more info.

Default value: ``undef``

##### <a name="vas_conf_vasd_password_change_script"></a>`vas_conf_vasd_password_change_script`

Data type: `Optional[Stdlib::Absolutepath]`

Path for script to set value of password-change-script in
[vasd] section of vas.conf. See VAS.CONF(5) for more info.

Default value: ``undef``

##### <a name="vas_conf_vasd_password_change_script_timelimit"></a>`vas_conf_vasd_password_change_script_timelimit`

Data type: `Optional[Integer]`

Integer for number of seconds to set value of
password-change-script-timelimit in [vasd] section of vas.conf.
See VAS.CONF(5) for more info.

Default value: ``undef``

##### <a name="vas_conf_vasd_workstation_mode"></a>`vas_conf_vasd_workstation_mode`

Data type: `Boolean`

Boolean to control whether or not vasd operates in Workstation mode.
See VAS.CONF(5) for more info.

Default value: ``false``

##### <a name="vas_conf_vasd_workstation_mode_users_preload"></a>`vas_conf_vasd_workstation_mode_users_preload`

Data type: `Optional[String[1]]`

Comma separated list of groups for preloading users in Workstation mode.
See VAS.CONF(5) for more info.

Default value: ``undef``

##### <a name="vas_conf_vasd_workstation_mode_group_do_member"></a>`vas_conf_vasd_workstation_mode_group_do_member`

Data type: `Boolean`

Boolean to control if vasd should process group memberships in Workstation
mode. See VAS.CONF(5) for more info.

Default value: ``false``

##### <a name="vas_conf_vasd_workstation_mode_groups_skip_update"></a>`vas_conf_vasd_workstation_mode_groups_skip_update`

Data type: `Boolean`

Boolean that can be used to reduce the number of updates by vasd in
Workstation mode. See VAS.CONF(5) for more info.

Default value: ``false``

##### <a name="vas_conf_vasd_ws_resolve_uid"></a>`vas_conf_vasd_ws_resolve_uid`

Data type: `Boolean`

Boolean to control whether vasd will resolve unknown UIDs when in
Workstation mode. See VAS.CONF(5) for more info.

Default value: ``false``

##### <a name="vas_conf_vasd_deluser_check_timelimit"></a>`vas_conf_vasd_deluser_check_timelimit`

Data type: `Optional[Integer]`

Integer for number of seconds to set value of deluser-check-timelimit in
[vasd] section of vas.conf. See VAS.CONF(5) for more info.

Default value: ``undef``

##### <a name="vas_conf_vasd_delusercheck_interval"></a>`vas_conf_vasd_delusercheck_interval`

Data type: `Optional[Integer]`

Integer for number of minutes to set value of delusercheck-interval in
[vasd] section of vas.conf. See VAS.CONF(5) for more info.

Default value: ``undef``

##### <a name="vas_conf_vasd_delusercheck_script"></a>`vas_conf_vasd_delusercheck_script`

Data type: `Optional[Stdlib::Absolutepath]`

Path for script to set value of delusercheck-script in [vasd] section of
vas.conf. See VAS.CONF(5) for more info.

Default value: ``undef``

##### <a name="vas_conf_vasd_username_attr_name"></a>`vas_conf_vasd_username_attr_name`

Data type: `Optional[String[1]]`

String to be used for username-attr-name  in [vasd] section of vas.conf.
See VAS.CONF(5) for more info.

Default value: ``undef``

##### <a name="vas_conf_vasd_groupname_attr_name"></a>`vas_conf_vasd_groupname_attr_name`

Data type: `Optional[String[1]]`

String to be used for groupname-attr-name  in [vasd] section of vas.conf.
See VAS.CONF(5) for more info.

Default value: ``undef``

##### <a name="vas_conf_vasd_uid_number_attr_name"></a>`vas_conf_vasd_uid_number_attr_name`

Data type: `Optional[String[1]]`

String to be used for uid-number-attr-name  in [vasd] section of vas.conf.
See VAS.CONF(5) for more info.

Default value: ``undef``

##### <a name="vas_conf_vasd_gid_number_attr_name"></a>`vas_conf_vasd_gid_number_attr_name`

Data type: `Optional[String[1]]`

String to be used for gid-number-attr-name  in [vasd] section of vas.conf.
See VAS.CONF(5) for more info.

Default value: ``undef``

##### <a name="vas_conf_vasd_gecos_attr_name"></a>`vas_conf_vasd_gecos_attr_name`

Data type: `Optional[String[1]]`

String to be used for gecos-attr-name  in [vasd] section of vas.conf.
See VAS.CONF(5) for more info.

Default value: ``undef``

##### <a name="vas_conf_vasd_home_dir_attr_name"></a>`vas_conf_vasd_home_dir_attr_name`

Data type: `Optional[String[1]]`

String to be used for home-dir-attr-name  in [vasd] section of vas.conf.
See VAS.CONF(5) for more info.

Default value: ``undef``

##### <a name="vas_conf_vasd_login_shell_attr_name"></a>`vas_conf_vasd_login_shell_attr_name`

Data type: `Optional[String[1]]`

String to be used for login-shell-attr-name  in [vasd] section of vas.conf.
See VAS.CONF(5) for more info.

Default value: ``undef``

##### <a name="vas_conf_vasd_group_member_attr_name"></a>`vas_conf_vasd_group_member_attr_name`

Data type: `Optional[String[1]]`

String to be used for group-member-attr-name  in [vasd] section of vas.conf.
See VAS.CONF(5) for more info.

Default value: ``undef``

##### <a name="vas_conf_vasd_memberof_attr_name"></a>`vas_conf_vasd_memberof_attr_name`

Data type: `Optional[String[1]]`

String to be used for memberof-attr-name  in [vasd] section of vas.conf.
See VAS.CONF(5) for more info.

Default value: ``undef``

##### <a name="vas_conf_vasd_unix_password_attr_name"></a>`vas_conf_vasd_unix_password_attr_name`

Data type: `Optional[String[1]]`

String to be used for unix_password-attr-name  in [vasd] section of vas.conf.
See VAS.CONF(5) for more info.

Default value: ``undef``

##### <a name="vas_conf_vasd_netgroup_mode"></a>`vas_conf_vasd_netgroup_mode`

Data type: `Optional[Enum['NSS', 'NIS', 'OFF']]`

String to be used to set value of netgroup-mode in the [vasd] section of
vas.conf. Valid values are 'NSS', 'NIS' and 'OFF'. If not specified, the
netgroup-mode parameter will not be set in vas.conf.
See VAS.CONF(5) for more info.

Default value: ``undef``

##### <a name="vas_conf_prompt_vas_ad_pw"></a>`vas_conf_prompt_vas_ad_pw`

Data type: `String[1]`

prompt-vas-ad-pw option in vas.conf. Sets the password prompt for logins.

Default value: `'"Enter Windows password: "'`

##### <a name="vas_conf_pam_vas_prompt_ad_lockout_msg"></a>`vas_conf_pam_vas_prompt_ad_lockout_msg`

Data type: `Optional[String[1]]`

prompt-ad-lockout-msg option in vas.conf. See VAS.CONF(5) for more info.

Default value: ``undef``

##### <a name="vas_conf_libdefaults_forwardable"></a>`vas_conf_libdefaults_forwardable`

Data type: `Boolean`

Boolean to set value of forwardable in [libdefaults] vas.conf.
See VAS.CONF(5) for more info.

Default value: ``true``

##### <a name="vas_conf_libdefaults_tgs_default_enctypes"></a>`vas_conf_libdefaults_tgs_default_enctypes`

Data type: `String[1]`

FIXME Missing description

Default value: `'arcfour-hmac-md5'`

##### <a name="vas_conf_libdefaults_tkt_default_enctypes"></a>`vas_conf_libdefaults_tkt_default_enctypes`

Data type: `String[1]`

FIXME Missing description

Default value: `'arcfour-hmac-md5'`

##### <a name="vas_conf_libdefaults_default_etypes"></a>`vas_conf_libdefaults_default_etypes`

Data type: `String[1]`

String to set value of default_etypes in [libdefaults] vas.conf.
See VAS.CONF(5) for more info.

Default value: `'arcfour-hmac-md5'`

##### <a name="vas_conf_libdefaults_default_cc_name"></a>`vas_conf_libdefaults_default_cc_name`

Data type: `Optional[String[1]]`

String to set where kerberos cache files should be stored (default on most
systems is /tmp/krb5cc_${uid}).
Example: FILE:/new/path/krb5cc_${uid}

Default value: ``undef``

##### <a name="vas_conf_vas_auth_uid_check_limit"></a>`vas_conf_vas_auth_uid_check_limit`

Data type: `Optional[Integer]`

Integer for uid-check-limit option in vas.conf.
See VAS.CONF(5) for more info.

Default value: ``undef``

##### <a name="vas_conf_vas_auth_allow_disconnected_auth"></a>`vas_conf_vas_auth_allow_disconnected_auth`

Data type: `Optional[Boolean]`

Boolean to set value of allow-disconnected-auth option in [vas_auth] section
of vas.conf. See VAS.CONF(5) for more info. If set to 'UNSET' nothing will
get printed.

Default value: ``undef``

##### <a name="vas_conf_vas_auth_expand_ac_groups"></a>`vas_conf_vas_auth_expand_ac_groups`

Data type: `Optional[Boolean]`

Boolean to set value of expand-ac-groups option in [vas_auth] section of
vas.conf. See VAS.CONF(5) for more info. If set to 'UNSET' nothing will get
printed.

Default value: ``undef``

##### <a name="vas_conf_libvas_vascache_ipc_timeout"></a>`vas_conf_libvas_vascache_ipc_timeout`

Data type: `Integer[0]`

Integer for number of seconds to set value of vascache-ipc-timeout in
[libvas] section of vas.conf. See VAS.CONF(5) for more info.

Default value: `15`

##### <a name="vas_conf_libvas_use_server_referrals"></a>`vas_conf_libvas_use_server_referrals`

Data type: `Variant[Boolean, Enum['']]`

Boolean to set valut of use-server-referrals in [libvas] section of vas.conf.
See VAS.CONF(5) for more info. Set to 'USE_DEFAULTS' for automagically
switching depending on running $vas_version.
Also see $vas_conf_libvas_use_server_referrals_version_switch.

Default value: ``true``

##### <a name="vas_conf_libvas_use_server_referrals_version_switch"></a>`vas_conf_libvas_use_server_referrals_version_switch`

Data type: `String[1]`

String with version number to set use-server-referrals to false when
$vas_conf_libvas_use_server_referrals is set to 'USE_DEFAULTS'.
Equal or higher version numbers will pull the trigger.

Default value: `'4.1.0.21518'`

##### <a name="vas_conf_libvas_auth_helper_timeout"></a>`vas_conf_libvas_auth_helper_timeout`

Data type: `Integer[0]`

Integer for number of seconds to set value of auth-helper-timeout in
[libvas] section of vas.conf. See VAS.CONF(5) for more info.

Default value: `10`

##### <a name="vas_conf_libvas_mscldap_timeout"></a>`vas_conf_libvas_mscldap_timeout`

Data type: `Integer[0]`

Integer to control the timeout when performing a MSCLDAP ping against
AD Domain Controllers. See VAS.CONF(5) for more info.

Default value: `1`

##### <a name="vas_conf_libvas_site_only_servers"></a>`vas_conf_libvas_site_only_servers`

Data type: `Boolean`

Boolean to set valut of site-only-servers in [libvas] section of
vas.conf. See VAS.CONF(5) for more info.

Default value: ``false``

##### <a name="vas_conf_libvas_use_dns_srv"></a>`vas_conf_libvas_use_dns_srv`

Data type: `Boolean`

Boolean to set value of use-dns-srv in [libvas] section of vas.conf.
See VAS.CONF(5) for more info.

Default value: ``true``

##### <a name="vas_conf_libvas_use_tcp_only"></a>`vas_conf_libvas_use_tcp_only`

Data type: `Boolean`

Boolean to set value of use-tcp-only in [libvas] section of vas.conf.
See VAS.CONF(5) for more info.

Default value: ``true``

##### <a name="vas_conf_lowercase_names"></a>`vas_conf_lowercase_names`

Data type: `Optional[Boolean]`

Boolean to set value of lowercase-names in [nss_vas] section of vas.conf.
See VAS.CONF(5) for more info.

Default value: ``undef``

##### <a name="vas_conf_lowercase_homedirs"></a>`vas_conf_lowercase_homedirs`

Data type: `Optional[Boolean]`

Boolean to set value of lowercase-homedirs in [nss_vas] section of vas.conf.
See VAS.CONF(5) for more info.

Default value: ``undef``

##### <a name="vas_config_path"></a>`vas_config_path`

Data type: `Stdlib::Absolutepath`

Path to VAS config file.

Default value: `'/etc/opt/quest/vas/vas.conf'`

##### <a name="vas_config_owner"></a>`vas_config_owner`

Data type: `String[1]`

vas.conf owner.

Default value: `'root'`

##### <a name="vas_config_group"></a>`vas_config_group`

Data type: `String[1]`

vas.conf group.

Default value: `'root'`

##### <a name="vas_config_mode"></a>`vas_config_mode`

Data type: `Stdlib::Filemode`

vas.conf mode.

Default value: `'0644'`

##### <a name="vas_user_override_path"></a>`vas_user_override_path`

Data type: `Stdlib::Absolutepath`

Path to user-override file.

Default value: `'/etc/opt/quest/vas/user-override'`

##### <a name="vas_user_override_owner"></a>`vas_user_override_owner`

Data type: `String[1]`

user-override file owner.

Default value: `'root'`

##### <a name="vas_user_override_group"></a>`vas_user_override_group`

Data type: `String[1]`

user-override file group.

Default value: `'root'`

##### <a name="vas_user_override_mode"></a>`vas_user_override_mode`

Data type: `Stdlib::Filemode`

user-override file mode.

Default value: `'0644'`

##### <a name="vas_group_override_path"></a>`vas_group_override_path`

Data type: `Stdlib::Absolutepath`

Path to user-override file.

Default value: `'/etc/opt/quest/vas/group-override'`

##### <a name="vas_group_override_owner"></a>`vas_group_override_owner`

Data type: `String[1]`

group-override file owner.

Default value: `'root'`

##### <a name="vas_group_override_group"></a>`vas_group_override_group`

Data type: `String[1]`

group-override file group.

Default value: `'root'`

##### <a name="vas_group_override_mode"></a>`vas_group_override_mode`

Data type: `Stdlib::Filemode`

group-override file mode.

Default value: `'0644'`

##### <a name="vas_users_allow_path"></a>`vas_users_allow_path`

Data type: `Stdlib::Absolutepath`

Path to users.allow file.

Default value: `'/etc/opt/quest/vas/users.allow'`

##### <a name="vas_users_allow_owner"></a>`vas_users_allow_owner`

Data type: `String[1]`

users.allow file owner.

Default value: `'root'`

##### <a name="vas_users_allow_group"></a>`vas_users_allow_group`

Data type: `String[1]`

users.allow file group.

Default value: `'root'`

##### <a name="vas_users_allow_mode"></a>`vas_users_allow_mode`

Data type: `Stdlib::Filemode`

users.allow file mode.

Default value: `'0644'`

##### <a name="vas_users_deny_path"></a>`vas_users_deny_path`

Data type: `Stdlib::Absolutepath`

Path to users.deny file.

Default value: `'/etc/opt/quest/vas/users.deny'`

##### <a name="vas_users_deny_owner"></a>`vas_users_deny_owner`

Data type: `String[1]`

users.deny file owner.

Default value: `'root'`

##### <a name="vas_users_deny_group"></a>`vas_users_deny_group`

Data type: `String[1]`

users.deny file group.

Default value: `'root'`

##### <a name="vas_users_deny_mode"></a>`vas_users_deny_mode`

Data type: `Stdlib::Filemode`

users.deny file mode.

Default value: `'0644'`

##### <a name="vasjoin_logfile"></a>`vasjoin_logfile`

Data type: `Stdlib::Absolutepath`

Path to logfile used by AD join commando.

Default value: `'/var/tmp/vasjoin.log'`

##### <a name="vastool_binary"></a>`vastool_binary`

Data type: `Stdlib::Absolutepath`

Path to vastool binary to create symlink from.

Default value: `'/opt/quest/bin/vastool'`

##### <a name="symlink_vastool_binary_target"></a>`symlink_vastool_binary_target`

Data type: `Stdlib::Absolutepath`

Path to where the symlink should be created.

Default value: `'/usr/bin/vastool'`

##### <a name="symlink_vastool_binary"></a>`symlink_vastool_binary`

Data type: `Boolean`

Boolean for ensuring a symlink for vastool_binary to
symlink_vastool_binary_target. This is useful since /opt/quest/bin is a
non-standard location that is not in your $PATH.

Default value: ``false``

##### <a name="license_files"></a>`license_files`

Data type: `Hash`

Hash of license files.

Default value: `{}`

##### <a name="domain_realms"></a>`domain_realms`

Data type: `Hash`

Hash of domains that should be mapped to correct realm.

Default value: `{}`

##### <a name="join_domain_controllers"></a>`join_domain_controllers`

Data type: `Array[String[1]]`

A string or an array with domain controllers to contact during the join
process. Normally the servers for the domain will be automatically detected
through DNS and LDAP lookups. By specifying this parameter vastool will
contact the specified servers and only those servers during the join process.
This can be useful if the machine being joined is not able to talk with all
global Domain Controllers (e.g. due to firewalls). Note that this will have
no effect after the join, where normal site discovery of servers will be
made.

Default value: `[]`

##### <a name="unjoin_vas"></a>`unjoin_vas`

Data type: `Boolean`

Boolean to trigger an unjoining of the domain. Obviously this will only
work if the system is joined to a domain.

Default value: ``false``

##### <a name="use_srv_infocache"></a>`use_srv_infocache`

Data type: `Optional[Boolean]`

A bool to achieve the same thing as issuing "vastool configure vas libvas
use-srv-info-cache <bool>" Only has any effect if set to false.

Default value: ``undef``

##### <a name="kdcs"></a>`kdcs`

Data type: `Array[String[1]]`

An array of kdcs that are to be entered under the [realms] section. If set
has the same effect as issuing
"vastool configure realm domain.tld srv1.domain.tld srv2.domain.tld". (eg)

Default value: `[]`

##### <a name="kdc_port"></a>`kdc_port`

Data type: `Stdlib::Port`

An integer containing the kdc port. Has no effect unless kdcs is populated
with servernames.

Default value: `88`

##### <a name="kpasswd_servers"></a>`kpasswd_servers`

Data type: `Array[String[1]]`

An array of kpasswd servers that are to be entered under the [realms] section
Normally needs not be set unless you want something different than the value
of kdcs (above).

Default value: `[]`

##### <a name="kpasswd_server_port"></a>`kpasswd_server_port`

Data type: `Stdlib::Port`

An integer containing the kpasswd server port. Has no effect unless
kpasswd_servers or kdcs is populated with servernames.

Default value: `464`

##### <a name="api_enable"></a>`api_enable`

Data type: `Boolean`

A boolean to control, whether the API function is called. If called, the API
will return a list of entries for the users.allow file. This result will be
merged with whatever content is provided otherwise provided; i.e. it will be
concatenated with the content created by parameters users_allow_entries.

Default value: ``false``

##### <a name="api_users_allow_url"></a>`api_users_allow_url`

Data type: `Optional[Stdlib::HTTPSUrl]`

The URL towards the API.

Default value: ``undef``

##### <a name="api_token"></a>`api_token`

Data type: `Optional[String[1]]`

Security token for authenticated access to the API.

Default value: ``undef``

## Functions

### <a name="api_fetch"></a>`api_fetch`

Type: Ruby 3.x API

The api_fetch function.

#### `api_fetch()`

The api_fetch function.

Returns: `Any`

