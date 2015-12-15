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

| Port       | Purpose             | Description
|------------|---------------------|--------
| `8300`     | Server RPC          | Used by servers to handle incoming requests from other agents.
| `8301`     | Serf LAN            | Used to handle gossip in the LAN. Required by all agents.
| `8301/udp` | Serf LAN (UDP)      | Used to handle gossip in the LAN. Required by all agents.
| `8302`     | Serf LAN            | Used by servers to gossip over the WAN to other servers.
| `8302/udp` | Serf LAN (UDP)      | Used by servers to gossip over the WAN to other servers.
| `8400`     | CLI RPC             | Used by all agents to handle RPC from the CLI.
| `8500`     | HTTP API            | Used by clients to talk to the HTTP API.
| `8600`     | DNS Interface       | Used to resolve DNS queries.
| `8600/udp` | DNS Interface (UDP) | Used to resolve DNS queries.

## License
[MIT](https://tldrlegal.com/license/mit-license)

## Contributors
* [Chris Olstrom](https://colstrom.github.io/) | [e-mail](mailto:chris@olstrom.com) | [Twitter](https://twitter.com/ChrisOlstrom)
