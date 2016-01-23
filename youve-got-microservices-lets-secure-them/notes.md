# Keycloak

Integrated SSO and IDM for browser apps and RESTful web services.  Built on top of the OAuth 2.0, Open ID Connect, JSON Web Token (JWT) and SAML 2.0 specifications.  Keycloak has tight integration with a variety of platforms and has a HTTP security proxy service where we don't have tight integration.  Options are to deploy it with an existing app server, as a black-box appliance, or as an Openshift cloud service and/or cartridge.

[http://keycloak.jboss.org/](http://keycloak.jboss.org/)

## Features

- OpenID Connect and SAML 2.0 SSO and Single Log Out for browser applications
- Social Broker.  Enable Google, Facebook, Yahoo, Twitter social login with no code required.
- Identity Broker.  Delegate to an external SAML 2.0 or OIDC broker for auth.
- Optional LDAP/Active Directory integration
- Optional User Registration, with optional Recaptcha ability
- Password and TOTP support (via Google Authenticator).  Client cert auth coming soon.
- User session management from both admin and user perspective
- Customizable themes for user facing pages: login, grant pages, account management, emails, and admin console all customizable!
- OAuth 2.0 Bearer token auth for REST Services
- Integrated Browser App to REST Service token propagation
- Admin REST API
- CORS Support
- Completely centrally managed user and role mapping metadata.  Minimal configuration at the application side
- Admin Console for managing users, roles, role mappings, applications, user sessions, allowed CORS web origins, and OAuth clients.
- Deployable as a WAR, appliance, or an Openshift  cloud service (SaaS).
- Supports JBoss AS7, EAP 6.x, Wildfly, Tomcat, Jetty, and Pure Javascript applications.   Plans to support Node.js, RAILS, GRAILS, and other non-Java applications.
- HTTP Security Proxy for environments/platforms/languages that don't have a client adapter
- Javascript/HTML 5 adapter for pure Javascript apps
- Session management from admin console
- Claim/assertion mappings.  Make your tokens and assertion XML look however you want.
- Revocation policies
- Password policies
- Impersonation.  Allow your admins to impersonate a user to debug problems.

# Notes from Presentation

## Key Points

- Distributed services rather than monolith
- Best practice seems to be 1 functional area per service
- No sneaky backdoors, everything goes through APIs and Messaging Services
- No specific technology required!

## What you used to do

- A monolith where all authentication used to happen

## The new fancy way

- You have an aythentication service just like all the other services
- It should be distributed and fault tolerant
- It should be able to scale indepedantly
- It should have a standard way to interact

## So how do I get my hands on this hotness

- Stormpath
- Auth0
- We are going to show an installable FOSS project from Red Hat called Keycloak

## Keycloak

- Open Source Identity and Access Management (Redhat)

## Authentication

- Keycloak deals with authentication
- Safely store passwords
- Two factor authentication
- Customizable flows
- Single Sign On

## Protocols

- OpenID Connect
- SAML v2
- Kerberos SSO Bridge

## Clustering

- Scalability
- High Availability

## Client Adapters

- Easy to use client libraries
- JavaEE, Spring, JavaSCript, NodeJS and mobile
- More to come
- Can also use
    - Any OpenID or SAML v2 provider

## Service Provider Interfaces (SPIs)

- Keycloak aims to be an out of the box solution
- But! Some people have custom requirements
- That's why we have SPIs
    - User Store
    - User Federation
    - Authentcation
    - Required ACtions
    - And any more, even pluggable protocols
