appengine-go-recaptcha
============

About
-----

This package handles reCaptcha (http://www.google.com/recaptcha) form submissions in Go (http://golang.org/) on Google AppEngine.
If you are not using Google AppEngine please refer to the original app (https://github.com/dpapathanasiou/go-recaptcha)

Usage
-----

Download the package in your environment:

```
git clone github.com/ajite/appengine-go-recaptcha
```

To use it within your own code, import "github.com/ajite/appengine-go-recaptcha" and "appengine/urlfetch" call:

```
recaptcha.Init (recaptcha_private_key)
```

once, to set the reCaptcha private key for your domain, then:

```
recaptcha.Confirm (http_client,client_ip_address, recaptcha_challenge_field, recaptcha_response_field)
```

You can get the http client with the following code

```
c := appengine.NewContext(r)
client := urlfetch.Client(c)
```

for each reCaptcha form input you need to check, using the values obtained by reading the form's POST parameters.

The recaptcha.Confirm() function returns either true (i.e., the captcha was completed correctly) or false.

