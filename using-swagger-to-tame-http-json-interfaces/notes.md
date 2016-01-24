HTTP/JSON is amazing

- requests
- HAProxy
- httplib
- Varnish
- simplejson
- curl
- Apache
- Pyramid
- Dropwizard
- jq
- NGINX

Write Spec DOCS

- Pro
    - It's easy to get started
    - People can comment if you use e.g. gdocs
    - Approachable by non-technical individuals
- Con
    - Implementation and spec can drift over time
    - It's easy to be imprecise

Switch to Thrift / Protocol Buffers / Avro /...

- Pro
    - More efficient on the wire
    - More efficient to decode than JSON
- Con
    - Cannot use L7 technologies such as HTTP caching
    - Difficult to debug on the wire
    - Variable quality of support across languages?

Write lots of integration tests

- Pro
    - You should already have (some) of the tests.
- Con
    - Final testing phase; slow to correct bugs at this stage
    - Integration tests take a (relatively) long time to run

Write client libraries

- The client library API becomes the spec for consumers

- Pro
    - Consumers don't need to worry about wire protocol
        - We've used this approach at Yelp, and it can work,
- Con
    - Lots of boilerplate
    - Manual validation
    - No spec for the wire protocol
    - Still need integration tests from clientlib / service ifc

Where do Swagger specs live?

- At Yelp we check them into the service codebase
- Serve from a well-known endpoints of the service

Modifying specs

- Swagger will not prevent you doing something bad
- You the programmer need to make sure that all spec changes are backwards compatible
- If you like living safely, only add new end-points

What can I do with a spec?

- Review an API
- Browse other specs
- Generate a client library
- Perform server-side validation
- Testing

Brief aside: Same-origin polic

- Only can interact with the same server you downloaded the resource from.
- Access-Control-Allow-Origin: http://swagger-ui

Swagger Client

```
from swagger_client import ApiClient
from swagger_)client import PetApi
client = ApiClient()
pet_api.client(client)
pet_api.get_pet_by_id(42)
```

```
# Yelp Module for Dynamic Swagger Clientk
Bravado.client import SwaggerClient
client = SwaggerClient.from_url('urlhere')
client.pet.getPetById(petId=42).result()
```

pyramid_swagger

- This project offers convenient tools for using Swagger to define and validate your intrfaces in a Pyramid app.

Testing with Swagger

- This is a fairly standard testing problem
- Your type checker can help here (if you have one:)
- Future work: add support for returning mock data
- Validate your responses as part of your testing
- Fairly easy if your service already contains a validator?
- Could also use an external validator

SwaggerHub

- Enter Swagger specs and see them
- Generate client libraries
- Share with other callaborators

Other spec langs:

- API Blueprint by Apiary
- I/O Docs by Mashery

Conclusions:

- Swagger provides an easy way to define JSON/HTTP interfaces for new and existing services
- Once you have an interface, you get lots of tooling 'fore free'
    - Automatic generation of clientlibs for many different languages
