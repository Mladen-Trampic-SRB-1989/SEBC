# Content kdc.conf file

```
[libdefaults]
default_realm = MLADEN-TRAMPIC-SRB-1989.SG
allow_weak_crypto = true

[kdcdefaults]
 kdc_ports = 88
 kdc_tcp_ports = 88

[realms]
 MLADEN-TRAMPIC-SRB-1989.SG = {
  acl_file = /var/kerberos/krb5kdc/kadm5.acl
  dict_file = /usr/share/dict/words
  key_stash_file = /var/kerberos/krb5kdc/stash
  admin_keytab = /var/kerberos/krb5kdc/kadm5.keytab
  supported_enctypes = aes128-cts:normal arcfour-hmac:normal 
  max_life = 1d
  max_renewable_life = 7d
  default_principal_flags = +preauth, +forwardable
 }
```