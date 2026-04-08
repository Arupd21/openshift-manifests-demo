# openshift-manifests-demo

A production-grade collection of Red Hat OpenShift 4.x manifests demonstrating real-world cluster administration, security enforcement, networking, and workload management used in enterprise environments.

Built from hands-on experience managing OpenShift clusters in hybrid cloud environments (Azure AKS and AWS EKS) at enterprise scale.

---

## What This Repo Covers

| Area | Topics |
|------|--------|
| Security | SCCs, RBAC, Roles, RoleBindings, ServiceAccounts |
| Networking | Routes (Edge, Passthrough, Re-encrypt), NetworkPolicies |
| Workloads | Deployments, StatefulSets, DaemonSets, CronJobs |
| Storage | PersistentVolumes, PVCs, StorageClasses |
| Autoscaling | HPA, resource requests and limits |
| Operators | OLM Subscription, OperatorGroup examples |
| Quotas | ResourceQuota, LimitRange per namespace |

---

## Repo Structure

```
openshift-manifests-demo/
├── rbac/
│   ├── role.yaml
│   ├── clusterrole.yaml
│   ├── rolebinding.yaml
│   └── serviceaccount.yaml
├── scc/
│   ├── custom-scc.yaml
│   └── scc-assignment.md
├── networking/
│   ├── route-edge.yaml
│   ├── route-passthrough.yaml
│   ├── route-reencrypt.yaml
│   └── networkpolicy-deny-all.yaml
├── workloads/
│   ├── deployment.yaml
│   ├── statefulset.yaml
│   ├── daemonset.yaml
│   └── cronjob.yaml
├── storage/
│   ├── storageclass.yaml
│   ├── pv.yaml
│   └── pvc.yaml
├── autoscaling/
│   ├── hpa.yaml
│   └── resource-limits.yaml
├── quotas/
│   ├── resourcequota.yaml
│   └── limitrange.yaml
├── operators/
│   ├── operatorgroup.yaml
│   └── subscription.yaml
└── README.md
```

---

## Prerequisites

- OpenShift 4.x cluster (use [Red Hat Developer Sandbox](https://developers.redhat.com/developer-sandbox) for free)
- `oc` CLI installed and logged in
- Cluster admin access for SCC and RBAC operations

---

## Quick Start

```bash
# Clone the repo
git clone https://github.com/Arupd21/openshift-manifests-demo.git
cd openshift-manifests-demo

# Login to your OpenShift cluster
oc login --token=<token> --server=<server-url>

# Create a new project
oc new-project demo-project

# Apply RBAC
oc apply -f rbac/

# Apply networking
oc apply -f networking/

# Apply workloads
oc apply -f workloads/
```

---

## Sections

### RBAC & Security
Demonstrates Role-Based Access Control in OpenShift — creating scoped Roles, ClusterRoles, and binding them to users and ServiceAccounts. Follows least-privilege principles.

### SCCs (Security Context Constraints)
OpenShift-specific security policies controlling what a pod is allowed to do at the OS level — whether it can run as root, mount host paths, use privileged mode, etc. Includes a custom SCC example for applications requiring specific UIDs.

### Routes & Networking
All three OpenShift route types (Edge, Passthrough, Re-encrypt) with TLS configuration. NetworkPolicy examples for namespace isolation and pod-to-pod traffic control.

### Workloads
Production-grade workload manifests with proper resource requests/limits, health probes (liveness, readiness, startup), and pod disruption budgets.

### Storage
PersistentVolume and PersistentVolumeClaim examples with different access modes and StorageClass configurations.

### Autoscaling
Horizontal Pod Autoscaler configured for CPU and memory-based scaling. Resource requests and limits following QoS best practices.

### Operators via OLM
OperatorGroup and Subscription manifests for installing Operators via the Operator Lifecycle Manager.

---

## Author

**Arup Das**
Senior OpenShift & Kubernetes Engineer | 4+ Years | Wipro Technologies
AWS Certified Solutions Architect – Associate | M.Tech, BITS Pilani

- Email: arupd.jsr@gmail.com
- LinkedIn: linkedin.com/in/arup-das-69160a367
