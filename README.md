# vertx_jwt_auth_sample
Authentication using vertx jwt token


Simple main application

using RS256
private and public key to sign jwt token

token expires in 60 * 60 * 24 seconds

# generation of tokens


1. generate private key

openssl genrsa -out private.pem 2048

2.The standard JDK cannot read this file as is, so we must convert it to PKCS8 format first:

openssl pkcs8 -topk8 -inform PEM -in private.pem -out private_key.pem -nocrypt

3.public key
openssl rsa -in private.pem -outform PEM -pubout -out public.pem

took from (https://vertx.io/docs/vertx-auth-jwt/java/)
