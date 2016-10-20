# ansible-ntp-timesync
Ansible Role for configuring NTP

## Description

This role configures NTP while also paying attention to things like centrify sntp and vmware timesync feature on guests.

This is NOT ready for implementation yet, don't use in any prod environment, lot of testing still needed.

Configures:

* installation of ntp packages
* ntp.conf configuration for support of various options
* disabling vmware timesync
* disabling centrify sntp client

Variables:

| Name           | Default Value | Description                        |
| -------------- | ------------- | -----------------------------------|
| `os_auth_pw_max_age` | 60 | Max days a password is valid before requiring a change |
| `os_auth_pw_min_age` | 10 | Min days of age a password must have before it can be changed |
| `os_auth_pw_warn_age` | 7 | Days before password expires that account will be warned |
| `fail_deny` | 5 | Amount of times failed password can be tried before locking the account |
| `fail_unlock` | 300 | Seconds that must pass before account is unlocked after failed logins |
| `pwquality_minlen` | 8 | Minimum password length in characters |
| `pwquality_maxrepeat` | 3 | Maximum amount of same characters repeated in password |
| `pwquality_lcredit` | -1 | lowercase amount of chars that must be present in password |
| `pwquality_ucredit` | -1 | uppercase amount of chars that must be present in password |
| `pwquality_dcredit` | -1 | digits that must be present in password | 
| `pwquality_ocredit` | -1 | special chars that must be present in a password |
| `passhistory` | 6 | number of password to remember to avoid reusage |
| `sshrootlogin` | 'no' | allow ssh root login, keep single quotes to avoid boolean evaluation |
| `sshmainport` | 22 | main ssh port |
| `sshextraport` | 32 | secondary ssh port, set to 0 to disable an extra port |
| `setloginbanner` | 'yes' | use a login banner in ssh, keep single quotes to avoid boolean evaluation |
| `selinux_state` | permissive | selinux configuration value |
| `firewall_state` | stopped | Firewall desired status |
| `firewall_enable` |'no' | Desired firewall configuration status |
| `shell_timeout` | 900 | desired shell timeout in seconds, set 0 to disable |
| `sshd_solaris_restrict_ipv4` | True | Restrict ssh connections to ipv4 in solaris as workaround for DISPLAY issues |
| `solaris_dictionary_minwordlength` | 5 | Solaris minimum dictionary word length |
| `disable_ctrlaltdel` | True | Whether to disable Control-Alt-Del and physical sendbreak in Solaris |
