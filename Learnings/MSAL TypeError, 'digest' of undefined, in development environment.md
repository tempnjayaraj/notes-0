---
type: learning
last-modified-date: 23-02-2023
creation-date: 21-02-2023
parent-topic: MSAL
tags: Authentication
---

```ad-error
When we're building our Angular SPA for localhost it works perfectly.

On our dev environment, this error creeps into the DevTool console and breaks everything: ERROR Error: Uncaught (in promise): TypeError: Cannot read property 'digest' of undefined
```javascript
TypeError: Cannot read property 'digest' of undefined
    at N (auth0-spa-js.production.js:1)
    at ie.<anonymous> (auth0-spa-js.production.js:1)
    at Generator.next (<anonymous>)
    at auth0-spa-js.production.js:1
    at new ZoneAwarePromise (zone-evergreen.js:876)
    at t (auth0-spa-js.production.js:1)
```

```ad-success
title:Solution
It's probably because your dev server is setup as an insecure origin.

The `digest` likely refers to `window.crypto.subtle.digest` of the [Web Crypto API](https://developer.mozilla.org/en-US/docs/Web/API/Web_Crypto_API). if you are using a Chromium-based browser, according to the the [Chromium Projects page here](https://www.chromium.org/blink/webcrypto), the `subtle` property can only be used in a secure origin:

> Access to the WebCrypto API is restricted to secure origins (which is to say https:// pages).
> 
> Note: In the spec, crypto.subtle is supposed to be undefined in insecure contexts

Because `digest` is a method of `subtle`, and `subtle` is `undefined`, you are getting this error.

We got the same error when using the [auth0-spa-js library](https://github.com/auth0/auth0-spa-js). It worked on localhost, not on our http staging site, but OK on our production https site.

If you aren't in a secure origin, try making your dev environment secure and then testing again (a self-signed certificate should do). As a reminder, [secure origins](https://www.chromium.org/Home/chromium-security/security-faq#TOC-Which-origins-are-secure-) are:

> ## Which origins are "secure"?
> 
> Secure origins are those that match at least one of the following (scheme, host, port) patterns:
> 
> -   (https, *, *)
> -   (wss, *, *)
> -   (*, localhost, *)
> -   (*, 127/8, *)
> -   (*, ::1/128, *)
> -   (file, *, —)
> -   (chrome-extension, *, —)
> 
> That is, secure origins are those that load resources either from the local machine (necessarily trusted) or over the network from a cryptographically-authenticated server.

I'm not sure if the [Auth0](https://auth0.com/) team have an SPA library that works in a non-secure origin (or plans to enable that capability in their latest SPA library), but their native JS libraries definitely do.
```
