## Creando un Namespace:

Crea un Namespace llamado `ejercicio-final`

1.- fichero yaml con el nombre del namespace ejercicio-final-name.yaml

2.- desplegamos el yaml , kubectl apply -f ejercicio-final-name.yaml 


C:\disco-d\cursos\kubernetes\repo-git-curso\ejercicios\FINAL>kubectl apply -f ejercicio-final-name.yaml
namespace/jercicio-final created

C:\disco-d\cursos\kubernetes\repo-git-curso\ejercicios\FINAL>kubectl get namespace
NAME              STATUS   AGE
default           Active   21m
jercicio-final    Active   31s
kube-node-lease   Active   21m
kube-public       Active   21m
kube-system       Active   21m


## Creando un pod:

Crea un pod que use labels: 
`ejercicio:final`

1.- creamos fichero pod.yaml con las etiquetas, requeridas
2.- ejecutamos kubectl apply -f pod.yaml
3.- comprobamos la etiqueta. con kubectl get nodes --show-labels
NAME    READY   STATUS    RESTARTS   AGE   LABELS
nginx   1/1     Running   0          6s    ejercicio=final



## Creando un replicaset:

Crea un manifiesto para tener un RS, que use esta imagen: `gcr.io/google_samples/gb-frontend:v3`
Y que tenga `3 replicas`.
Crealo en su propio namespace: `replica-gb`

1.- creamos fichero yaml , para el namespace name-replica-yaml
2.- creamos el fichero yaml, para el replicaset con los datos indicados replicas.yaml
3.- ejecutamos primero el name-replica.yaml, kubectl aplly -f name-replica.yaml
4.- desplegamos el replicaset, kubectl apply -f replicas.yaml 

y comprobamos

C:\disco-d\cursos\kubernetes\repo-git-curso\ejercicios\FINAL>kubectl get namespace
NAME              STATUS   AGE
default           Active   59m
jercicio-final    Active   38m
kube-node-lease   Active   59m
kube-public       Active   59m
kube-system       Active   59m
replica-gb        Active   53s

C:\disco-d\cursos\kubernetes\repo-git-curso\ejercicios\FINAL>kubectl get pods --namespace replica-gb
NAME             READY   STATUS    RESTARTS   AGE
frontend-4rrwg   1/1     Running   0          86s
frontend-f55tg   1/1     Running   0          86s
frontend-pw8ch   1/1     Running   0          86s


## Creando un deployment:

Crea un deployment con 3 replicas, de la imagen nginx, con el comando sleep 3600.

Que incluya el label: 

`tipo: deployment`

1.- creamos el fichero yaml, deployment.yaml 
2.- desplegamos el yaml con 


## Crea un ServiceAccount:

Crea un **ServiceAccount** llamado "ejercicio-SA" dentro del namespace: `ejercicio-final`

1.- deplegamos  el yaml ejercico-final-name.yaml, para tener el namespace indicado. kubectl apply -f ejercicio-final-name.yaml
2.- creamos y desplegamos el fichero yaml sc.yaml. kubectl apply -f sc.yaml

debido a un problema con los RFC el service acount tiene que llamarse ejecercio-sa, ay que con mayusculas no lo permite.

The ServiceAccount "ejercicio-SA" is invalid: metadata.name: Invalid value: "ejercicio-SA": a lowercase RFC 1123 subdomain must consist of lower case alphanumeric characters, '-' or '.', and must start and end with an alphanumeric character (e.g. 'example.com', regex used for validation is '[a-z0-9]([-a-z0-9]*[a-z0-9])?(\.[a-z0-9]([-a-z0-9]*[a-z0-9])?)*')


## Crea un ClusterRole

Crea un **ClusterRole** llamado "ejercicio-clusterrole" que tenga permisos para listar, crear y borrar pods y servicios en **todos los namespaces**

Aplica el Binding apropiado a ese ClusterRole para el ejercicio-SA y ejercicio-clusterrole

creamos el fichero rbac y aplicamos con kubectl apply -f rbac.yaml

## Affinity Rules:



creamos los ficheros Yaml deployment1 y deploiment2 con las configuraciones pertinentes.

aplicamos 


