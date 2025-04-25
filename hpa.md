# Workout on hpa.yml


```
➜  HPA git:(main) ✗ vim hpa.yml

➜  HPA git:(main) ✗ kubectl apply -f hpa.yml
horizontalpodautoscaler.autoscaling/apache-hpa created

➜  HPA git:(main) ✗ kubectl get hpa -n apache-ns
NAME         REFERENCE                      TARGETS             MINPODS   MAXPODS   REPLICAS   AGE
apache-hpa   Deployment/apache-deployment   cpu: <unknown>/5%   1         5         0          12s

➜  HPA git:(main) ✗ Handling connection for 5050
Handling connection for 5050
Handling connection for 5050
Handling connection for 5050

➜  HPA git:(main) ✗ kubectl get hpa -n apache-ns
NAME         REFERENCE                      TARGETS      MINPODS   MAXPODS   REPLICAS   AGE
apache-hpa   Deployment/apache-deployment   cpu: 1%/5%   1         5         3          56s

➜  HPA git:(main) ✗ kubectl get pods -n apache-ns
NAME                                 READY   STATUS    RESTARTS   AGE
apache-deployment-7784586dff-4s6mp   1/1     Running   0          15m
apache-deployment-7784586dff-j46t9   1/1     Running   0          15m
apache-deployment-7784586dff-q7rsw   1/1     Running   0          40m

➜  HPA git:(main) ✗ kubectl scale deployment apache-deployment --replicas=1 -n apache-ns
deployment.apps/apache-deployment scaled

➜  HPA git:(main) ✗ kubectl get pods -n apache-ns                                       
NAME                                 READY   STATUS      RESTARTS   AGE
apache-deployment-7784586dff-4s6mp   0/1     Completed   0          16m
apache-deployment-7784586dff-j46t9   0/1     Completed   0          16m
apache-deployment-7784586dff-q7rsw   1/1     Running     0          40m

➜  HPA git:(main) ✗ kubectl get pods -n apache-ns
NAME                                 READY   STATUS    RESTARTS   AGE
apache-deployment-7784586dff-q7rsw   1/1     Running   0          41m

```
