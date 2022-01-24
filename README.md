###### acme-fitness-4-site
##### AZURE - US EAST INSTRUCTIONS #####
###### in aks-us-east deploy the front end
###### start with the Istio gateways.
kubectl apply -f aks-fe-gateway.yaml

###### deploy the secrets.
kubectl apply -f secrets.yaml

###### Before deploying the application itself, change the YAML file
###### to indicate the name of the Catalog service in the GNS the Frontend will 
###### try to reach. Select a GNS domains name (e.g. acmegns.local)
###### Edit aks-us-east-front-end.yaml and search for “catalog”.  Edit spec.containers.env.value:   
###### and change it to somthing like acmegns.com
###### this deploys the front end:  shopping service, user service, user DB:
kubectl apply -f aks-us-east-front-end.yaml


##### AKS - US WEST INSTRUCTIONS #####
###### in aks-us-west deploy the front end
###### start with the Istio gateways.
kubectl apply -f aks-fe-gateway.yaml

###### deploy the secrets.
kubectl apply -f secrets.yaml

###### Before deploying the application itself, we need to change the YAML file
###### to indicate what will be the name of the Catalog service the Frontend will 
###### try to reach. Select a GNS domains name (e.g. acmegns.local)
###### Edit aks-us-west-front-end.yaml and search for “catalog”.  Edit spec.containers.env.value:   
###### and change it to somthing like acmegns.com
###### this deploys the front end:  shopping service, user service, user DB:
kubectl apply -f aks-us-west-front-end.yaml


##### AWS - US EAST INSTRUCTIONS #####
###### deploy the secrets.
kubectl apply -f secrets.yaml

###### Deploy the backend:
kubectl apply -f aws-us-east-be.yaml


##### AWS - US WEST INSTRUCTIONS #####
###### deploy the secrets.
kubectl apply -f secrets.yaml

###### Deploy the backend:
kubectl apply -f aws-us-west-be.yaml
