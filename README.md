# QueueMetrics.io BullMQ Connector

This is a small service which enables you to connect your [BullMQ](https://github.com/taskforcesh/bullmq) queues to [QueueMetrics.io](https://queuemetrics.io). It acts as a proxy between your Bull queues and the [QueueMetrics.io](https://queuemetrics.io) API, providing bi-directional data transfer which enables advanced queue insights and management with [QueueMetrics.io](https://queuemetrics.io).

This connector is designed to be used in production-grade environments and does not require the sharing of passwords or SSH tunnels to function. It is also very useful to use the connector in local development environments for rapid queue development and debugging.

The connector is very lightweight and efficient, and uses minimal resources.

## Installation

```sh
npm install queuemetrics-connector-bullmq
```

## Usage

```sh
Usage: queuemetrics-connector-bullmq [options]

Options:
  -V, --version                           output the version number
  -n, --connector-name <connection-name>  Connector name. Defaults to 'Default connector'. (default: "Default connector")
  -a, --api-key <api-key>                 QueueMetrics.io organization API key. Get this from https://dashboard.queuemetrics.io
  -h, --host <host>                       Redis host. Defaults to localhost. (default: "localhost")
  -p, --port <port>                       Redis port. Defaults to 6379. (default: "6379")
  -d, --database <database>               Redis database. Defaults to 0. (default: "0")
  -w, --password <password>               Redis password, can also be supplied by setting REDIS_PASSWORD environment variable.
  --tls [tls]                             Activate secured TLS connection to Redis
  -u, --uri [uri]                         Redis URI.
  -s, --sentinels [host:port]             Comma-separated list of sentinel host/port pairs
  -m, --master [name]                     Name of master node used in sentinel configuration
  -b, --backend <backend>                 QueueMetrics backend. Defaults to wss://api.queuemetrics.io (default: "wss://api.queuemetrics.io")
  --help                                  display help for command
```

### Example usage

```sh
npx queuemetrics-connector-bullmq -u redis://<your-redis-host>:<your-redis-port>/<your-redis-db> -a <your-queuemetrics-api-key>
```

Your API key can be obtained from your [Queuemetrics.io Dashboard](https://dashboard.queuemetrics.io/)
