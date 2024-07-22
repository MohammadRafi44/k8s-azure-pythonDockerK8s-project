# k8s-azure-pythonDockerK8s-project
#K8s Azure >> Python - Docker - AKS

******************************************************* 
Here we will create a local docker container, run thru the docker build commands, create kubernetes cluster commands and deploy docker image into your aks cluster
******************************************************* 
az account show
az login
docker images
docker build -t pythonregis123890/pythonrepo123890:v1 .
docker run -p 5000:5000 pythonregis123890/pythonrepo123890:v1
 
az acr create --resource-group LearningKuberpythones123890 --name pythonregis123890 --sku Basic
az acr login -n pythonregis123890
docker tag pythonregis123890/pythonrepo123890:v1 pythonregis123890.azurecr.io/pythonrepo123890:v1
docker push pythonregis123890.azurecr.io/pythonrepo123890:v1
az aks create --name kubcluster123890 --resource-group LearningKuberpythones123890 --node-count 1 --generate-ssh-keys --attach-acr pythonregis123890
az aks get-credentials --resource-group LearningKuberpythones123890 --name kubcluster123890
kubectl apply -f eks-deploy-from-ecr.yaml
kubectl get service
kubectl get pods
kubectl get nodes

#access the application 

