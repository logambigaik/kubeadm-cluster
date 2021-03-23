# kubeadmcluster

# kubeadm:

Kubeadm is a toolkit for bootstrapping a best-practises Kubernetes cluster on existing infrastructure. Kubeadm cannot provision your infrastructure which is one of the main differences to kops(Kops stands for Kubernetes operations. The tagline for the project is that it’s “the easiest way to get a production-grade Kubernetes cluster up and running”. Kops is sometimes referred to as the ‘kubectl’ for spinning up clusters). 
Another differentiator is that Kubeadm can be used not only as an installer but also as a building block.

![image](https://user-images.githubusercontent.com/54719289/111772552-e69d1380-88a4-11eb-974f-6d837c37c142.png)

# Usage:

        kubeadm init to bootstrap a Kubernetes control-plane node
        kubeadm join to bootstrap a Kubernetes worker node and join it to the cluster
        kubeadm upgrade to upgrade a Kubernetes cluster to a newer version
        kubeadm config if you initialized your cluster using kubeadm v1.7.x or lower, to configure your cluster for kubeadm upgrade
        kubeadm token to manage tokens for kubeadm join
        kubeadm reset to revert any changes made to this host by kubeadm init or kubeadm join
        kubeadm version to print the kubeadm version
        kubeadm alpha to preview a set of features made available for gathering feedback from the community

# Kubeadm vs kops

        Kubeadm is in the middle of the stack and it runs on each node, and basically creates and then talks to the Kubernetes API.
        Kops on the other hand is responsible for the entire lifecycle of the cluster, from infrastructure provisioning to upgrading to deleting, and it knows about everything:           nodes, masters, load balancers, cloud providers, monitoring, networking, logging etc.

# Kubeadm installation: ( Install in both master and worker machine)


        Update the apt package index and install packages needed to use the Kubernetes apt repository:

        sudo apt-get update
        sudo apt-get install -y apt-transport-https ca-certificates curl
        
        Download the Google Cloud public signing key:

        sudo curl -fsSLo /usr/share/keyrings/kubernetes-archive-keyring.gpg https://packages.cloud.google.com/apt/doc/apt-key.gpg

        Add the Kubernetes apt repository:

        echo "deb [signed-by=/usr/share/keyrings/kubernetes-archive-keyring.gpg] https://apt.kubernetes.io/ kubernetes-xenial main" | sudo tee /etc/apt/sources.list.d/kubernetes.list

        Update apt package index, install kubelet, kubeadm and kubectl, and pin their version:

        sudo apt-get update
        sudo apt-get install -y kubelet kubeadm kubectl
        sudo apt-mark hold kubelet kubeadm kubectl
        
        
# Why swapoff -a is required?

        swapoff -a
        
![image](https://user-images.githubusercontent.com/54719289/111790500-2a4e4800-88ba-11eb-80c0-bc8fb93c7122.png)


        modprobe br_netfilter
        
        - This module is required to enable transparent masquerading and to facilitate Virtual Extensible LAN (VxLAN) traffic for communication between Kubernetes pods across   the cluster
        
        sysctl -p
        sudo sysct
        sudo sysctl net.bridge.bridge-nf-call-iptables=1
        apt-get install docker.io -y
        usermod -aG docker ubuntu
        systemctl enable docker
        systemctl start docker
        systemctl status docker
        docker --version
        
        systemctl daemon-reload
        systemctl start kubelet
        systemctl enable kubelet.service
        
        
        # run this command in master
        kubeadm init
        
        
        
