---
name: Bug report
about: Problems and issues with code or docs
title: ''
labels: kind/bug
assignees: ''

---

<!--

Welcome to ingress-nginx!  For a smooth issue process, try to answer the following questions.
Don't worry if they're not all applicable; just try to include what you can :-)

If you need to include code snippets or logs, please put them in fenced code
blocks.  If they're super-long, please use the details tag like
<details><summary>super-long log</summary> lots of stuff </details>

-->

<!--

IMPORTANT!!!

Please complete the next sections or the issue will be closed.
This questions are the first thing we need to know to understand the context.

-->

**NGINX Ingress controller version**:

**Kubernetes version** (use `kubectl version`):

**Environment**:

- **Cloud provider or hardware configuration**:
- **OS** (e.g. from /etc/os-release):
- **Kernel** (e.g. `uname -a`):
- **Install tools**:
  - `Please mention how/where was clsuter created like kubeadm/kops/minikube/kind etc. `
- **Basic cluster related info**:
  - `kubectl version`
  - `kubectl get nodes -o wide`

- **How was the ingress-nginx-controller installed**:
  - If helm was used then please show output of `helm ls -A`
  - If helm was used then please show output of `helm -n <ingresscontrollernamepspace> get values <helmreleasename>`
  - If helm was not used, then please explain how the ingress-nginx-controller was installed or copy/paste the command used to install the controller below
  - if you have more than one instance of the ingress-nginx-controller installed in the same cluster, please provide details for all the instances

- **Current State of the controller**:
  - `kubectl -n <ingresscontrollernamespace> get all -A -o wide`
  - `kubectl -n <ingresscontrollernamespace> describe po <ingresscontrollerpodname>`
  - `kubectl -n <ingresscontrollernamespace> describe svc <ingresscontrollerservicename>`

- **Current state of ingress object, if applicable**:
  - `kubectl -n <appnnamespace> get all,ing -o wide`
  - `kubectl -n <appnamespace> describe ing <ingressname>`
  - If applicable, then, your complete and exact curl/grpcurl command (redacted if required) and the reponse to the curl/grpcurl command with the -v flag

- **Others**:
  - Any other related information like ;
    - copy/paste of the snippet (if applicable)
    - `kubectl describe ...` of any custom configmap(s) created and in use
    - Any other related information that may help

**What happened**:

<!-- (please include exact error messages if you can) -->

**What you expected to happen**:

<!-- What do you think went wrong? -->

**How to reproduce it**:
<!---

As minimally and precisely as possible. Keep in mind we do not have access to your cluster or application.
Help up us (if possible) reproducing the issue using minikube or kind.

## Install minikube/kind

- Minikube https://minikube.sigs.k8s.io/docs/start/
- Kind https://kind.sigs.k8s.io/docs/user/quick-start/

## Install the ingress controller

kubectl apply -f https://raw.githubusercontent.com/kubernetes/ingress-nginx/main/deploy/static/provider/baremetal/deploy.yaml

## Install an application that will act as default backend (is just an echo app)

kubectl apply -f https://raw.githubusercontent.com/kubernetes/ingress-nginx/main/docs/examples/http-svc.yaml

## Create an ingress (please add any additional annotation required)

echo "
  apiVersion: networking.k8s.io/v1beta1
  kind: Ingress
  metadata:
    name: foo-bar
  spec:
    rules:
    - host: foo.bar
      http:
        paths:
        - backend:
            serviceName: http-svc
            servicePort: 80
          path: /
" | kubectl apply -f -

## make a request

POD_NAME=$(k get pods -n ingress-nginx -l app.kubernetes.io/name=ingress-nginx -o NAME)
kubectl exec -it -n ingress-nginx $POD_NAME -- curl -H 'Host: foo.bar' localhost

--->

**Anything else we need to know**:

<!-- If this is actually about documentation, add `/kind documentation` below -->

/kind bug
