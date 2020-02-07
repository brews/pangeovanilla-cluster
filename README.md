# Pangeo vanilla cluster deployment

Google Kubernetes Engine (GKE) cluster setup for a vanilla Pangeo deployment.

## Cluster setup

Deploy hardware with `gcloud deployment-manager deployments create pangeovanilla-cluster-deployment --config pangeovanilla-cluster-deployment.yaml --labels env=dev,app=pangeo`.

Update the cluster deployment with `gcloud deployment-manager deployments update pangeovanilla-cluster-deployment --config pangeovanilla-cluster-deployment.yaml`, if hardware changes have an update path. You may need to delete the existing deployment and re-create it, otherwise. 

Delete the deployment with `gcloud deployment-manager deployments delete pangeovanilla-cluster-deployment`.

## Notes

This deployment creates a fixed external IP address. This address needs to be assigned to the jupyterhub loadbalancer. The default name of the address is "pangeo-jhubip-address" and so you can find this fixed IP with: `gcloud compute addresses list | grep pangeo-jhubip-address`

