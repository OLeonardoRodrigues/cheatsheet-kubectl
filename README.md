# Cheatsheet Kubectl

1. Get Running Pods:
<code>kubectl get pods --field-selector=status.phase=Running -n <namespace></code>

1. Get Failed or Errored Pods:
<code>kubectl get pods --field-selector=status.phase=Failed -n <namespace></code>

1. Describe Deployment:
<code>kubectl describe deployment my-deployment -n <namespace></code>

1. Tail Logs from Container in Pod:
<code>kubectl logs -f pod my-pod -c container-name -n <namespace></code>

1. Access or Execute Command from Container:
<code>kubectl exec -it my-pod -n <namespace> --container container-name -- /bin/bash</code>

1. Edit ConfigMap:
<code>kubectl edit configmap my-configmap -n <namespace></code>

1. Rollout Status:
<code>kubectl rollout status deployment my-deployment -n <namespace></code>

1. Scale Deployment:
<code>kubectl scale deployment my-deployment --replicas=3 -n <namespace></code>

1. Select Pods by Label:
<code>kubectl get pods -l app=my-app -n <namespace></code>

1. Port Forward Pod so it is accessible from localhost:
<code>kubectl port-forward -n <namespace> pod my-pod 8080:80</code>

1. Get Resource Usage from Specific Pod:
<code>kubectl top pod my-pod -n <namespace></code>

1. Apply Remote Manifest:
<code>kubectl apply -f https://url-to-resource.yaml -n <namespace></code>

1. Explain Field:
<code>kubectl explain pod.spec.containers</code>

1. List Events Sorted by Timestamp:
<code>kubectl get events --sort-by=.metadata.creationTimestamp</code>

1. Annotate Deployment:
<code>kubectl annotate deployment my-deployment my-label=updated -n <namespace></code>

1. Rollback Deployment:
<code>kubectl rollout undo deployment my-deployment -n <namespace></code>

1. PVCs by Capacity:
<code>kubectl get pvc --sort-by=.spec.capacity.storage</code>

1. View Deployment Rollout History:
<code>kubectl rollout history deployment my-deployment -n <namespace></code>

1. Label a Pod:
<code>kubectl label pod my-pod my-label=updated -n <namespace></code>

1. Diff Manifests:
<code>kubectl diff -f https://url-to-new-resource.yaml</code>

1. Node Details:
<code>kubectl describe node my-node</code>

1. Get Services with Details:
<code>kubectl get services --all-namespaces -o wide</code>

1. Pause Rollout:
<code>kubectl rollout pause deployment my-deployment -n <namespace></code>

1. Describe Ingress:
<code>kubectl describe ingress my-ingress -n <namespace></code>

1. Force Delete Pod:
<code>kubectl delete pod my-pod --grace-period=0 --force -n <namespace></code>

1. Decode Secret (Kubernetes Secrets are too easy to break):
<code>kubectl get secret my-secret -o jsonpath='{.data.username}' | base64 -d</code>

1. Resume Rollout:
<code>kubectl rollout resume deployment my-deployment -n <namespace></code>

1. Export HPA:
<code>kubectl get hpa my-hpa -n <namespace> -o yaml > hpa.yaml</code>

1. Taint a Node:
<code>kubectl taint node my-node key=value:NoSchedule</code>

1. Get Completed Jobs:
<code>kubectl get jobs -n <namespace> --field-selector=status.successful=1</code>

1. Drain a Node:
<code>kubectl drain my-node --ignore-daemonsets</code>

1. Service IPs:
<code>kubectl get endpoints my-service -n <namespace> -o jsonpath='{.subsets[0].addresses[*].ip}'</code>

1. Rollback by Revision:
<code>kubectl rollout history deployment my-deployment --revision=3</code>

1. Explain Replica Count:
<code>kubectl explain deployment.spec.replicas</code>

1. Replace Resource:
<code>kubectl replace -f https://url-to-updated-resource.yaml</code>

1. Restart Deployment:
<code>kubectl rollout restart deployment my-deployment</code>

1. Uncordon Node:
<code>kubectl uncordon my-node</code>

1. Pending CSRs:
<code>kubectl get csr --sort-by=.metadata.creationTimestamp</code>

1. Rollback with Revision:
<code>kubectl rollout undo deployment my-deployment --to-revision=2</code>

1. Cordon Node:
<code>kubectl cordon my-node</code>

1. CRD List:
<code>kubectl api-resources | grep CustomResourceDefinition</code>

1. DaemonSet Status:
<code>kubectl rollout status daemonset/my-daemonset</code>

1. Ingress Hostname:
<code>kubectl get ingress my-ingress -o jsonpath='{.spec.rules[0].host}'</code>

1. Debug Pod:
<code>kubectl run -it --rm --restart=Never debug-pod --image=busybox -- sh</code>

1. Label Value:
<code>kubectl get rs my-replicaset -o jsonpath='{.metadata.labels.app}'</code>

1. Create Secret:
<code>kubectl create secret generic my-secret --from-literal=username=admin --from-literal=password=pass</code>

1. Rollback DaemonSet:
<code>kubectl rollout undo daemonset/my-daemonset</code>

1. Namespace Deployments:
<code>kubectl get deploy -n my-namespace</code>

1. ConfigMap Data:
<code>kubectl get cm my-configmap -o jsonpath='{.data.key}'</code>

1. DaemonSet History:
<code>kubectl rollout history daemonset/my-daemonset</code>

1. Service Ports:
<code>kubectl explain svc.spec.ports</code>
