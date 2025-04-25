# Watching the autoscaling of hpa on load-testing

```
➜  Desktop kubectl get all -n apache-ns     
NAME                                     READY   STATUS    RESTARTS   AGE
pod/apache-deployment-7784586dff-5gxn7   1/1     Running   0          12m
pod/load-generator                       1/1     Running   0          15m

NAME                     TYPE        CLUSTER-IP      EXTERNAL-IP   PORT(S)    AGE
service/apache-service   ClusterIP   10.96.226.197   <none>        5050/TCP   70m

NAME                                READY   UP-TO-DATE   AVAILABLE   AGE
deployment.apps/apache-deployment   1/1     1            1           74m

NAME                                           DESIRED   CURRENT   READY   AGE
replicaset.apps/apache-deployment-7784586dff   1         1         1       74m

NAME                                             REFERENCE                      TARGETS      MINPODS   MAXPODS   REPLICAS   AGE
horizontalpodautoscaler.autoscaling/apache-hpa   Deployment/apache-deployment   cpu: 1%/5%   1         5         1          35m
➜  Desktop kubectl get all -n apache-ns
NAME                                     READY   STATUS    RESTARTS   AGE
pod/apache-deployment-7784586dff-5gxn7   1/1     Running   0          12m
pod/load-generator                       1/1     Running   0          15m

NAME                     TYPE        CLUSTER-IP      EXTERNAL-IP   PORT(S)    AGE
service/apache-service   ClusterIP   10.96.226.197   <none>        5050/TCP   70m

NAME                                READY   UP-TO-DATE   AVAILABLE   AGE
deployment.apps/apache-deployment   1/1     1            1           74m

NAME                                           DESIRED   CURRENT   READY   AGE
replicaset.apps/apache-deployment-7784586dff   1         1         1       74m

NAME                                             REFERENCE                      TARGETS      MINPODS   MAXPODS   REPLICAS   AGE
horizontalpodautoscaler.autoscaling/apache-hpa   Deployment/apache-deployment   cpu: 1%/5%   1         5         1          35m
➜  Desktop kubectl get all -n apache-ns
NAME                                     READY   STATUS    RESTARTS   AGE
pod/apache-deployment-7784586dff-5gxn7   1/1     Running   0          12m
pod/load-generator                       1/1     Running   0          15m

NAME                     TYPE        CLUSTER-IP      EXTERNAL-IP   PORT(S)    AGE
service/apache-service   ClusterIP   10.96.226.197   <none>        5050/TCP   70m

NAME                                READY   UP-TO-DATE   AVAILABLE   AGE
deployment.apps/apache-deployment   1/1     1            1           74m

NAME                                           DESIRED   CURRENT   READY   AGE
replicaset.apps/apache-deployment-7784586dff   1         1         1       74m

NAME                                             REFERENCE                      TARGETS      MINPODS   MAXPODS   REPLICAS   AGE
horizontalpodautoscaler.autoscaling/apache-hpa   Deployment/apache-deployment   cpu: 1%/5%   1         5         1          35m

➜  Desktop kubectl get all -n apache-ns
NAME                                     READY   STATUS    RESTARTS   AGE
pod/apache-deployment-7784586dff-5gxn7   1/1     Running   0          12m
pod/load-generator                       1/1     Running   0          16m

NAME                     TYPE        CLUSTER-IP      EXTERNAL-IP   PORT(S)    AGE
service/apache-service   ClusterIP   10.96.226.197   <none>        5050/TCP   71m

NAME                                READY   UP-TO-DATE   AVAILABLE   AGE
deployment.apps/apache-deployment   1/1     1            1           75m

NAME                                           DESIRED   CURRENT   READY   AGE
replicaset.apps/apache-deployment-7784586dff   1         1         1       75m

NAME                                             REFERENCE                      TARGETS      MINPODS   MAXPODS   REPLICAS   AGE
horizontalpodautoscaler.autoscaling/apache-hpa   Deployment/apache-deployment   cpu: 1%/5%   1         5         1          35m
➜  Desktop kubectl get all -n apache-ns
NAME                                     READY   STATUS              RESTARTS   AGE
pod/apache-deployment-7784586dff-5gxn7   1/1     Running             0          12m
pod/apache-deployment-7784586dff-p5zm8   0/1     ContainerCreating   0          3s
pod/apache-deployment-7784586dff-trk9g   0/1     ContainerCreating   0          3s
pod/apache-deployment-7784586dff-vnfgr   0/1     Pending             0          3s
pod/load-generator                       1/1     Running             0          16m

NAME                     TYPE        CLUSTER-IP      EXTERNAL-IP   PORT(S)    AGE
service/apache-service   ClusterIP   10.96.226.197   <none>        5050/TCP   71m

NAME                                READY   UP-TO-DATE   AVAILABLE   AGE
deployment.apps/apache-deployment   1/4     4            1           75m

NAME                                           DESIRED   CURRENT   READY   AGE
replicaset.apps/apache-deployment-7784586dff   4         4         1       75m

NAME                                             REFERENCE                      TARGETS       MINPODS   MAXPODS   REPLICAS   AGE
horizontalpodautoscaler.autoscaling/apache-hpa   Deployment/apache-deployment   cpu: 70%/5%   1         5         1          35m
➜  Desktop kubectl get all -n apache-ns
NAME                                     READY   STATUS              RESTARTS   AGE
pod/apache-deployment-7784586dff-5gxn7   1/1     Running             0          12m
pod/apache-deployment-7784586dff-p5zm8   0/1     ContainerCreating   0          4s
pod/apache-deployment-7784586dff-trk9g   0/1     ContainerCreating   0          4s
pod/apache-deployment-7784586dff-vnfgr   1/1     Running             0          4s
pod/load-generator                       1/1     Running             0          16m

NAME                     TYPE        CLUSTER-IP      EXTERNAL-IP   PORT(S)    AGE
service/apache-service   ClusterIP   10.96.226.197   <none>        5050/TCP   71m

NAME                                READY   UP-TO-DATE   AVAILABLE   AGE
deployment.apps/apache-deployment   2/4     4            2           75m

NAME                                           DESIRED   CURRENT   READY   AGE
replicaset.apps/apache-deployment-7784586dff   4         4         2       75m

NAME                                             REFERENCE                      TARGETS       MINPODS   MAXPODS   REPLICAS   AGE
horizontalpodautoscaler.autoscaling/apache-hpa   Deployment/apache-deployment   cpu: 70%/5%   1         5         1          35m
➜  Desktop kubectl get all -n apache-ns
NAME                                     READY   STATUS              RESTARTS   AGE
pod/apache-deployment-7784586dff-5gxn7   1/1     Running             0          12m
pod/apache-deployment-7784586dff-p5zm8   1/1     Running             0          5s
pod/apache-deployment-7784586dff-trk9g   0/1     ContainerCreating   0          5s
pod/apache-deployment-7784586dff-vnfgr   1/1     Running             0          5s
pod/load-generator                       1/1     Running             0          16m

NAME                     TYPE        CLUSTER-IP      EXTERNAL-IP   PORT(S)    AGE
service/apache-service   ClusterIP   10.96.226.197   <none>        5050/TCP   71m

NAME                                READY   UP-TO-DATE   AVAILABLE   AGE
deployment.apps/apache-deployment   3/4     4            3           75m

NAME                                           DESIRED   CURRENT   READY   AGE
replicaset.apps/apache-deployment-7784586dff   4         4         3       75m

NAME                                             REFERENCE                      TARGETS       MINPODS   MAXPODS   REPLICAS   AGE
horizontalpodautoscaler.autoscaling/apache-hpa   Deployment/apache-deployment   cpu: 70%/5%   1         5         1          35m
➜  Desktop kubectl get all -n apache-ns
NAME                                     READY   STATUS              RESTARTS   AGE
pod/apache-deployment-7784586dff-5gxn7   1/1     Running             0          12m
pod/apache-deployment-7784586dff-p5zm8   1/1     Running             0          7s
pod/apache-deployment-7784586dff-trk9g   0/1     ContainerCreating   0          7s
pod/apache-deployment-7784586dff-vnfgr   1/1     Running             0          7s
pod/load-generator                       1/1     Running             0          16m

NAME                     TYPE        CLUSTER-IP      EXTERNAL-IP   PORT(S)    AGE
service/apache-service   ClusterIP   10.96.226.197   <none>        5050/TCP   71m

NAME                                READY   UP-TO-DATE   AVAILABLE   AGE
deployment.apps/apache-deployment   3/4     4            3           75m

NAME                                           DESIRED   CURRENT   READY   AGE
replicaset.apps/apache-deployment-7784586dff   4         4         3       75m

NAME                                             REFERENCE                      TARGETS       MINPODS   MAXPODS   REPLICAS   AGE
horizontalpodautoscaler.autoscaling/apache-hpa   Deployment/apache-deployment   cpu: 70%/5%   1         5         1          35m


....
after some it scale down to 1 pod

```
