# Contents of krb5.conf file

```
[libdefaults]
default_realm = MLADEN-TRAMPIC-SRB-1989.SG
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
MLADEN-TRAMPIC-SRB-1989.SG = {
kdc = ip-172-31-33-245.eu-central-1.compute.internal
admin_server = ip-172-31-33-245.eu-central-1.compute.internal
}
```