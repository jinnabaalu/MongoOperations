# Deploying Mongo 3 Node Cluster 

- Using docker-compose

```bash
cd mongodb/
docker-compose down
docker-compose up -d
```

- Using kubernetes manifest

```bash

```

## Initialise the cluster 

```bash
docker exec -it mongo1 mongosh --eval "rs.initiate({
 _id: \"mongoDevReplicaSet\",
 members: [
   {_id: 0, host: \"mongo1\"},
   {_id: 1, host: \"mongo2\"},
   {_id: 2, host: \"mongo3\"}
 ]
})"

```

## Verify the Multinode replica set with mongoDB 

- Verify the cluster
```bash
docker exec -it mongo1 mongosh --eval "rs.status()"
docker exec -it mongo2 mongosh --eval "rs.status()"
docker exec -it mongo3 mongosh --eval "rs.status()"
```
- Stop any node, `mongo1` and verify cluster connecting to `mongo2` or `mongo3`

```bash
docker stop mongo1
docker exec -it mongo2 mongosh --eval "rs.status()"
docker exec -it mongo3 mongosh --eval "rs.status()"
```




