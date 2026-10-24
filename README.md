# Certified Kubernetes Administrator (CKA) with Practice Tests — KodeKloud

[Course page](https://www.udemy.com/course/certified-kubernetes-administrator-with-practice-tests/) · **Instructor:** Mumshad Mannambeth (KodeKloud) · **Status:** completed, **CKA passed** (2025)

## About

Kubernetes is an open-source **container orchestrator**. It deploys, scales and manages containerized apps on a cluster of machines. Google created it; the Cloud Native Computing Foundation (CNCF) maintains it today.

This course prepares the CKA, a hands-on exam on live clusters. Practice: KodeKloud labs and mock exams, and the killer.sh exam simulator.

## Course content

| # | Section | Topics |
|---|---|---|
| 1 | Introduction | Course overview, exam tips |
| 2 | Core Concepts | Cluster architecture, etcd, API server, Pods, ReplicaSets, Deployments, Services, namespaces |
| 3 | Scheduling | Labels and selectors, taints and tolerations, node affinity, resource limits, DaemonSets, static Pods |
| 4 | Logging and Monitoring | Metrics Server, application logs |
| 5 | Application Lifecycle Management | Rolling updates, commands and arguments, ConfigMaps, Secrets, multi-container Pods, autoscaling |
| 6 | Cluster Maintenance | Node drain, cluster upgrade, etcd backup and restore |
| 7 | Security | TLS certificates, kubeconfig, RBAC, service accounts, network policies |
| 8 | Storage | Volumes, PersistentVolumes, PersistentVolumeClaims, StorageClasses |
| 9 | Networking | CNI, cluster DNS, Ingress, Gateway API |
| 10 | Design and Install a Cluster | Install with kubeadm |
| 11 | Troubleshooting | Application, control plane, worker node and network failures |

## My notes

My Kubernetes cheat sheets: [cheatsheets/k8s](https://github.com/PoissonChevre/cheatsheets/tree/main/k8s)

| Folder | Content |
|---|---|
| [manifests](./manifests/) | YAML written during practice tests (list below) |
| [techworld-nana](./techworld-nana/) | Beginner tutorial by TechWorld with Nana: Minikube, kubectl basics, MongoDB demo, Ingress |

### manifests/

| File | What it shows |
|---|---|
| [deployment.yaml](./manifests/deployment.yaml) | A basic Deployment with an environment variable |
| [gateway-https.yaml](./manifests/gateway-https.yaml) | Gateway API: HTTPS listener with a TLS Secret |
| [gateway-multi-host-tls.yaml](./manifests/gateway-multi-host-tls.yaml) | Gateway API: two hostnames, one certificate each |
| [hpa.yaml](./manifests/hpa.yaml) | HorizontalPodAutoscaler on CPU, with scale-up and scale-down speed |
| [vpa.yaml](./manifests/vpa.yaml) | VerticalPodAutoscaler with min and max resources |
| [networkpolicy-egress.yaml](./manifests/networkpolicy-egress.yaml) | Egress allowed only to one namespace, plus DNS |
| [pod-secret-env.yaml](./manifests/pod-secret-env.yaml) | Secret loaded as environment variables (`envFrom`) |
| [pod-secret-volume.yaml](./manifests/pod-secret-volume.yaml) | Secret mounted as files (volume) |

The course slides (PDF) stay on my machine: they belong to KodeKloud, so they are not in Git.

## Takeaways

- Clear, well-structured course, with a practical lab after each topic.

## Resources

**Official docs**

- [Kubernetes documentation](https://kubernetes.io/docs/home/)
- [kubectl quick reference](https://kubernetes.io/docs/reference/kubectl/quick-reference/)
- [Kubernetes basics tutorial](https://kubernetes.io/docs/tutorials/kubernetes-basics/)
- [Back up an etcd cluster](https://kubernetes.io/docs/tasks/administer-cluster/configure-upgrade-etcd/#backing-up-an-etcd-cluster)
- [Install Minikube](https://minikube.sigs.k8s.io/docs/start/)

**Course notes**

- [KodeKloud CKA course notes (GitHub)](https://github.com/kodekloudhub/certified-kubernetes-administrator-course)

**Videos**

- TechWorld with Nana: [Kubernetes Crash Course for Absolute Beginners](https://www.youtube.com/watch?v=s_o8dwzRlu4) · [Kubernetes Tutorial for Beginners (4 hours)](https://www.youtube.com/watch?v=X48VuDVv0do)
- KodeKloud: [Install Kubernetes from Scratch](https://www.youtube.com/watch?v=uUupRagM7m0&list=PL2We04F3Y_41jYdadX55fdJplDvgNGENo)
- Learn Linux TV: [Build a Kubernetes cluster on Proxmox](https://www.learnlinux.tv/how-to-build-an-awesome-kubernetes-cluster-using-proxmox-virtual-environment/)

