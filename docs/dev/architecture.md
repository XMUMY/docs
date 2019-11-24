# Architecture

Here is a overview of the XMUX project.

## Cluster Architecture

![ClusterArchitecture](https://i.jpg.dog/img/874c6bf7570e53550776b27556eed9f3.png)

XMUX cluster is designed to be high availability, high performace and extendable. Currently it is running on a set of virtual machines in Xiamen University Malaysia main cluster. On top of virtual machines, almost all applications are powered by [docker container](https://www.docker.com/products/container-runtime) which provided a virtualization of underlying operating system with higher performance and lower cost for both storage space and computing resources.

Generally, the cluster can be splited into 4 layers. (from buttom to top)
