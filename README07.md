 # Bearer Authorization:
## JSON Web Token (JWT)
### What is JSON Web Token?
is an open standard (RFC 7519) that defines a compact and self-contained way for securely transmitting information between parties as a JSON object. 

- can be signed using a secret (with the HMAC algorithm) or a public/private key pair using RSA or ECDSA.
- can be encrypted to also provide secrecy between parties
### When you need JSON Web Tokens?
- Authorization
- Information Exchange
###  JSON Web Token structure?
- Header:
* Type of the token
* Signing algorithm being used, such as HMAC SHA256 or RSA.
-----------------------------------------------------------------
- Payload: which contains the claims. Claims are statements about an entity (typically, the user) and additional data
three type of claims:
* registered
* public
* private claims
-------------------------------------------------------------------------------

- Signature: To create the signature part you have to take the encoded header, the encoded payload, a secret, the algorithm specified in the header, and sign that.
JSON Web Tokens consist of three parts separated by dots (.)

JWT how to they are secure?
JWTs can be either signed, encrypted or both. If a token is signed, but not encrypted, everyone can read its contents, but when you don't know the private key, you can't change it. Otherwise, the receiver will notice that the signature won't match anymore.


References:

[jwtint](https://jwt.io/introduction/)

[Are JWTs Secure?](https://stackoverflow.com/questions/27301557/if-you-can-decode-jwt-how-are-they-secure)


[Home page](README.md)