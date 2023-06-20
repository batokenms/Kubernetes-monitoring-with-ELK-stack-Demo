# Notes 

# Deploying a stateful application

Stateful applications save data to persistent disk storage for use by the server, by clients, and by other applications. 

An example of a stateful application is a database or key-value store to which data is saved and retrieved by other applications.

Persistent storage can be dynamically provisioned, so that the underlying volumes are created on demand. 

In Kubernetes, you configure dynamic provisioning by creating a StorageClass. 

In GKE, a default StorageClass allows you to dynamically provision Compute Engine persistent disks.

Kubernetes uses the StatefulSet controller to deploy stateful applications as StatefulSet objects. 

Pods in StatefulSets are not interchangeable: each Pod has a unique identifier that is maintained no matter where it is scheduled.

Stateful applications are different from stateless applications, in which client data is not saved to the server between sessions.

# Deploying a stateless application 

# Deploying a stateless Linux application

Stateless applications are applications which do not store data or application state to the cluster or to persistent storage. 

Instead, data and application state stay with the client, which makes stateless applications more scalable. 

For example, a frontend application is stateless: you deploy multiple replicas to increase its availability and scale down when demand is low, and the replicas have no need for unique identities.

Kubernetes uses the Deployment controller to deploy stateless applications as uniform, non-unique Pods. 

Deployments manage the desired state of your application: how many Pods should run your application, what version of the container image should run, what the Pods should be labelled, and so on. The desired state can be changed dynamically through updates to the Deployment's Pod specification.

Stateless applications are in contrast to stateful applications, which use persistent storage to save data and which use StatefulSets to deploy Pods with unique identities.

# Stateful Deployment 

Stateful Deployment:

A stateful deployment typically involves deploying applications that require persistent storage or maintain stateful data.
In this example, we'll create a stateful deployment for a WordPress application that uses a MySQL database.



