[libdefaults]
default_realm = ALEXSEBC.COM
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
ALEXSEBC.COM = {
kdc = ip-10-1-2-181.ec2.internal
admin_server = ip-10-1-2-181.ec2.internal
}
[domain_realm]