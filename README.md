# SupDeVinci Equipe 1

## Récupérer le kubeconfig

REQUIS : ```aws cli``` et ```kubectl```

Pour récupérer le kubeconfig il faut exporter les variables AWS contenu dans ce repo en executant les commandes suivantes : 

```shell
export AWS_ACCESS_KEY_ID="MY_ACCESS_KEY_ID"
```

```shell
export AWS_SECRET_ACCESS_KEY="MY_SECRET_ACCESS_KEY"
```

```shell
export AWS_SESSION_TOKEN="MY_SESSION_TOKEN"
```

Ensuite il suffit de récupérer le kubeconfig avec le cli aws avec la commande suivante :

```shell
aws eks --region eu-west-1 update-kubeconfig --name eks-cluster-equipe-09
```

## Infrastructure 

Vous disposez d'un cluster Kubernetes déployé avec le service managé EKS de AmazonWebServices.
Pour déployer les applications un ArgoCD à été installé sur le cluster, ci dessous la liste des outils installés sur le cluster qui vous seront utiles pour le hackaton : 

    - app-grafana
    - app-loki
    - app-mimir
    - app-tempo
    - app-otel

Vous pouvez modifier ces applications.

Les applications suivantes ne doivent absolument pas être modifié :

    - app-argocd
    - argocd-configs
    - infra-apps
    - infra-nfs

Vous pouvez rajoutez d'autres applications si vous le souhaitez via argoCD ou non.

Il y a deux applications qui n'ont pas été déployées avec ArgoCD qui sont :

    - app-pokeshop
    - app-tracetest

Vous n'avez de toute façon pas besoin de toucher à cces applications.

## Url et identifiants de connexion

Les passwords des applications sont enregistrés dans les variables gitlab.

- argocd :
    - url : a753797ed306743d2a965e4916b1f37f-c1a2f4014f7cf7a4.elb.eu-west-1.amazonaws.com
    - user : admin
- grafana :
    - url : a72896e0a59504e9287b70b2f6848527-3a0b8633ae3acfab.elb.eu-west-1.amazonaws.com
    - user : admin
- pokeshop :
    - url : a412e7325e40b4493b95baa7b14658fa-1615178376.eu-west-1.elb.amazonaws.com
- tracetest :
    - url : aae662bd4fd3c4d79a9fc5038f701664-a83ffec49036515f.elb.eu-west-1.amazonaws.com:11633

Pour utilisez Pokeshop avec tracetest vous pouvez trouvez les documentations içi :

    - https://github.com/kubeshop/pokeshop/blob/master/docs/overview.md
    - https://tracetest.io/

Pour l'utilisation de TraceTest et de Pokeshop n'hésitez pas à nous contacter.    