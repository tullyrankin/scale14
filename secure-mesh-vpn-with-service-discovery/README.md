# Secure Mesh VPN with Service Discovery

**Presenter:** Spencer Krum<br />
**Audience:** Advanced<br />
**Topic:** New to SCALE

Tinc (http://www.tinc-vpn.org/) provides a secure mesh vpn for any number of hosts. My friends and I used this to build a network linking our homes, laptops, and various hosted machines. We started doing some cool things with it such as UPnP and NFS, things that would be impossible to do securely over the public internet. We then added Consul (https://consul.io/) which provides a service directory and health checks. Consul's raft consensus algorithm works well for us because nodes drop on and off this network frequently.

In this talk I will cover the configuration of our VPN and the neat things that we do with it.

**Room:** Ballroom F<br />
**Time:** Saturday, January 23, 2016 - 11:30 to 12:30
