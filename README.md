[![Build Status](https://travis-ci.org/scathatheworm/ansible-ntp-timesync.svg)](https://travis-ci.org/scathatheworm/ansible-ntp-timesync) [![Ansible Galaxy](http://img.shields.io/badge/galaxy-scathatheworm.ntp-timesync.svg)](https://galaxy.ansible.com/scathatheworm/ntp-timesync)

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
| `ntp_tinkerpanicifvm` | True | Set tinker panic 0 for ntp never to panic for out of initial sync values |
| `configure_timezone` | False | Do not configure the system timezone by default |
| `ntp_timezone` | UTC | Default timezone value |
| `ntp_server` | RHEL sources | Default timeservers to use |
| `ntp_restrict_v4` | True | set security restrictions for ipv4 |
| `ntp_restrict_v6` | True | set security restrictions for ipv6 |
| `ntp_uselocalclock` | False | set local hardware clock as fallback time source |
| `ntp_statistics` | no | statistic records to use, such as clockstats cryptostats loopstats peerstats |
| `ntp_broadcast` | no | broadcast server |
| `ntp_broadcastclient` | no | broadcast client |
| `ntp_multicastclient` | no | multicast client |
| `ntp_slewenable` | False | Set slew mode, useful for DB systems and to avoid issues with leap seconds |

OS Specific varibles:

| Name           | Description                                     |
| -------------- | ------------------------------------------------|
| `ntp_restrict_opts` | Restrict options to use for security |
| `ntp_driftfile` | Location of the drift file |
