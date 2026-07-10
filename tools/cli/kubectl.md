# kubectl Cheat-Sheet

## Cluster and Context

| Command | Description |
| --- | --- |
| `kubectl version` | Show client and server version |
| `kubectl cluster-info` | Display cluster endpoint information |
| `kubectl config view` | Show the merged kubeconfig |
| `kubectl config get-contexts` | List all available contexts |
| `kubectl config current-context` | Display the current context |
| `kubectl config use-context <context>` | Switch to another context |
| `kubectl config set-context --current --namespace=<ns>` | Set the default namespace for the current context |

## Getting Resources

| Command | Description |
| --- | --- |
| `kubectl get pods` | List pods in the current namespace |
| `kubectl get pods -A` | List pods across all namespaces |
| `kubectl get pods -o wide` | List pods with node and IP details |
| `kubectl get all` | List common resources in the namespace |
| `kubectl get nodes` | List cluster nodes |
| `kubectl get svc,deploy,ing` | List several resource types at once |
| `kubectl get pods -l app=nginx` | Filter resources by label selector |
| `kubectl get pods --watch` | Stream changes to the resource list |
| `kubectl get pod <pod> -o yaml` | Output a resource as YAML |
| `kubectl get pods --sort-by=.metadata.creationTimestamp` | Sort output by a field |

## Describe and Inspect

| Command | Description |
| --- | --- |
| `kubectl describe pod <pod>` | Show detailed state and events for a pod |
| `kubectl describe node <node>` | Show node details, capacity and conditions |
| `kubectl explain deployment.spec` | Show documentation for a resource field |
| `kubectl api-resources` | List all supported resource types |
| `kubectl get events --sort-by=.lastTimestamp` | List events sorted by time |

## Logs and Exec

| Command | Description |
| --- | --- |
| `kubectl logs <pod>` | Print logs of a pod |
| `kubectl logs <pod> -c <container>` | Print logs of a specific container |
| `kubectl logs -f <pod>` | Follow (stream) pod logs |
| `kubectl logs <pod> --previous` | Show logs from the previous container instance |
| `kubectl exec -it <pod> -- /bin/sh` | Open an interactive shell in a pod |
| `kubectl exec <pod> -- env` | Run a one-off command in a pod |
| `kubectl cp <pod>:/path ./local` | Copy files from a pod to local |
| `kubectl port-forward <pod> 8080:80` | Forward a local port to a pod |

## Create, Apply and Delete

| Command | Description |
| --- | --- |
| `kubectl apply -f manifest.yaml` | Create or update resources from a file |
| `kubectl apply -f ./dir/` | Apply all manifests in a directory |
| `kubectl create -f manifest.yaml` | Create resources from a file |
| `kubectl delete -f manifest.yaml` | Delete resources defined in a file |
| `kubectl delete pod <pod>` | Delete a specific pod |
| `kubectl delete pods --all` | Delete all pods in the namespace |
| `kubectl create deployment nginx --image=nginx` | Create a deployment imperatively |
| `kubectl run tmp --rm -it --image=busybox -- sh` | Run a throwaway interactive pod |

## Edit and Update

| Command | Description |
| --- | --- |
| `kubectl edit deployment <deploy>` | Edit a resource in your default editor |
| `kubectl set image deployment/<deploy> app=nginx:1.25` | Update a container image |
| `kubectl scale deployment <deploy> --replicas=3` | Scale a deployment |
| `kubectl rollout status deployment/<deploy>` | Watch the status of a rollout |
| `kubectl rollout history deployment/<deploy>` | Show rollout revision history |
| `kubectl rollout undo deployment/<deploy>` | Roll back to the previous revision |
| `kubectl rollout restart deployment/<deploy>` | Restart all pods of a deployment |
| `kubectl label pod <pod> env=prod` | Add or update a label |
| `kubectl annotate pod <pod> note=hello` | Add or update an annotation |

## Namespaces

| Command | Description |
| --- | --- |
| `kubectl get namespaces` | List namespaces |
| `kubectl create namespace <ns>` | Create a namespace |
| `kubectl delete namespace <ns>` | Delete a namespace |
| `kubectl get pods -n <ns>` | List pods in a specific namespace |

## Config, Secrets and ConfigMaps

| Command | Description |
| --- | --- |
| `kubectl create configmap <name> --from-file=config.txt` | Create a ConfigMap from a file |
| `kubectl create configmap <name> --from-literal=key=value` | Create a ConfigMap from a literal |
| `kubectl create secret generic <name> --from-literal=pass=1234` | Create a generic secret |
| `kubectl get secret <name> -o jsonpath='{.data.pass}' | base64 -d` | Decode a secret value |

## Troubleshooting

| Command | Description |
| --- | --- |
| `kubectl top pod` | Show CPU/memory usage of pods (needs metrics-server) |
| `kubectl top node` | Show CPU/memory usage of nodes |
| `kubectl get pod <pod> -o jsonpath='{.status.phase}'` | Extract a single field with JSONPath |
| `kubectl wait --for=condition=Ready pod/<pod>` | Block until a condition is met |
| `kubectl debug <pod> -it --image=busybox` | Attach an ephemeral debug container |
| `kubectl drain <node> --ignore-daemonsets` | Safely evict pods from a node |
| `kubectl cordon <node>` | Mark a node as unschedulable |
| `kubectl uncordon <node>` | Mark a node as schedulable again |
