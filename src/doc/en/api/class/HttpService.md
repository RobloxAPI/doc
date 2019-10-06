# Summary
Allows a server to make HTTP requests.

# Details
The URL schemes allowed by HttpService are `http` and `https`. Domains are
filtered using a blacklist. Generally, requests to any URL are allowed, while
requests to Roblox domains are disallowed. If a URL is disallowed or otherwise
invalid, then the following error will be thrown:

	URL: Trust check failed

Where `URL` is the given URL.

If the URL is empty, then the following error will be thrown:

	Empty URL

There is a limit to the number of concurrent connections made by HttpService.
This amount is subject to change, and so should not be relied upon. At least one
connection at a time is guaranteed.

# Members

## GenerateGUID
Generates a Universally Unique Identifier (UUID).

### Details
GenerateGUID returns a UUID version 4 string as defined by [RFC 4122][rfc4122],
which is generated pseudo-randomly.

If *wrapInCurlyBraces* is true, then the returned string will begin and end with
curly braces (`{...}`). If false, then the braces are omitted.

[rfc4122]: https://tools.ietf.org/html/rfc4122

## GetAsync
## GetHttpEnabled
## HttpEnabled
Determines whether requests are enabled.

### Details
If false, then [GetAsync](member:GetAsync), [PostAsync](member:PostAsync), and
[RequestAsync](member:RequestAsync) will throw the following error:

	Http requests are not enabled. Enable via game settings

## JSONDecode
## JSONEncode
## PostAsync
## RequestAsync
## RequestInternal
## SetHttpEnabled
## UrlEncode
