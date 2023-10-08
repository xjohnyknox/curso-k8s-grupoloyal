# Ejercicios Dia 06.

En este dia, tenemos los siguientes ejercicios:

- [Ejercicios Dia 06.](#ejercicios-dia-06)
  - [1-node-labels](#1-node-labels)
  - [2-node-selector](#2-node-selector)
  - [3-pod-con-node-affinity](#3-pod-con-node-affinity)


## 1-node-labels

Vamos a ver qué labels ya tienen nuestros nodos:

Ejecutamos minikube con 2 nodos:
`minikube start --nodes 2 -p 2-nodos`

Luego revisamos con:

`kubectl get nodes --show-labels`

Y comenta, cuáles de esta lista aparecieron?

- [ ] kubernetes.io/arch
- [ ] kubernetes.io/hostname
- [ ] kubernetes.io/os

Y pega en el archivo: `respuesta_aqui.txt` la información.

## 2-node-selector

De los nodos que tiene tu cluster, vamos a agregar una etiqueta extra a 1 nodo (elije cuál):

`kubectl label nodes NOMBRE disco=ssd`

Ahora revisemos que si quedó:

`kubectl get nodes --show-labels | grep disco`


Ahora, en la carpeta ahi un fichero, revisalo y despliegalo.

`kubectl apply -f ejercicio2.yaml`

Y revisa en que nodo fue ubicado ese pod:

`kubectl get pods -o wide`

Ahora, edita el archivo `2.yaml`, para que se despliegue este otro pod en tu otro nodo (cambia su **nodeName**)

## 3-pod-con-node-affinity

Ahora vamos a desplegar un pod con node affinity.

