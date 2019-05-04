# free5gcservice-operator

```sh
$ operator-sdk new free5gcservice-operator  --cluster-scoped --api-version=free5gc.com/v1alpha1 --kind=Free5gcService --type helm
INFO[0000] Creating new Helm operator 'free5gcservice-operator'. 
INFO[0000] Created helm-charts/free5gcservice           
INFO[0000] Generating RBAC rules
WARN[0000] The RBAC rules generated in deploy/role.yaml are based on the chart's default manifest. Some rules may be missing for resources that are only enabled with custom values, and some existing rules may be overly broad. Double check the rules generated in deploy/role.yaml to ensure they meet the operator's permission requirements.
INFO[0000] Created build/Dockerfile
INFO[0000] Created watches.yaml
INFO[0000] Created deploy/service_account.yaml
INFO[0000] Created deploy/role.yaml
INFO[0000] Created deploy/role_binding.yaml
INFO[0000] Created deploy/operator.yaml
INFO[0000] Created deploy/crds/free5gc_v1alpha1_free5gcservice_crd.yaml
INFO[0000] Created deploy/crds/free5gc_v1alpha1_free5gcservice_cr.yaml
INFO[0000] Run git init ...
Initialized empty Git repository in /root/go/src/github.com/sufuf3/free5gcservice-operator/.git/
INFO[0000] Run git init done
INFO[0000] Project creation complete.
```

## Usage

### 1. Create CRD

```sh
kubectl create -f deploy/crds/free5gc_v1alpha1_free5gcservice_crd.yaml
```

### 2. Deploy operator 
```sh
kubectl create -f deploy/namespace.yaml
kubectl create -f deploy/service_account.yaml
kubectl create -f deploy/role.yaml
kubectl create -f deploy/role_binding.yaml
kubectl create -f deploy/operator.yaml
```

### 3. Deploy Free5gc custom resource
```sh
kubectl create -f deploy/crds/free5gc_v1alpha1_free5gcservice_cr.yaml
```
