# Ejercicio Final.

En este dia, tenemos los siguientes ejercicios:

- [Ejercicio Final.](#ejercicio-final)
  - [Creando un Namespace:](#creando-un-namespace)
  - [Creando un pod:](#creando-un-pod)
  - [Creando un replicaset:](#creando-un-replicaset)
  - [Creando un deployment:](#creando-un-deployment)
  - [Crea un ServiceAccount:](#crea-un-serviceaccount)




## Creando un Namespace:

Crea un Namespace llamado "ejercicio-final"

## Creando un pod:

## Creando un replicaset:

Crea un manifiesto para tener un RS, que use esta imagen: gcr.io/google_samples/gb-frontend:v3
Y que tenga 3 replicas.
Crealo en su propio namespace: replica-gb

## Creando un deployment:

Crea un 

## Crea un ServiceAccount:

Create a ServiceAccount named "exercise-serviceaccount" within the "exercise-namespace."
Create a ClusterRole:

Create a ClusterRole named "exercise-clusterrole" that has permissions to list Pods and Services across all namespaces.
Bind the ServiceAccount and ClusterRole:

Create a ClusterRoleBinding to bind the "exercise-serviceaccount" to the "exercise-clusterrole."
Create Deployments:

Create two Deployments within the "exercise-namespace."
Deployment 1: Name it "app-deployment-1."
Deployment 2: Name it "app-deployment-2."
Each Deployment should have a label indicating its purpose (e.g., "app=exercise-app-1" for Deployment 1, and "app=exercise-app-2" for Deployment 2).
Affinity Rules:

Define affinity rules for both Deployments:
Deployment 1 should have an anti-affinity rule to ensure it does not run on the same node as Deployment 2.
Deployment 2 should have an affinity rule to ensure it runs on the same node as Deployment 1.
Labels:

Apply labels to Pods in each Deployment:
Pods in "app-deployment-1" should have a label "tier=frontend."
Pods in "app-deployment-2" should have a label "tier=backend."
Validation:

Deploy the resources and verify that the Deployments run in separate nodes due to the anti-affinity rule and that the labels are correctly applied to the Pods.
Documentation:

Provide a README or documentation file explaining the purpose of each resource, how they are connected, and how the affinity and anti-affinity rules work in this context.