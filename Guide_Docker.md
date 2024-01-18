# Installation
###############################################################################
#######IMPORTANT#######
## Supprimer les anciennes versions de composants Docker installés (IMPORTANT !)
```bash
sudo apt-get remove docker docker-engine docker.io containerd runc
```

## Installation de quelques pré-requis
```bash
sudo apt-get install ca-certificates curl gnupg lsb-release
```
## Téléchargement de la clé GPG pour Docker
```bash
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg
```
## Ajout du dépôt APT pour Docker
```bash
echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu \
  $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
```

## Mise à jour du cache et installation des composants Docker
```bash
sudo apt-get update
sudo apt-get install docker-ce docker-ce-cli containerd.io
```

## Lister les versions de Docker disponibles
```bash
apt-cache madison docker-ce
```
Présents dans la seconde colonne, les ID de versions sont semblables au suivant:
`5:20.10.12~3-0~debian-buster`
## Installer une version spécifique de Docker
```bash
sudo apt-get install docker-ce=<VERSION_STRING> docker-ce-cli=<VERSION_STRING> containerd.io
```


# Permettre à un utilisateur non-root d'utiliser Docker
###############################################################################
## On crée le groupe docker
```bash
sudo groupadd docker
```
## On y ajoute l'utilisateur courant
```bash
sudo usermod -aG docker $USER
```




# Tester l'installation en lançant le container hello-world
```bash
docker run hello-world
```

# Afficher TOUS les conteneurs Docker présents
```bash
docker ps -a
```

Le conteneur est dans cet état car il n'a aucune opération supplémentaire à effectuer.
Pour le garder actif malgré cela, il doit avoir été lancé en mode interactif.

# Créer un conteneur à partir d'une image
```bash
docker run nom_image
```
# Créer un conteneur avec un nom spécifique
```bash
docker run --name=nom_conteneur nom_image
```
# Créer un conteneur qui sera supprimé automatiquement une fois stoppé
```bash
docker run --rm nom_image
```

# Démarrer un conteneur
```bash
docker start nom_ou_ID_conteneur
```
# Démarrer un conteneur en arrière-plan (mode détaché)
```bash
docker start -d nom_ou_ID_conteneur
```
# Démarrer un conteneur en mode interactif
```bash
docker start -it nom_ou_ID_conteneur
```
# Arrêter un conteneur
```bash
docker stop nom_ou_ID_conteneur
```

# Rechercher des images dans le hub docker
```bash
docker search termes_de_la_recherche
```
# Télécharger une image depuis le hub
```bash
docker pull nom_image
```
# Créer une image Docker à partir d'un conteneur
docker
# Se connecter à un hub
```bash
docker login URL_ou_IP_serveur_distant
```
# Se déconnecter du hub
```bash
docker logout
```
# Charger une image vers le hub
```bash
docker push nom_image
```
# Supprimer une image
docker
# 
```bash
docker image prune
```
# 
docker
# Consulter les logs d'un conteneur
```bash
docker logs nom_ou_ID_conteneur
```
# Suivre les logs d'un conteneur
```bash
docker logs -f nom_ou_ID_conteneur
```
# Récupérer l'adresse IP d'un conteneur
```bash
docker inspect -f '{{range.NetworkSettings.Networks}}{{.IPAddress}}{{end}}' nom_ou_ID_conteneur
```
# Lister tous les réseaux du daemon Docker
```bash
docker network ls
```
# Récupérer les adresses IP de tous les conteneurs d'un réseau donné
```bash
docker network inspect bridge -f '{{json .Containers}}'
```
# 
docker
# 
docker
# 
docker
# 
docker
# Créer un nouveau réseau Docker
```bash
docker network create nom_du_rx
```
# Connecter un conteneur à un réseau Docker
```bash
docker network connect nom_du_rx nom_ou_ID_conteneur
```
# Déconnecter un conteneur d'un réseau Docker (Le conteneur doit être actif)
```bash
docker network disconnect nom_du_rx nom_ou_ID_conteneur
```
# Supprimer un réseau Docker
```bash
docker network rm nom_du_rx
```
# 
docker
