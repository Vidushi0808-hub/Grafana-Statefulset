# GRAFANA

## Type the following commands to deploy the statefulset of grafana

- Create the configmap using the following command
``` kubectl create -f grafana-datasource-config.yaml ```

- Create the statefulset
``` kubectl create -f grafana.yaml ```

- You can check the created statefulset using the following command
 ``` kubectl get statefulsets --namespace=monitoring ```



## Connecting To Grafana Dashboard 

- First, get the Grafana pod name
``` kubectl get pods --namespace=monitoring ```

- Execute the following command with your pod name to access Grafana from localhost or host-ip port 3000
``` kubectl port-forward grafana-ss-0 3000:3000 -n monitoring ``` ( Note: Replace your pod name though most probably it will be the same )

- Exposing Prometheus as a Service ( if you dont want to use port-forward )
``` kubectl create -f service.yaml --namespace=monitoring ```

### Connecting to Grafana service
- First, get the external IP of the node that has grafana running. 
- Open browser and type, 
         Node ExternalIp:32000

##Chart Number to import - ``` 8588 ```

## General Commands 

- How to set any working namespace
```kubectl config set-context --current --namespace=monitoring```

- How to view the current namespace 
```kubectl config view | grep namespace```
