FROM ubuntu:16.04
RUN apt-get update && apt-get upgrade -y && apt install wget -y
RUN ["apt-get", "install", "-y", "vim"]
RUN apt-get install net-tools
RUN wget https://dist.ipfs.io/go-ipfs/v0.4.19/go-ipfs_v0.4.19_linux-amd64.tar.gz
RUN tar -zxvf go-ipfs_v0.4.19_linux-amd64.tar.gz && cp go-ipfs/ipfs /bin/
RUN ipfs init
RUN wget https://dist.ipfs.io/ipfs-cluster-ctl/v0.10.0/ipfs-cluster-ctl_v0.10.0_linux-amd64.tar.gz
RUN tar -zxvf ipfs-cluster-ctl_v0.10.0_linux-amd64.tar.gz && cp ipfs-cluster-ctl/ipfs-cluster-ctl /bin/
RUN wget https://dist.ipfs.io/ipfs-cluster-service/v0.10.0/ipfs-cluster-service_v0.10.0_linux-amd64.tar.gz
RUN tar -zxvf ipfs-cluster-service_v0.10.0_linux-amd64.tar.gz && cp ipfs-cluster-service/ipfs-cluster-service /bin/
ENV CLUSTER_SECRET  5843bfa4dcab8fa2f8edda1245da86754bf0abbee12a213fd075b97d661e337c
RUN ipfs-cluster-service init
COPY script_master .
CMD chmod +x script_master
ENTRYPOINT ./script_master
