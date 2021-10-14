# RS256 and HS256 – signing tokens for Auth0

RS256 generates an asymmetric signature, whereas HS256 generates a symmetric MAC code. Simply put HS256 requires both parties to hold a client secret. The asymmetric signature that RS256 produces is signed with a private key and verified with a public key. This verifies that JWT is the primary sender as they hold the private key.

JSON Web Keys (a publicly held key) are used of verifying the asymmetric signatures signed by RS256. Here's an example of a JWKS (JSON Web Key Set), which is a JSON data structure used for holding several JSWKs (JSON Web Keys).

```JSON
{
"keys": [
  {
    "alg": "RS256",
    "kty": "RSA",
    "use": "sig",
    "x5c": [
      "MIIC+DCCAeCgAwIBAgIJBIGjYW6hFpn2MA0GCSqGSIb3DQEBBQUAMCMxITAfBgNVBAMTGGN1c3RvbWVyLWRlbW9zLmF1dGgwLmNvbTAeFw0xNjExMjIyMjIyMDVaFw0zMDA4MDEyMjIyMDVaMCMxITAfBgNVBAMTGGN1c3RvbWVyLWRlbW9zLmF1dGgwLmNvbTCCASIwDQYJKoZIhvcNAQEBBQADggEPADCCAQoCggEBAMnjZc5bm/eGIHq09N9HKHahM7Y31P0ul+A2wwP4lSpIwFrWHzxw88/7Dwk9QMc+orGXX95R6av4GF+Es/nG3uK45ooMVMa/hYCh0Mtx3gnSuoTavQEkLzCvSwTqVwzZ+5noukWVqJuMKNwjL77GNcPLY7Xy2/skMCT5bR8UoWaufooQvYq6SyPcRAU4BtdquZRiBT4U5f+4pwNTxSvey7ki50yc1tG49Per/0zA4O6Tlpv8x7Red6m1bCNHt7+Z5nSl3RX/QYyAEUX1a28VcYmR41Osy+o2OUCXYdUAphDaHo4/8rbKTJhlu8jEcc1KoMXAKjgaVZtG/v5ltx6AXY0CAwEAAaMvMC0wDAYDVR0TBAUwAwEB/zAdBgNVHQ4EFgQUQxFG602h1cG+pnyvJoy9pGJJoCswDQYJKoZIhvcNAQEFBQADggEBAGvtCbzGNBUJPLICth3mLsX0Z4z8T8iu4tyoiuAshP/Ry/ZBnFnXmhD8vwgMZ2lTgUWwlrvlgN+fAtYKnwFO2G3BOCFw96Nm8So9sjTda9CCZ3dhoH57F/hVMBB0K6xhklAc0b5ZxUpCIN92v/w+xZoz1XQBHe8ZbRHaP1HpRM4M7DJk2G5cgUCyu3UBvYS41sHvzrxQ3z7vIePRA4WF4bEkfX12gvny0RsPkrbVMXX1Rj9t6V7QXrbPYBAO+43JvDGYawxYVvLhz+BJ45x50GFQmHszfY3BR9TPK8xmMmQwtIvLu1PMttNCs7niCYkSiUv2sc2mlq1i3IashGkkgmo="
    ],
    "n": "yeNlzlub94YgerT030codqEztjfU_S6X4DbDA_iVKkjAWtYfPHDzz_sPCT1Axz6isZdf3lHpq_gYX4Sz-cbe4rjmigxUxr-FgKHQy3HeCdK6hNq9ASQvMK9LBOpXDNn7mei6RZWom4wo3CMvvsY1w8tjtfLb-yQwJPltHxShZq5-ihC9irpLI9xEBTgG12q5lGIFPhTl_7inA1PFK97LuSLnTJzW0bj096v_TMDg7pOWm_zHtF53qbVsI0e3v5nmdKXdFf9BjIARRfVrbxVxiZHjU6zL6jY5QJdh1QCmENoejj_ytspMmGW7yMRxzUqgxcAqOBpVm0b-_mW3HoBdjQ",
    "e": "AQAB",
    "kid": "NjVBRjY5MDlCMUIwNzU4RTA2QzZFMDQ4QzQ2MDAyQjVDNjk1RTM2Qg",
    "x5t": "NjVBRjY5MDlCMUIwNzU4RTA2QzZFMDQ4QzQ2MDAyQjVDNjk1RTM2Qg"
  }
]}
```

The key's properties represent:

* `alg`: refers to the algorithm
* `kty`: is the key type (RSA)
* `use`: is how the key is meant to be used
* `x5c`: is the x509 certificate chain
* `e`: is the exponent for a standard pem
* `n`: is the modulus for the standard pem
* `kid`: is the unique identifier for the key
* `x5t`: is the thumbprint of the x.509 cert

## Vocabulary

* `MAC`: Message Authentication Code [[4]](https://en.wikipedia.org/wiki/Message_authentication_code)
  * These are used to verify if the message came from the stated sender
  * To verify these messages, both clients need to hold a secret key

* `Signature`:
  * "A digital signature protects bits in a token from tampering. If the bits are changed or tampered with, the signature will no longer be able to be verified and it will be rejected." [[1]](https://auth0.com/docs/glossary)

* `JSWK`: JSON Web Key
  * Is a cryptographic key used for verifying JSON Web Tokens(JWT)[[2]](https://auth0.com/docs/tokens/json-web-tokens/json-web-key-sets)[[5]](https://datatracker.ietf.org/doc/html/rfc7517)

* `JWKS`: JSON Web Key Sets
  * A JSON data structure holding several public cryptographic keys[[5]](https://datatracker.ietf.org/doc/html/rfc7517)

* `Authorization Server`:
  * "A server that contributes to the defining the boundaries of a user's access"[[1]](https://auth0.com/docs/glossary)
  * Signs tokens using a private key

## Resources

1. [Auth0 Identity Glossary](https://auth0.com/docs/glossary)
1. [JSON Web Key Sets](https://auth0.com/docs/tokens/json-web-tokens/json-web-key-sets)
1. [Navigating RS256 and JWKS](https://auth0.com/blog/navigating-rs256-and-jwks/)
1. [Message Authentication Code](https://en.wikipedia.org/wiki/Message_authentication_code)
1. [RFC7517 – JSON Web Keys](https://datatracker.ietf.org/doc/html/rfc7517)