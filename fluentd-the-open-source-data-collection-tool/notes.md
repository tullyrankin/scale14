# Fluentd
Open Source Data Collector

## Logging

- Pros
    - Application status
    - Debugging
    - General information about anomalies: errors

### Logging Matters

From a business point of view

- Input data -> analytics
- User interaction / behaviors
- Improvements

#### Assumptions

- I have enough disk space
- I/O operations will not block
- Log messages are human readable
- My logging mechanism scale

#### Concerns

- Logs **increase** = data **increase**
- Message format get more **complex**
- Did the Kernel flush the buffers? (sync(2))
- Multi-thread application?, **locking**?
- **M**ultiple Applications = **M**ultiple Logs

## Common Sources & Inputs

- Application Logs
    - Apache
    - NGINX
    - Syslog (-ng)
- Custom applications / Languages
    - C, Ruby, Python, etc

## Highlights

- High Performance
- Built-in Reliability
- Structured Logs
- Pluggable Architecture
- More than 300 Plugins! (input/filtering/output)

## Architecture

- Input-ish
    - Input
    - Parser
    - Filter
- Output-ish
    - Buffer
    - Output
    - Formatter

### Input plugins

- Receive logs
- Or pull logs from data sources
- In non-blocking manner

### Output plugins

- Write or send event logs

### Buffer plugins

- Improve performance
- Provide reliability
- Provide thread-safety

## Simple Forwarding: configuration

### Logs from a file

```
<source>
type    tail
path    /var/log/httpd.log
format  apache2
tag backend.apache
</source>
```

### logs from client libraries

```
<source>
type    forward
port    24224
</source>
```

### store logs to MongoDB

```
<match backend.*>
type mongo
database fluent
collection test
</match>
```

## Internet of Things

### Facts

- IoT will grow to many billiions of devices over the next decade.

### Alliances

- Vendors formed alliances to join forces and develop generic software layers for their products

### Analytics

- IoT requires a generic solution to collect events and data from different sources for further analysis.

## Fluent Bit

- Fouent Bit is an open source data collector
- It lets you collect data from IoT/Embedded devices

### Targets

- Services
- Sensors / Signals / Radios
- Operating System information
- Automotive / Telematics

### Requirements

IoT and Embedded environment requires special handling, specifically on performance and resource utilization:

- Lightweight
- Written in C Language

### Integration

- data source
- fluent-bit
    - data collection
- fluentd
    - data colleciton
    - filtering
    - buffering
    - distribution
- stored
    - processing
    - analytics
    - big data

### Direct Output

- data source
- fluent-bit
    - data-collection
- storage
    - processing
    - analytics
    - big data

## Resources

- http://fluentd.org
- http://fluentbit.io
- https://docs.docker.com/reference/logging/fluentd/
- http://github.com/fluent/fluentd
