# Architecture

Here is an overview of XMUX project.

## Cluster Architecture

![ClusterArchitecture](https://s4.ax1x.com/2022/03/05/b0q841.png)

XMUX cluster is designed to be high availability, high performace and extendable. Currently it is running on a set of virtual machines in Xiamen University Malaysia. On top of virtual machines, almost all applications are powered by [containerd runtime](https://containerd.io/) which provided a virtualization of underlying operating system with higher performance and lower cost for both storage space and computing resources.

Generally, the cluster can be splited into 4 layers. (from buttom to top)

- Cluster Fondations provide the essential environment for all applications above, including [kubernetes components](https://kubernetes.io/docs/concepts/overview/components/), [Kube-Router](https://www.kube-router.io/) and [Longhorn](https://longhorn.io/) cluster. Kube-Router provide a virtual network shared amone the whole cluster, based on IPVS and BGP. Longhorn stores persistent data produced by upper layer applications with at least 2 replicas in different physical devices.

- Application Fondations provide a set of neccessary services that applications rely on. [Prometheus](https://prometheus.io/) is a monitoring system that collect metrics from all other services and alert cluster manager if some error occured. [NATS](https://nats.io/) ensures a high-performace & reliable message delivery for all micro services above. [MinIO](https://min.io/) is an object storage that provides advanced features including cache, compression and encryption. [PostgreSQL](https://www.postgresql.org/) and [MongoDB](https://www.mongodb.com) are different kind of databases for applications to store and query data efficiently.

- Applications layer is the layer for regular applications. XMUS is a set of micro services that drive the XMUX project. The new API(v4) is written with Golang by using [Kratos framework](https://github.com/go-kratos/kratos) while the old API(v2) is written with Node.JS. Dashboards provide a user-friendly interface for monitoring and controlling the cluster. The CI/CD runners also running in the cluster thus they can communicate with other applications easily for testing.

- On top is the load balancer. [Nginx](https://www.nginx.com/) reverse proxy server can deliver user requests to different services by their path, which make the cluster can be easily extended according to the load of each service.

## Client Architecture

![Flutter](https://www.donnfelker.com/wp-content/uploads/2019/05/flutter-arch.png)

XMUX client is powered by [Flutter](https://flutter.dev), which is a UI toolkit for building beautiful, natively compiled applications for mobile, web, and desktop from a single codebase. Currently XMUX client can be run on Android, iOS and web(Alpha).