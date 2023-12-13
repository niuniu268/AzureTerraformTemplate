# Terraform Template for Azure ServiceBus and K8S

- Get Subscription, CLIENT_SECRET and TENANT_ID

```
az account set --subscription 9365ab69-ca62-4339-9f92-cbda19d0c9c5
```

```
az ad sp create-for-rbac --role="Contributor" --scopes="/subscription/9365ab69-ca62-4339-9f92-cbda19d0c9c5"
 
az account set --subscription="9365ab69-ca62-4339-9f92-cbda19d0c9c5"
```

```
az login --service-principal -u CLIENT_ID -p CLIENT_SECRET --tenant TENANT_ID
```

```
terraform init
terraform validate
terraform apply
```

## Check Azure ServiceBus message by Golang

`https://github.com/niuniu268/AzureServiceBus.git`

## Check gRPC gateway
`https://github.com/niuniu268/grpc-gateway`

docker build 

``` 
docker build -t your-image-name:tag .
```

Kubernetes Service deploy

- Configure `kubectl` to use AKS cluster

```
az aks get-credentials --resource-group <your-resource-group> --name <your-aks-cluster-name>
```

- Apply the Kubernetes manifests

```
kubectl apply -f deployment.yaml
kubectl apply -f service.yaml
```

- LoadBalancer's external IP

```
kubectl get svc your-app
```