# Rust: Systems Programming for Web Developers


**Presenter:** Herman Radtke<br />
**Audience:** Developer<br />
**Topic:** Developer

## Theory

1. Rust will not be a C++ killer.
    1. Paul Graham’s Blub Paradox - “Whatever language people happen to be used to, they tend to consider just good enough.”
1. Rust can make systems programming more accessible for web developers.

## History Repeats Itself

1. Ruby - Endless debates about whether PHP or Ruby/Rails was better. People did not count on the fact that EC2 launched and traditional ops was dying. Ruby spawned an entire generation of developers who built the tooling traditionally owned by ops people.

2. Node - Web ate the desktop, but people still want the native feel. Developers are being asked to create increasingly more complex UIs. This event-driven model did not translate well to the existing Ruby/Python/PHP frameworks. When node.js came out, many server side developers did not get it. Example: Ted Dzuiba and all the fibonacci examples. Node is not about technology! Async IO (libuv) and JS rendering (Rhino) has existed for years. Node is about giving client developers the power to create backends that worked well with web sockets.

3. Rust - The modern web stack continues to become more complex. As distributed computing becomes more commonplace, the services powering the web are more fragile than ever. The next decade will be about not splitting compute down into smaller resources but instead combining compute power into larger resources. Think Apache Mesos. Rust allows us to do this in one specific way by guaranteeing safety between threads. It is not a panacea but it does solve a problem in a fundamentally different way than using map/reduce.
    1. Map/reduce is not bad, we just need multiple strategies for distributed computing.

## Why Should A Web Developer Choose Rust?

1. Memory safety without garbage collection
2. Concurrency without data races
3. Abstraction without overhead


## Takeaways:

1. Rust adoption is not zero-sum. Let us empower non-systems developers, not just convert existing ones.

2. The existing web eco-system is feeling the pain of using systems in an ever-increasing distributed space and Rust is poised to be part of the solution.

3. The Rust community has done a ton of amazing things to make systems programming more accessible, but there are many more obstacles that a non-C++ developer has to overcome.

**Room:** Ballroom C<br />
**Time:** Sunday, January 24, 2016 - 15:00 to 16:00
