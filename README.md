# Notes 

# The deployment order doesn't matter; however, I think you should follow this order. 

1. elasticsearch-ss.yaml
2. logstash-deployment.yaml
3. filebeat-ds.yaml            ==>  ds stands for deamon set
4. metricbeat-ds.yaml          ==>  ds stands for deamon set
5. kibana-deployment.yaml
6. curator-cronjob.yaml

# Images from the above project 

#Workloads 

![image](https://github.com/joshking1/Kubernetes-monitoring-with-ELK-stack-Demo/assets/88409463/c8da6da5-ba27-45b2-9b93-0c570284c741)


#Services & Ingress 
![image](https://github.com/joshking1/Kubernetes-monitoring-with-ELK-stack-Demo/assets/88409463/697ccb36-f0b9-4540-ab51-7d4092adb0a4)


# Deploying a stateful application

Stateful applications save data to persistent disk storage for the server, clients, and other applications. 

An example of a stateful application is a database or key-value store to which other applications save and retrieve data.

Persistent storage can be dynamically provisioned, creating the underlying volumes on demand. 

In Kubernetes, you configure dynamic provisioning by creating a StorageClass. 

In GKE, a default StorageClass allows you to dynamically provision Compute Engine persistent disks.

Kubernetes uses the StatefulSet controller to deploy stateful applications as StatefulSet objects. 

Pods in StatefulSets are not interchangeable: each Pod has a unique identifier maintained no matter where it is scheduled.

Stateful applications differ from stateless applications, in which client data is not saved to the server between sessions.

# Deploying a stateless application 

# Deploying a stateless Linux application

Stateless applications do not store data or application state to the cluster or persistent storage. 

Instead, data and application states stay with the client, which makes stateless applications more scalable. 

For example, a frontend application is stateless: you deploy multiple replicas to increase its availability and scale down when demand is low, and the replicas do not need unique identities.

Kubernetes uses the Deployment controller to deploy stateless applications as uniform, non-unique Pods. 

Deployments manage the desired state of your application: how many Pods should run your application, what version of the container image should run, what the Pods should be labeled, and so on. The desired state can be changed dynamically through updates to the Deployment's Pod specification.

Stateless applications contrast stateful applications, which use persistent storage to save data and StatefulSets to deploy Pods with unique identities.

# Stateful Deployment 

Stateful Deployment:

A stateful deployment typically involves deploying applications that require persistent storage or maintain stateful data.
In this example, we'll create a stateful deployment for a WordPress application that uses a MySQL database.



