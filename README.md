# Travail pratique 2 - 420-w45-SF
## date: 04/07/2023
---
<br>

## Description: verification et container

### SECTION 1 ETAPE 1
---

capture d'ecran des commandes pour obtenir les versions des composants docker engine et docker compose et le resultat de ces commandes<br>

![version docker engine](./capture/engine&compose_version.png)


### SECTION 1 ETAPE 2
---
commande pour la creation d'un reseau
```bash
docker network create mon_reseau
```

commande pour creation des containers apache et mongodb
```bash
//apache
docker run -d -p 80:80 --name apache --network mon_reseau httpd:alpine

//mongodb
docker run --name mongodb --network mon_reseau -e MONGO_INITDB_ROOT_USERNAME=adminmongo -e MONGO_INITDB_ROOT_PASSWORD=EncoreUneAutreBD -v ./mongodb:/data/db -d mongo
```
<BR>
capture d'ecran reseau prive virtuel<br>

![reseau prive virtuel](./capture/verif_reseau.png)

capture d'ecran de l'utilisateur adminmongo

![adminmongo](./capture/log_adminmongo.png)

### REFERENCES
---

https://hub.docker.com/_/drupal<br>
https://doc.ubuntu-fr.org/tutoriel/console_commandes_de_base <br>
https://manpages.ubuntu.com/manpages/xenial/man1/docker.1.html