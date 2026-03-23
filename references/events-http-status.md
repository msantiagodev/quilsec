# HTTP Status Codes (Security Context)
> Source: HTTP Status Codes | Events: 30


## Index

- [http](#http)


### http

**200** -- OK
  OK - Request succeeded

**201** -- Created
  Created - Resource created

**204** -- No Content
  No Content - Request succeeded, no body

**301** -- Moved Permanently
  Moved Permanently - Redirect (check for open redirect)

**302** -- Found
  Found - Temporary redirect (check for open redirect)

**304** -- Not Modified
  Not Modified - Cached response

**400** -- Bad Request
  Bad Request - Malformed request (possible injection attempt)

**401** -- Unauthorized
  Unauthorized - Authentication required/failed

**403** -- Forbidden
  Forbidden - Access denied (insufficient permissions)

**404** -- Not Found
  Not Found - Resource not found (possible enumeration/scanning)

**405** -- Method Not Allowed
  Method Not Allowed - HTTP method not permitted

**408** -- Request Timeout
  Request Timeout - Connection timed out

**413** -- Payload Too Large
  Payload Too Large - Request body exceeds limit

**414** -- URI Too Long
  URI Too Long - URL exceeds limit (possible buffer overflow attempt)

**429** -- Too Many Requests
  Too Many Requests - Rate limit exceeded (possible brute force/DDoS)

**431** -- Request Header Fields Too Large
  Request Header Fields Too Large - Header injection attempt

**444** -- No Response (nginx)
  No Response (nginx) - Connection closed without response (bot mitigation)

**451** -- Unavailable For Legal Reasons
  Unavailable For Legal Reasons - Legally restricted content

**499** -- Client Closed Request (nginx)
  Client Closed Request (nginx) - Client disconnected before response

**500** -- Internal Server Error
  Internal Server Error - Server-side error (possible exploitation success)

**502** -- Bad Gateway
  Bad Gateway - Upstream server error

**503** -- Service Unavailable
  Service Unavailable - Server overloaded or in maintenance (possible DDoS effect)

**504** -- Gateway Timeout
  Gateway Timeout - Upstream timeout

**520** -- Web Server Returned Unknown Error (Cloudflare)
  Web Server Returned Unknown Error (Cloudflare)

**521** -- Web Server Is Down (Cloudflare)
  Web Server Is Down (Cloudflare)

**522** -- Connection Timed Out (Cloudflare)
  Connection Timed Out (Cloudflare)

**523** -- Origin Is Unreachable (Cloudflare)
  Origin Is Unreachable (Cloudflare)

**524** -- A Timeout Occurred (Cloudflare)
  A Timeout Occurred (Cloudflare)

**525** -- SSL Handshake Failed (Cloudflare)
  SSL Handshake Failed (Cloudflare)

**530** -- Origin DNS Error (Cloudflare)
  Origin DNS Error (Cloudflare)
