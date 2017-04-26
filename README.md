# consul as a Docker Service
This docker compose file shows how to run Consul as a service in the >= 1.13 versions of Docker. It assumes you have >= 5 nodes in with the consul label assined and at least 1 with the temp label assigned.

1. Create a swarm of 5 nodes

2. Add temp label to one of the node

```
docker node update --label-add access=temp node-1
```

3. Add consul label to other nodes

```
docker node update --label-add access=consul node-2
docker node update --label-add access=consul node-3
docker node update --label-add access=consul node-4
docker node update --label-add access=consul node-5
```

4. Deploy the stack

```
docker stack deploy test -c docker-compose.yml
```


