# kubeadmcluster

![image](https://user-images.githubusercontent.com/54719289/111656033-11825b80-8802-11eb-9241-138548874519.png)


#kubeadm:

Kubeadm is a tool built to provide kubeadm init and kubeadm join as best-practice "fast paths" for creating Kubernetes clusters.

kubeadm performs the actions necessary to get a minimum viable cluster up and running. By design, it cares only about bootstrapping, not about provisioning machines. Likewise, installing various nice-to-have addons, like the Kubernetes Dashboard, monitoring solutions, and cloud-specific addons, is not in scope.

Instead, we expect higher-level and more tailored tooling to be built on top of kubeadm, and ideally, using kubeadm as the basis of all deployments will make it easier to create conformant clusters

# Usage:

        kubeadm init to bootstrap a Kubernetes control-plane node
        kubeadm join to bootstrap a Kubernetes worker node and join it to the cluster
        kubeadm upgrade to upgrade a Kubernetes cluster to a newer version
        kubeadm config if you initialized your cluster using kubeadm v1.7.x or lower, to configure your cluster for kubeadm upgrade
        kubeadm token to manage tokens for kubeadm join
        kubeadm reset to revert any changes made to this host by kubeadm init or kubeadm join
        kubeadm version to print the kubeadm version
        kubeadm alpha to preview a set of features made available for gathering feedback from the community

