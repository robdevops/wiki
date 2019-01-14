#  Config checkers
It's a good idea to sanity check your config changes before attempting to reload/restart a service.
In most cases, they also return an exit status you could use like: ''checkcommand && reloadcommand'' to always reload your services this way.

There should also be worked into orchestration tools which reload services (Puppet, Ansible, Salt, Chef).

## Apache
`apachectl configtest`

## BIND
`named-checkconf /etc/named.conf`

Debian Interfaces:
`ifreload -as`

## dhcpd
`dhcpd -t -cf /etc/dhcp/dhcpd.conf`

## Icinga2
`icinga2 daemon -C`

## Keepalived (starting in v2.0.4)
`keepalived -t -f /etc/keepalived/keepalived.conf`

## mysqld
`mysqld --verbose --help 1>/dev/null`

## OpenSSH
`sshd -t`

## Postifx
`postfix check`

## RADIUS
`radiusd -C`

## Squid
`squid -k check`
