# Neo4j Causal Cluster

This compose example has been built to help developers test their applications with a neo4j cluster. This cluster uses the Neo4j official images (3.5.3) enterprise. Please review the [license information](https://neo4j.com/licensing/) before using this project.

Also, the project provides Prometheus and Grafana - Prometheus is scraping metrics from the neo4j servers.

## Starting the cluster

This project use a [Docker Compose](https://docs.docker.com/compose/) file vs 3.x that requires docker engine: 1.13.0+, 17.04.0+.

Start you environment with:

```bash
    docker-compose up
```

Access the cluster nodes at:

* [node1](http://localhost:7474/browser/)
* [node2](http://localhost:7475/browser/)
* [node3](http://localhost:7476/browser/)

Using `neo4j/opencredo` as user/password, please change the password after logging in using:

```none
    :server change-password
```

This project uses a Docker Compose file v 3.x that requires docker engine: 1.13.0+, 17.04.0+.

Start your environment with:

```cypher
    CALL dbms.cluster.overview
```

## Monitoring

Prometheus is running [locally](http://localhost:9090/graph); you will need to configure a datasource in [graphana](http://localhost:3000/) to create cluster dashboards.

Grafana default user and password is a`admin/admin`

Grafana will require a new datasource:

![ds](doc/ds.png)

And we are ready to create new dashboards

![dash](doc/dash.png)
