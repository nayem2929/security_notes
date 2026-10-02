Hyper Text Transfer Protocol is used whenever a client requests a web page from the internet. 
URL (Unified Resource Locator) is essentially the instructions sent to the server whenever said request is made. Some features include:
![[Screenshot 2026-06-02 223315.png]]
Scheme: HTTP, HTTPS, FTP etc.
User: For authentication
Host/Domain: The actual web address of the server
Port: 80, commonly used for HTTP, 443 for HTTPS. More info here: [[6_Port_Forwarding_Firewalls_and_VPNs.md]]
Path: Name or location of the resource
Query String: Extra info for specifying
Fragment: Sometimes used for highlighting specific parts of a web-page

**HTTP methods**
Functions in web-server language. Common methods are:
GET: To obtain info from the website.
POST: To submit new info/create new record
PUT: To update existing records
DELETE: To delete info/records

**HTTP Status Codes**
Below is a list of status code ranges and their meaning:
100-199: Information response. Sent when part of the request was received and rest is awaiting confirmation.
200-299: Successful connection.
300-399: Redirection.
400-499: Client side issues.
500-599: Server side issues
*Common Codes:*
200 - OK
201 - Created: Sent when a new record(User info/blog post) has been successfully uploaded.
301 - Moved permanently
302 - Found: Moved temporarily
400 - Bad request: Protocol mismatch, insecure connection etc.
401 - Not authorized: Log in to access
403 - Forbidden: Unable to access as the current user
404 - Page not found
405 - Method not allowed: Client request vs. server expectation mismatch.
500 - Internal service error
503 - Service Unavailable

**Headers**:
Additional bits of data sent with both HTTP request and response to ensure a smoother experience for the client. Common examples of request headers include:
*Host*: To specify which service is being requested.
*User-Agent*: Browser software and version number to help with the formatting.
*Content-Length*: To ensure no data is lost.
*Accept-Encoding*: Which compression methods were used.
Cookie: To remember the user.
Some examples of response headers:
*Set-Cookie*: Which info is being saved
*Cache-Control*: How long should the browser cache the content for.
*Content-Type*: Self-explanatory, helps with processing.
*Content-Encoding*: Server-side encoding.

**Cookies**:
Little pieces of data stored in the device and sent with every request; mainly used for authentication