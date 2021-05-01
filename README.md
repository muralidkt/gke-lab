
 Prerequesites
 * [GCP Account and Project ](https://cloud.google.com/free)
 * [ GCloud CLI Configured ](https://cloud.google.com/sdk/docs/install) 

# Provisioning GKE Cluster
* Using GCloud CLI
* Using Terraform

## GKE Cluster Provisiong using gcloud CLI

Enable compute and container APIs
```
gcloud services enable compute.googleapis.com
gcloud services enable container.googleapis.com
```

List the GKE Clusters
```
gcloud container clusters list
```

Check GKE Cluster create options from CLI
```
gcloud container clusters create --help
````

Create GKE Cluster
```
gcloud container clusters create gke-dev-cluster --zone europe-west3-a
```
List the cluster
````
gcloud container clusters list
````

Get the credentials
```
gcloud container clusters get-credentials gke-dev-cluster
````

Explore the cluster with kubectl command
````
kubectl get node
kubectl get node -A
````


Delete the cluster
````
gcloud container clusters delete gke-dev-cluster --zone europe-west3-a
````


## GKE Cluster Provisioning using Terraform
We are going to create a private cluster, you can learn more about the private cluster [here](https://cloud.google.com/kubernetes-engine/docs/how-to/private-clusters)

Clone this repository
````
git clone https://github.com/muralidkt/gke-lab.git
````


Move to the path gke/iac/terraform
````
cd /gke-lab/iac/terraform
````


Initialise terraform
````
terraform init
````


Run terraform plan to see the list of resources
````
terraform plan
````


Apply terraform to create the cluster
````
terrform apply
````


Destroy the cluster
````
terraform destory
````
