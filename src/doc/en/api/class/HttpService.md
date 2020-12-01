# Summary
Allows a server to make HTTP requests.

# Details
Requests are made with the [RequestAsync][RA] function. The [GetAsync][GA] and
[PostAsync][PA] functions may also be used as shorthand for specific HTTP
methods, but these are discouraged in favor of RequestAsync.

## Headers
Each request function can receive custom headers to be included in the request.
However, the following headers are locked, and cannot be included by the caller:

Header              | Notes
--------------------|------
`Accept-Encoding`   |
`Connection`        |
`Content-Encoding`  | Allowed by RequestAsync.
`Content-Length`    |
`Content-Type`      | Allowed by RequestAsync.
`Expect`            |
`Forwarded`         |
`Host`              |
`Proxy-Connection`  |
`User-Agent`        |
`Via`               |
`X-Att-Deviceid`    |
`X-Forwarded-For`   |
`X-Forwarded-Host`  |
`X-Forwarded-Proto` |
`X-Wap-Profile`     |

Attempting to include a locked header causes the following error to be thrown:

	Header "HEADER" is not allowed!

Where `HEADER` is the name of the header.

By default, HttpService includes a number of headers along with each request:

Header            | Value             | Notes
------------------|-------------------|------
`Accept`          | `*/*`             |
`Accept-Encoding` | `gzip, deflate`   |
`Cache-Control`   | `no-cache`        |
`Content-Length`  | (body length)     | Length of the given body. Not included if the body is empty.
`Host`            | (URL host)        | Host part of the given URL. Not included if the URL has no host (e.g. an IP is used instead).
`Roblox-Id`       | (place ID)        | Corresponds to [DataModel.PlaceId](class:DataModel/PlaceId).
`User-Agent`      | (user agent)      | Depends on the current peer.

Such headers that are not locked can be overridden. These headers are included
with every request, except for `Content-Length`, which is included with all
methods except `GET` and `HEAD`. Certain request functions may include other
headers.

Requests are sent with a specific user agent that depends on the current peer:

Peer   | User agent
-------|-----------
Server | `RobloxGameCloud/1.0 (+http://www.roblox.com)`
Studio | `RobloxStudio/WinInet`

Header names are case-insensitive. If multiple equivalent headers are specified,
only one is chosen (which header is chosen is undefined).

## Limits
Only servers can make requests. If a request function is called on a client, the
following error is thrown:

	Http requests can only be executed by game server

The URL schemes allowed by HttpService are `http` and `https`. Domains are
filtered using a blacklist; requests to Roblox domains are disallowed, while
requests to any other domains are allowed. If a URL is disallowed or otherwise
invalid, then the following error will be thrown:

	URL: Trust check failed

Where `URL` is the given URL. Some request functions may throw a more specific
error instead.

Requests made by HttpService are rate-limited to 500 requests per minute. When a
request is made after the limit is exceeded, the following error is thrown:

	Number of requests exceeded limit

There is a limit to the number of concurrent requests that can be made by
HttpService. When a request is made, it is put into a "slot", and remains there
until the request is resolved. When all slots are occupied, new requests will
block until a slot becomes available.

## Other errors
If a given URL is empty, then the following error will be thrown:

	Empty URL

If the HTTP client encounters an error while making a request, then it will be
thrown as the following:

	HttpError: MESSAGE

Where `MESSAGE` describes the error. For example, if the DNS server was unable
to resolve the given domain, the error will be `HttpError: DnsResolve`.

# Members

## GenerateGUID
Generates a Universally Unique Identifier (UUID).

### Details
GenerateGUID returns a UUID version 4 string as defined by [RFC 4122][rfc4122],
which is generated pseudo-randomly.

If *wrapInCurlyBraces* is true, then the returned string will begin and end with
curly braces (`{}`). If false, then the braces are omitted.

[rfc4122]: https://tools.ietf.org/html/rfc4122

## GetAsync
[GA]: member:GetAsync

Sends a GET request to a website.

*See the [HttpService Details section](#details) for information regarding all
request functions.*

### Details
GetAsync makes a request using the GET method. *url* is the URL to which the
request will be sent. If *nocache* is true, then the `Cache-Control` header of
the request will be set to `no-cache`. *headers* is an optional table of HTTP
headers.

<!-- CITE:nocache:https://devforum.roblox.com/t/366643/2 -->

If successful, GetAsync returns the body of the response.

*headers* is an optional table for specifying additional headers to be included
with the request. Each entry must be a key-value pair, where the key is a string
indicating a header name, and the value is a string indicating the header value.

If the response returns a non-successful status code, then the status is thrown
as an error:

	HTTP 000 (MESSAGE)

Where `000` is the status code, and `MESSAGE` is the status message.

#### Bugs
`Cache-Control` is set to `no-cache` regardless of the *nocache* argument.

## GetHttpEnabled
## HttpEnabled
Determines whether HttpService can make requests.

### Details
If false, then [GetAsync](member:GetAsync), [PostAsync](member:PostAsync), and
[RequestAsync](member:RequestAsync) will throw the following error:

	Http requests are not enabled. Enable via game settings

## JSONDecode
Decodes a JSON-formatted string into a value. The string is decoded according to
[RFC8259][RFC8259].

The following JSON types are converted into a corresponding Lua type:
- A null is decoded into a Lua nil.
- A boolean is decoded into a Lua boolean.
- A number is decoded into the nearest representing Lua number.
- A string is decoded into a Lua string.
- An array is decoded into a Lua table, where each entry in the array is an
  entry in the table, with indices starting at 1.
- An object is decoded into a Lua table, where each field of the object is a
  key-value pair in the table.

[RFC8259]: https://tools.ietf.org/html/rfc8259

## JSONEncode
Encodes *input* into a JSON-formatted string. *input* cannot be nil.

The following types are encoded. Other types are encoded as `null`.

### Boolean
Mapped directly to a JSON boolean.

### Number
Encoded as a JSON number. Infinity and NaN are encoded as `null`.

### String
Encoded as a UTF-8 string. The following characters are escaped:

Character       | Code | Escape
----------------|------|-------
Backspace       | 0x08 | `\b`
Horzontal tab   | 0x09 | `\t`
Line feed       | 0x0A | `\n`
Form feed       | 0x0C | `\f`
Carriage Return | 0x0D | `\r`
Double quote    | 0x22 | `\"`
Backslash       | 0x5C | `\\`

Control characters (0x00 - 0x1F) not in this list are escaped as `\u00XX`, where
`XX` is the character code in hexadecimal.

Other unicode characters are encoded as-is. A malformed unicode character within
any encoded string causes the following error to be thrown:

	Can't convert to JSON

### Table
A table is encoded as either a JSON array or a JSON object, which depends on the
content. A table is interpreted as an array if it is empty, or if it contains
the integer 1 as a key. Otherwise, it is treated as an object.

Tables are encoded recursively. If a table that is being or has already been
encoded is traversed, the following error is thrown:

	tables cannot be cyclic

#### Array
An array encodes integer keys from 1 to the length of the table. Other keys are
ignored, and are not traversed.

#### Object
An object encodes certain types of keys to JSON strings. Keys are encoded in the
same way as string values.

The method for encoding non-string keys is undefined. It is possible that such a
key will be converted to a string, throw an error, or be ignored entirely.

## PostAsync
[PA]: member:PostAsync

Sends a POST request to a website.

### Details
PostAsync makes a request using the POST method. *url* is the URL to which the
request will be sent, and *data* is the body of the request.

*content_type* optionally sets the `Content-Type` header according to the given
[HttpContentType][HCT] value.

*compress* optionally determines whether the body will be compressed with gzip
encoding. The body will be sent compressed only if the compressed content is
shorter than the uncompressed content. If compressed, then the
`Content-Encoding` header is set to `gzip`.

*headers* is an optional table for specifying additional headers to be included
with the request. Each entry must be a key-value pair, where the key is a string
indicating a header name, and the value is a string indicating the header value.

If the response returns a non-successful status code, then the status is thrown
as an error:

	HTTP 000 (MESSAGE)

Where `000` is the status code, and `MESSAGE` is the status message.

The length of *data* cannot be greater than or equal to 1024KB (maximum is
1,023,999 bytes). If *data* is too large, then the following error will be
thrown:

	Post data too large. Limit: 1024 KB. Post size: SIZE KB

Where `SIZE` is the length of *data* in kilobytes. Note that [RequestAsync][RA]
does not have this limit.

[HCT]: enum:HttpContentType

## RequestAsync
[RA]: member:RequestAsync

Sends an HTTP request and receives the response.

*See the [HttpService Details section](#details) for information regarding all
request functions.*

### Details
*requestOptions* specifies the content of the request using the following
fields:

Field     | Type       | Required | Description
----------|------------|----------|------------
`Body`    | string     | no       | The body of the request.
`Headers` | Dictionary | no       | A table containing headers to send with the request.
`Method`  | string     | no       | The HTTP request method to be used. Defaults to `GET`.
`Url`     | string     | yes      | The URL to which the request will be sent.

If `Url` has a blacklisted Roblox domain, then the following error will be
thrown:

	HttpService is not allowed to access ROBLOX resources

`Method`, which is case-sensitive, must be one of `GET`, `HEAD`, `POST`, `PUT`,
`DELETE`, `TRACE`, `OPTIONS`, `CONNECT`, or `PATCH`. If `Method` is `GET` or
`HEAD`, and `Body` is specified, then the following error will be thrown:

	Invalid request options, Body should be empty for 'GET' or 'HEAD' method

RequestAsync blocks until a response has been received and processed, or the
request has timed out.

Each entry to the `Headers` table must be a key-value pair, where the key is a
string indicating a header name, and the value is a string indicating the header
value.

#### Response
If successful, RequestAsync returns response data as a table with the following
fields:

Field           | Type       | Description
----------------|------------|------------
`Body`          | string     | The body of the response.
`Headers`       | Dictionary | A table of response headers.
`StatusCode`    | int        | The HTTP status code of the response.
`StatusMessage` | string     | A readable message corresponding to the StatusCode.
`Success`       | bool       | Whether or not the request succeeded.

The response Headers field is a table, where each key is a string indicating a
header name, and the value is a string indicating the header value. Header
names, which are case-insensitive, are normalized to lowercase. If a header was
sent multiple times, the value of the latest such header is selected.

## RequestInternal
## SetHttpEnabled
## UrlEncode
