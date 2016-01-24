# Using Swagger to tame HTTP/JSON interfaces


**Presenter:** John Billings<br />
**Audience:** Beginner<br />
**Topic:** Developer

There are many advantages to standardizing on HTTP/JSON interfaces for services: developer familiarity, mature tooling for caching and loading balancing, and ease of debugging.  However, one significant disadvantage is that there is no standard way of defining interfaces.  The open source Swagger project addresses this issue by providing an open source specification language and tooling for HTTP/JSON interfaces.

In this talk we describe how we have adopted Swagger at Yelp in order to tame our growing ecosystem of HTTP/JSON services.  In particular, we cover the following topics:

Real world Swagger specifications:  we show how to use the Swagger language to specify common HTTP/JSON interface idioms, as well as how to extend it to handle custom datatypes.

Automatic generation of client libraries:  given a Swagger specification for a service, we show how to use the Swagger tooling to automatically generate client libraries for a range of different programming languages.

Service interface directory:  it can be difficult for developers to keep track of growing numbers of services within an organization.  We show how to aggregate all Swagger specifications and present them in a unified way through a directory service.

Testing:  we show how to use Swagger specifications to help verify the behavior of clients and services.

**Presentation:** [Slides](presentation.pdf)<br />
**Room:** Ballroom C<br />
**Time:** Sunday, January 24, 2016 - 13:30 to 14:30
