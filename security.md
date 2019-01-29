## Kerkchoffs Principle
https://en.wikipedia.org/wiki/Kerckhoffs%27s_principle

## XSS Protection

TODO: Check if the app renders html/script in json response.

## ZAP 

Zed-Attack-Proxy. Try to implement a basic dockerized version, and add it into the pipeline.

## CSP 

Short for Content-Security-Policy. Look into how to implement a basic policy:

```golang
w.Header().Add("Content-Security-Policy", "default-src 'self'")
```

## CSRF

```golang
if !checkCSRFHeader(r.Header.Get("X-CSRF-TOKEN")) {
    w.WriteHeader(http.StatusNotAcceptable)
    w.Write([]byte("Invalid CSRF Token"))
}
```

## Cookie

Set the option `SameSite=strict`.

## Clickjacking

```golang
w.Header().Add("X-Frame-Options", "SAMEORIGIN")
```

## Basic Auth

```golang
if r.Header.Get("Authorization")[0:5] != "Basic" {
    // Error
}

token = r.Header.Get("Authorization")[7:]
tokenDecoded, err := base64.StdEncoding.DecodeString(token)
username := tokenDecoded[0:strings.Index(":")]
password := tokenDecoded[strings.Index(":") + 1:]
w.Header().Set("WWW-Authenticate", `Basic-Realm=""`)
```

## NSP

Checkout node-security platform

## Ops Access

Add a cron job to randomize the credentials daily and email/slack it to the user.

## Client Side

When logging in, store the token in the application state rather than local storage. When user closes the application, store it in the local storage.

The next time the user login, get the token from the localStorage, store it in the application state and delete it from the localStorage.


## Allow passwords to auto-rotate by randomly generating a unique password

```
# Generate a hashed credentials
echo -n "username:password" | shasum -a 256

# Pass this in as an environment variable CREDENTIALS

# In the application, compare the hashed username:password with the credentials
```
