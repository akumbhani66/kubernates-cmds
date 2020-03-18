# kubernates-cmds

1. To create namespace: 

  `kubectl create namespace name`

2. To get namespaces: 

  `kubectl get namespace`
  
3. To deploy POD: 

  `kubectl apply -f sample-pod.yaml -n nameOfNamespace`
  
4. To get PODs running inside cluster: 

  `kubectl get pod -n nameOfNamespace`
  
5. Pod is running inside of the Kubernetes cluster, we need to forward a local port to the Pod’s containerPort to access the running app locally: 

  `kubectl port-forward pods/sample-pod -n nameOfNamespace 5000:5000`
  
6. To delete POD inside namespace: 

  `kubectl delete pod sample-pod -n nameOfNamespace`

7. Roll out the Deployment : 

  `kubectl apply -f sample-deployment.yaml -n nameOfNamespace`
  
8. To get Deployment, should be up and running in your cluster: 

  `kubectl get deploy -n nameOfNamespace`
  
9. pull up the individual Pods that are managed by the Deployment controller: 

  `kubectl get pod -n nameOfNamespace`
  
10. To access the app, we have to forward a port inside of the cluster: 

  `kubectl port-forward deployment/sample-dep -n nameOfNamespace 5000:5000`

> LoadBalancer

11. A Kubernetes Deployment allows the operator to flexibly scale a Pod template up or down, as well as manage rollouts and template updates. To create a stable network endpoint for this set of running Pod replicas, you can create a Kubernetes Service,
    
To create the Service : 

  `kubectl apply -f sample-service.yaml -n nameOfNamespace`
  
12. It may take a bit of time for Kubernetes to provision the cloud Load Balancer. You can track progress using the -w watch flag 

    `kubectl get svc -w`
