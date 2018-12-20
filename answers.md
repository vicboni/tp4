# Answers

Nom : Bonifacio
Prénom : Victor
NB : 2

# 1.
A quoi sert l'A/B testing ?
L'A/B testing permet de tester l'impact d'une version sur une portion des utilisateurs selectionné par rapport à une autre version.

Comment appliquer de l'A/B testing grâce à Istio ?
Avec Istio, on créée 2 routes correspondants à 2 versions différentes et on attibue à chaque route un poid compris entre 0 et 100 etla somme des 2 doit être égale à 100
ex: labels: version: v1 weight: 50
    labels: version: v3 weight: 50

# 2.
Comment simuler un problème de timeout avec Istio ?
En fasiant une "fault injection"

Comment le résoudre ?
On doit changer le timeout dans les configs

# 3.
Qu'est-ce que le canary release ?
Le canary release permet de réduire le risque lors de la msie en prod d'une version. On ré-oriente une portion des utilisateurs sur une nouvelle version.  

En quoi est-ce utile ?
Grâce à ça on peut tester une nouvelle version et éviter une sur-charge piur ensuite étendre la portion des utilisateurs petit à petit..

Comment l'implémenter dans Istio ?
On utilise le même principe que l'A/B Testing

# 4.

# 5.
Qu'est-ce qu'un Circuit Breaker ?
Il permet de re-router des flux si un service est trop lent ou bien s'il tombe

Comment l'implémenter dans un contexte Kubernetes ? En mettant des rgèles dans la config

# 6.
Pourquoi avoir besoin de mirrorer le traffic vers un autre composant ?
Ca permet de réduire le risque tout en modifiant la production. On aura ainsi un "mirror" du trafic situé sur le "request path" non critique pour le serveur

# 7.
Pourquoi bloquer le traffic vers un service ?
En cas de pannes d'un service, cela va également impacter les services voisins. Bloquer le traffic permet de contenir l'accumulation des retards 

Comment l'implémenter simplement avec Istio ?
Configurer le nombre max de requetes : istioctl create -f ratelimit-handler.yaml 
Configurer le quota de mémoire : istioctl create -f ratelimit-rule.yaml

# 8.
Quel est la problématique de tracing distribué ?
La problématique est la résolution des problèmes grâce à la compréhension du fonctionnement d'unne application

Quel est la spécification du tracing distribué et son implémentation dans Istio ?
Sa spécification est qu'on peut tracer tous les appels à toutes les applications pour les monitorer dans un dashboard

# 9.
Comment s'appelle l'outil de récupération des métrics ?
Promotheus

# 10.

# 11.
Comment s'appelle l'outil de visualisation des métrics ?
Graphana

# 12.
A quoi sert un servicegraph ?
il permet de faire apparaitre un schéma représentant tous les services et appels entre eux

Quel serait l'utilité dans le quotidien d'un ops ?
Dans ce tp il sert à visualier les services d'une application
