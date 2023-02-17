# Difference between HTTPS and HTTP/2

__HTTP__ - A protocol used by clients (e.g. web browsers) to request resources from servers (e.g. web servers).

__HTTPS__ - A way of encrypting HTTP. It basically wraps HTTP messages up in an encrypted format using SSL/TLS.
The web is moving towards HTTPS more and more and web browsers are starting to put more and more warnings when a website is served over unencrypted HTTP.
Unless you have a very good reason not to, use HTTPS on any websites you create now.

Digging into HTTP more we have:

__HTTP/1.1__ - this was the prevalent format of HTTP until recently. It is a text-based protocol and has some inefficiencies in it - 
especially when requesting lots of resources like a typical web page. HTTP/1.1 messages can be unencrypted (where web site addresses start http://)
or encrypted with HTTPS (where web site address start with https://). The client uses the start of the URL to decide which protocol to use,
usually defaulting to http:// if not provided.

__HTTP/2__ - a new version of HTTP released in 2015 which addresses some of the performance issues by moving away from a text based protocol
to a [binary protocol where each byte is clearly defined][1]. This is easier to parse for clients and servers, leaves less room for errors
and also allows [multiplexing][2]. HTTP/2, like HTTP/1.1, is available over unencrypted (http://) and encrypted (https://) channels
but web browsers only support it over HTTPS, where it is decided whether to use HTTP/1.1 or HTTP/2 as part of the HTTPS negotiation
at the start of the connection.

[HTTP/2 is used by about a third of all websites at the time of writing][3] (up to 50% of websites as of Jan 2020, and [67% of website requests][4]).
However not all clients support HTTP/2 so you should support HTTP/1.1 over HTTPS and HTTP/2 over HTTPS where possible
(I believe node automatically does this for you when using the http module). I do not believe HTTP/1.1 will be retired any time soon.
You should also consider supporting HTTP/1.1 over unencrypted HTTP and then redirect to HTTPS version (which will then use HTTP/1.1 or HTTP/2
as appropriate). A web server like Apache or Nginx in front of Node makes this easy.

HTTP/3 - the next version of HTTP, currently under development. It is expected to be finalised in 2020 though it will likely be late 2020 or even 2021
before you see this widely available in web servers and languages like node. It will be built on top of a UDP-based transport called
QUIC (rather than the TCP-based protocol that HTTP/1.1 and HTTP/2 are based on top of). It will include part of HTTPS in the protocol so HTTP/3
will only be available over HTTPS.

In short you should use HTTP/1.1 over HTTPS, should consider HTTP/2 as well if easy to implement (not always possible as not quite ubiquitous yet -
but getting there) and in future you might be using HTTP/3.

I suggest you get a firm understanding of all of these technologies (except maybe HTTP/3 just yet) if you want to do web development.
It will stand you in good stead.

[1]: https://stackoverflow.com/questions/58498116/why-is-it-said-that-http2-is-a-binary-protocol
[2]: https://stackoverflow.com/questions/36517829/what-does-multiplexing-mean-in-http-2/
[3]: https://w3techs.com/technologies/details/ce-http2/all/all
[4]: https://httparchive.org/reports/state-of-the-web#h2

> <https://stackoverflow.com/questions/53488601/what-is-difference-between-https-and-http-2>
