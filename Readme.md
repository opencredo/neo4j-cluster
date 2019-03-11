# Neo4j Causal Cluster

This compose enviroment enable developers to test they applications with a neo4j cluster. This cluster use the Neo4j official images (3.5.3) enterprise. Please review the [license information](https://neo4j.com/licensing/) before use this project.

In addition project provides prometheus and graphana, prometheus is scrapping metrics from the neo4j servers.

## Starting the cluster

This project use a compose file vs 3.x that requires docker engine 	1.13.0+, 17.04.0+.

Start you enviroment with:

```bash
    docker-compose up
```

Access the cluster nodes at:

* [node1](http://localhost:7474/browser/)
* [node2](http://localhost:7475/browser/)
* [node3](http://localhost:7476/browser/)

Using `neo4j/opencredo` as user/password, please change the password after loging using:

```none
    :server change-password
```

Please change the password for all the servers at the cluster.

To review the cluster topology neo4j provide a set of management functions:

```cypher
    CALL dbms.cluster.overview
```

## Monitoring

Prometheus is running [locally](http://localhost:9090/graph), you will need to configure a datasource in [graphana](http://localhost:3000/) to create cluster dashboards.

Grafana default user and password is a`admin/admin`

Grafana will require a new datasource:

![ds](doc/ds.png)

And we are ready to create new dashboards

![dash](doc/dash.png)