# Configuration snippets may be placed in this directory as well
includedir /etc/krb5.conf.d/

[logging]
 default = FILE:/var/log/krb5libs.log
 kdc = FILE:/var/log/krb5kdc.log
 admin_server = FILE:/var/log/kadmind.log

[libdefaults]
default_realm = ALEXPG06.HQ
dns_lookup_kdc = false
dns_lookup_realm = false
ticket_lifetime = 86400
renew_lifetime = 604800
forwardable = true
default_tgs_enctypes = rc4-hmac
default_tkt_enctypes = rc4-hmac
permitted_enctypes = rc4-hmac
udp_preference_limit = 1
kdc_timeout = 3000
[realms]
ALEXPG06.HQ = {
kdc = ip-10-1-2-155.ec2.internal
admin_server = ip-10-1-2-155.ec2.internal
}
[domain_realm]
# .example.com = EXAMPLE.COM
# example.com = EXAMPLE.COM