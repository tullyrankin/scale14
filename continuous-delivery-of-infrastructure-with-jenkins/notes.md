# Continuous Delivery of Infrastructure with Jenkins

## Resources

- Machiens (physical/virtual)
- Routers
- Load Balancers
- Switches

## Configuration Management

- Files
- Packages
- Secrets

## Build infrastructure

- Jenkins Master
- Jenkins agents

## Developer Tools

- Jira
- Confluence
- IRC bot
- Code quality reporters

## Release infrastructure

- Apache/MirrorBrain
- Jenkins
- Ratings app

## Project tooling

- MeetingBot
- LDAP
- Account app
- Spam bot

## Continuous Delivery

- every commit should be ready for delivery
- deploy production when the organization is ready

## Reproducibility

- Docker
    - Pros
        - Easy to partition workloads on physical hardware
        - Consistent application runtime environment
        - Rapidly evolving
    - Cons
        - What goes in Puppet vs Dockerfile
        - iptables
        - The image becomes another thing with a lifecycle
        - Rapidly evolving

## Where we use Docker

- JIRA
- Confluence
- Bind9
- IRC bots
