# SSL

### Self Signed

    openssl req -x509 -newkey rsa:2048 -keyout key.pem -out cert.pem -days XXX

Extra opts:

* Add `-nodes` for no DES passphrase encryption.
* Add `-subj "/C=US/ST=Colorado/L=Denver/O=Company Name/OU=Org/CN=www.example.com"`

### Signed

Generate CSR

    openssl req \
    -newkey rsa:2048 -nodes \
    -keyout domain.key \
    -out domain.csr
