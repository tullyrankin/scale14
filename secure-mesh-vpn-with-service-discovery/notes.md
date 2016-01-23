# Tinc

## What is Tinc?

tinc is a Virtual Private Network (VPN) daemon that uses tunnelling and encryption to create a secure private network between hosts on the Internet. tinc is Free Software and licensed under the GNU General Public License version 2 or later. Because the VPN appears to the IP level network code as a normal network device, there is no need to adapt any existing software. This allows VPN sites to share information with each other over the Internet without exposing any information to others. In addition, tinc has the following features:

**Encryption, authentication and compression**

- All traffic is optionally compressed using zlib or LZO, and OpenSSL is used to encrypt the traffic and protect it from alteration with message authentication codes and sequence numbers.

**Automatic full mesh routing**

- Regardless of how you set up the tinc daemons to connect to each other, VPN traffic is always (if possible) sent directly to the destination, without going through intermediate hops.

**Easily expand your VPN**

- When you want to add nodes to your VPN, all you have to do is add an extra configuration file, there is no need to start new daemons or create and configure new devices or network interfaces.

**Ability to bridge ethernet segments**

- You can link multiple ethernet segments together to work like a single segment, allowing you to run applications and games that normally only work on a LAN over the Internet.

**Runs on many operating systems and supports IPv6**

- Currently Linux, FreeBSD, OpenBSD, NetBSD, MacOS/X, Solaris, Windows 2000, XP, Vista and Windows 7 and 8 platforms are supported. See our section about supported platforms for more information about the state of the ports. tinc has also full support for IPv6, providing both the possibility of tunneling IPv6 traffic over its tunnels and of creating tunnels over existing IPv6 networks.

## Resources

- [http://www.tinc-vpn.org](http://www.tinc-vpn.org)


# Consul
Service discovery and configuration made easy. Distributed, highly available, and datacenter aware.

## What is Consul?

Consul has multiple components, but as a whole, it is a tool for discovering and configuring services in your infrastructure. It provides several key features:

**Service Discovery:**

- Clients of Consul can provide a service, such as api or mysql, and other clients can use Consul to discover providers of a given service. Using either DNS or HTTP, applications can easily find the services they depend upon.

**Health Checking:**

- Consul clients can provide any number of health checks, either associated with a given service ("is the webserver returning 200 OK"), or with the local node ("is memory utilization below 90%"). This information can be used by an operator to monitor cluster health, and it is used by the service discovery components to route traffic away from unhealthy hosts.

**Key/Value Store:**

- Applications can make use of Consul's hierarchical key/value store for any number of purposes, including dynamic configuration, feature flagging, coordination, leader election, and more. The simple HTTP API makes it easy to use.

**Multi Datacenter:**

- Consul supports multiple datacenters out of the box. This means users of Consul do not have to worry about building additional layers of abstraction to grow to multiple regions.


## Basic Architecture of Consul

Consul is a distributed, highly available system. This section will cover the basics, purposely omitting some unnecessary detail, so you can get a quick understanding of how Consul works.

Every node that provides services to Consul runs a Consul agent. Running an agent is not required for discovering other services or getting/setting key/value data. The agent is responsible for health checking the services on the node as well as the node itself.

The agents talk to one or more Consul servers. The Consul servers are where data is stored and replicated. The servers themselves elect a leader. While Consul can function with one server, 3 to 5 is recommended to avoid failure scenarios leading to data loss. A cluster of Consul servers is recommended for each datacenter.

Components of your infrastructure that need to discover other services or nodes can query any of the Consul servers or any of the Consul agents. The agents forward queries to the servers automatically.

Each datacenter runs a cluster of Consul servers. When a cross-datacenter service discovery or configuration request is made, the local Consul servers forward the request to the remote datacenter and return the result.

## Resources

- [https://consul.io](https://consul.io)
