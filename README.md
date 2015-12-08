# Consul on Docker

Service discovery and configuration made easy. Distributed, highly available, and datacenter-aware.

## Usage

Bootstrap a single-node Consul cluster:
```
docker run colstrom/consul agent -data-dir /data -server -bootstrap-expect 1
```

Add a node to a Consul cluster:
```
docker run colstrom/consul agent -data-dir /data -server -join $IP_OF_ANY_CLUSTER_MEMBER
```

Start a non-server node to a Consul cluster:
```
docker run colstrom/consul agent -data-dir /data -join $IP_OF_ANY_CLUSTER_MEMBER
```

## Exposed Ports
* 8300
* 8301
* 8301/udp
* 8302
* 8302/udp
* 8400
* 8500
* 8600
* 8600/udp

## License
[MIT](https://tldrlegal.com/license/mit-license)

## Contributors
* [Chris Olstrom](https://colstrom.github.io/) | [e-mail](mailto:chris@olstrom.com) | [Twitter](https://twitter.com/ChrisOlstrom)
