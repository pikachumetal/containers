# containers

To connect to builde rmachine from WLS:
```bash
ssh -i .ssh/fabmedical adminfabmedical@40.113.137.9
```

```
{
  "appId": "b196c8e7-a9f4-4f1c-9455-27b664cd8957",
  "displayName": "azure-cli-2019-06-27-17-03-16",
  "name": "http://Fabmedical-sp-mdsf",
  "password": "44d983ed-746c-432a-be07-9f5b903e00ff",
  "tenant": "cfa59073-695f-4500-8ad5-ab5e384a30c2"
}
```

```bash
docker login fabmedicalmdsf.azurecr.io -u fabmedicalmdsf -p bhbkkJO/8mXehi5taTxGCJZllw17Hmmi
docker tag content-web fabmedicalmdsf.azurecr.io/content-web
docker tag content-api fabmedicalmdsf.azurecr.io/content-api
docker push fabmedicalmdsf.azurecr.io/content-web
docker push fabmedicalmdsf.azurecr.io/content-api
```

```bash
docker tag fabmedicalmdsf.azurecr.io/content-web:latest fabmedicalmdsf.azurecr.io/content-web:v1
docker tag fabmedicalmdsf.azurecr.io/content-api:latest fabmedicalmdsf.azurecr.io/content-api:v1
docker images
```

```bash
docker pull fabmedicalmdsf.azurecr.io/content-web
docker pull fabmedicalmdsf.azurecr.io/content-web:v1
```

```bash
docker pull fabmedicalmdsf.azurecr.io/content-api
docker pull fabmedicalmdsf.azurecr.io/content-api:v1
```

Kubernetes dashboard:
```bash
az aks get-credentials --name fabmedical-mdsf --resource-group fabmedical-mdsf
kubectl create clusterrolebinding kubernetes-dashboard --clusterrole=cluster-admin --serviceaccount=kube-system:kubernetes-dashboard
az aks browse --name fabmedical-mdsf --resource-group fabmedical-mdsf
```

```
mongodb://fabmedical-mdsf:NivQnpnTAMo0kgkeAwvw3F5t3hj5bH6xnkoBopuvyYkraXzgnYDR3lKexFRvRDBDjvg7Ab272fJvUaSPPhqD8A%3D%3D@fabmedical-mdsf.documents.azure.com:10255/contentdb?ssl=true&replicaSet=globaldb
```

```
echo -n "mongodb://fabmedical-mdsf:NivQnpnTAMo0kgkeAwvw3F5t3hj5bH6xnkoBopuvyYkraXzgnYDR3lKexFRvRDBDjvg7Ab272fJvUaSPPhqD8A%3D%3D@fabmedical-mdsf.documents.azure.com:10255/contentdb?ssl=true&replicaSet=globaldb" | base64 -w 0

bW9uZ29kYjovL2ZhYm1lZGljYWwtbWRzZjpOaXZRbnBuVEFNbzBrZ2tlQXd2dzNGNXQzaGo1Ykg2eG5rb0JvcHV2eVlrcmFYemduWURSM2xLZXhGUnZSREJEanZnN0FiMjcyZkp2VWFTUFBocUQ4QSUzRCUzREBmYWJtZWRpY2FsLW1kc2YuZG9jdW1lbnRzLmF6dXJlLmNvbToxMDI1NS9jb250ZW50ZGI/c3NsPXRydWUmcmVwbGljYVNldD1nbG9iYWxkYg==%
```

```bash
kubectl set image deployment/api api=fabmedicalmdsf.azurecr.io/content-api:latest
```

http://fabmedical-mdsf-ingress.westeurope.cloudapp.azure.com
