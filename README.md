<h1>Introduce Kubernetes</h1>

Using : minikube

<h3>1. ASDF</h3>

- <b>$</b> git clone https://github.com/asdf-vm/asdf.git ~/.asdf --branch v0.8.1
  
<h5>Minikube</h5>

- <b>$</b> asdf plugin-add minikube 
- <b>$</b> asdf list-all minikube
- <b>$</b> asdf install minikube 1.21.0
- <b>$</b> asdf global minikube 1.21.0

<h5>Kubectx</h5>

- <b>$</b> asdf plugin-add kubectx
- <b>$</b> asdf list-all kubectx
- <b>$</b> asdf install kubectx 0.9.3
- <b>$</b> asdf global kubectx 0.9.3

<h5>Kubectl</h5>

- <b>$</b> asdf plugin-add kubectl
- <b>$</b> asdf list-all kubectl
- <b>$</b> asdf install kubectl 1.21.1
- <b>$</b> asdf global kubectl 1.21.1

<h3>2. Run</h3>

- <b>$</b> minikube start --driver=docker

<h3>3. Some commands : Kubectl</h3>

Get data about minikube settings (IP, ...)<br/>
```$ kubectl get nodes -o wide```<br/>

Get data about pods / services / etc...<br/>
```$ kubectl get all```<br/>

Deploy into the current folder your config<br/>
```$ kubectl apply -f .```<br/>

Delete into the current folder your config<br/>
```$ kubectl delete -f .```<br/>

Exec a pod and enter (like a docker container)<br/>
```$ kubectl exec -it wp-app-748889b9c6-jflt6 bash```<br/>

Give you some information about the given element<br/>
```$ kubectl describe pods wp-app-748889b9c6-jflt6```<br/>

Give you logs about the given element<br/>
```$ kubectl logs wp-app-748889b9c6-jflt6```<br/>

Change the config of the deployment to up or reduce pods replicas<br/>
```$ kubectl scale deployment/wp-app --replicas=0```<br/>

Example of inline pod creation which returns the YAML config and write it into the given file<br/>
```$ kubectl create deployment mysql --image=wordpress:5.7 --port=3306 --replicas=2 --dry-run=client -o yaml > deployment.wordpress.yaml```<br/>

Example of inline secret creation (like ^)<br/>
```$ kubectl create secret generic <name_of_the_secret> --from-file=.env --dry-run=client -o yaml```

<h3>4. Some commands : Kompose</h3>

Convert a docker-compose.yml into multiple files pre-configured <br/>
```$ kompose convert```<br/>

