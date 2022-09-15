# saml2
A Spring Security Service Provider

## Start Keycloak
`sudo systemctl start docker`
`docker run -p 8080:8080 -e KEYCLOAK_ADMIN=admin -e KEYCLOAK_ADMIN_PASSWORD=admin quay.io/keycloak/keycloak:19.0.2 start-dev`

## Generate SP-Certificate
`openssl req -x509 -newkey rsa:2048 -keyout credentials/private_p12.key -out credentials/public_p12.crt -days 3650 -nodes`

## Convert to PKCS#12
`openssl pkcs12 -export -out sp.p12 -inkey private_p12.key -in public_p12.crt -certfile public_p12.crt -name oose `


