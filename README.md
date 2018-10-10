# iOS Development Guides
Library of useful links, tips and hacks that I use. 

## Certificates

### Push certificates

#### Create
[Create push certificate guide](https://medium.com/@ankushaggarwal/generate-apns-certificate-for-ios-push-notifications-85e4a917d522)

#### Convert to .pem
<code>openssl pkcs12 -in pushcert.p12 -out pushcert.pem -nodes -clcerts</code>
