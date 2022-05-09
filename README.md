# Back Continuous Delivery with Jenkins in Kubernetes Engine Challenge Lab
Back Continuous Delivery with Jenkins in Kubernetes Engine Challenge Lab

### Download the source code
> gcloud config set compute/zone us-east1-d

> gsutil cp gs://spls/gsp051/continuous-deployment-on-kubernetes.zip .
> unzip continuous-deployment-on-kubernetes.zip
> cd continuous-deployment-on-kubernetes
### Provisioning Jenkins
> gcloud container clusters create jenkins-cd --num-nodes 2 --machine-type n1-standard-2 --scopes "https://www.googleapis.com/auth/source.read_write,cloud-platform"
> gcloud container clusters list
> gcloud container clusters get-credentials jenkins-cd
> kubectl cluster-info
### Setup Helm
> helm repo add jenkins https://charts.jenkins.io
> helm repo update
### Configure and Install Jenkins
> gsutil cp gs://spls/gsp330/values.yaml jenkins/values.yaml
> helm install cd jenkins/jenkins -f jenkins/values.yaml --wait
> kubectl get pods
> 
