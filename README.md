This is simple demo of Running .net Core app on Minikube-local version of kubernetes

Following are commands to follow:(Docker & Minikube Windows as Host OS and Linux gust OS)
Use project Path:
minikube start

minikube docker-env

@FOR /f "tokens=* delims=^L" %i IN ('minikube docker-env') DO %i

docker build -t coreappwithdocker .

kubectl create -f deployment.yaml

kubectl get deployments

kubectl get pods---> Display list of pods with status running

kubectl expose deployment coreappwithdocker --type=NodePort-->display message that it is exposed

minikube service coreappwithdocker --url

