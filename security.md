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
