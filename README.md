This JWT example taken from the internet - 
https://medium.com/swlh/spring-boot-security-jwt-hello-world-example-b479e457664c.

The description of each of the pieces of the JWT:
* The JWT is divided into three distinct pieces each URL-encoded base64.
    * Header
    * Payload
    * Signature

* Header - when decoded contains information about how the JWT was signed. 
For example, {"alg": "HS256"} shows the JWT was signed with HMAC (key-hashed message authentication code or
hash-based message authentication code) using SHA-256 (a secure cryptographic hash algorithm, which has
a digest length of 256 bits).

* Payload - when decoded shows a number of key-value pairs, the keys of which are called "Claims". The JWT
spec defines seven registered claims.
    * iss - Issuer
    * sub - Subject
    * aud - Audience
    * exp - Expiration
    * nbr - Not Before
    * iat - Issued at
    * jit - JWT ID

    In addition to any number of the registered claims in the payload, one can add custom claims but payload
    length is a consideration.
    
* Signature - created by taking the header followed by 'dot' followed by the payload then passing through the
specified algorithm in the header along with a known secret, which is always a byte array.

The concepts of the JWT:
   * JWT can be used as tokens since they are URL safe, encoded and cryptographically signed strings.
   * a compact and self-contained way to transmit information between parties using JSON strings.
   * a cryptically signed JWT token can be verified thereby providing proof that the token has not
   been tampered with.
   * The signature can be verified, and the information encoded in the JWT can be used to confirm its
   validity.
   * The string representation of the JWT must match what's stored on the server side and has not expired
   by inspecting the "exp" claim. Inspecting the "exp" claim saves the server from maintaining additional
   state.
