# Authentication & Production Server

## JSON Web Token

+ JSON Web Token (JWT) is an open standard that defines a compact and self-contained way for securely transmitting information between parties as a JSON object. This information can be verified and trusted because it is digitally signed. 
+ JWTs can be signed using a secret (with the HMAC algorithm) or a public/private key pair using RSA or ECDSA.
+ Signed tokens can verify the integrity of the claims contained within it, while encrypted tokens hide those claims from other parties. 
+ When tokens are signed using public/private key pairs, the signature also certifies that only the party holding the private key is the one that signed it.

### When should you use JSON Web Tokens?

+ Here are some scenarios where JSON Web Tokens are useful:
  + **Authorization:** This is the most common scenario for using JWT. Once the user is logged in, each subsequent request will include the JWT, allowing the user to access routes, services, and resources that are permitted with that token. Single Sign On is a feature that widely uses JWT nowadays, because of its small overhead and its ability to be easily used across different domains.
  + **Information Exchange:** JSON Web Tokens are a good way of securely transmitting information between parties. Because JWTs can be signed—for example, using public/private key pairs—you can be sure the senders are who they say they are. Additionally, as the signature is calculated using the header and the payload, you can also verify that the content hasn't been tampered with.

### What is the JSON Web Token structure?
+ In its compact form, JSON Web Tokens consist of three parts separated by dots (.), which are:
  + **Header**
    + The header typically consists of two parts: 
      + the type of the token, which is JWT,
      + the signing algorithm being used, such as HMAC SHA256 or RSA.
        + For example:
          + `{ "alg": "HS256",`
          + `"typ": "JWT" }`
        + Then, this JSON is Base64Url encoded to form the first part of the JWT.
}
  + **Payload**
    + The second part of the token is the payload, which contains the claims. Claims are statements about an entity (typically, the user) and additional data. There are three types of claims: 
      + **Registered**
        +  Registered claims: These are a set of predefined claims which are not mandatory but recommended, to provide a set of useful, interoperable claims. Some of them are: iss (issuer), exp (expiration time), sub (subject), aud (audience), and others.
        +  Notice that the claim names are only three characters long as JWT is meant to be compact.
      + **Public**
        + Public claims: These can be defined at will by those using JWTs. But to avoid collisions they should be defined in the IANA JSON Web Token Registry or be defined as a URI that contains a collision resistant namespace.
      + **Private**
        + Private claims: These are the custom claims created to share information between parties that agree on using them and are neither registered or public claims.
    + An example payload could be:
      + `{ "sub": "1234567890",`
      + `"name": "John Doe",`
      + `"admin": true }`
    + The payload is then Base64Url encoded to form the second part of the JSON Web Token.
  + **Signature**
    + To create the signature part you have to take the encoded header, the encoded payload, a secret, the algorithm specified in the header, and sign that.
    + For example if you want to use the HMAC SHA256 algorithm, the signature will be created in the following way:
      + `HMACSHA256(`
      + `base64UrlEncode(header) + "." +`
      + `base64UrlEncode(payload),secret)`
    + The signature is used to verify the message wasn't changed along the way, and, in the case of tokens signed with a private key, it can also verify that the sender of the JWT is who it says it is.

## How JWT Works?

+ The JWT is just an authorization token that should be included in all requests
+ The JWT is acquired by exchanging an username + password for an access token and an refresh token.
  + The **access token** is usually short-lived (expires in 5 min or so, can be customized though).
  + The **refresh token** lives a little bit longer (expires in 24 hours, also customizable). It is comparable to an authentication session. After it expires, you need a full login with username + password again.
    + At first glance the refresh token may look pointless, but in fact it is necessary to make sure the user still have the correct permissions. 
    + If your access token have a long expire time, it may take longer to update the information associated with the token. That’s because the authentication check is done by cryptographic means, instead of querying the database and verifying the data. So some information is sort of cached.

