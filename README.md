#  Readme complémentaire Killian x Guillaume

## Installer nodeJs dans un premier temps si vous ne l'avez pas : 
- Linux ( DEBIAN x UBUNTU )  : [ici](https://nodejs.org/en/download/package-manager#debian-and-ubuntu-based-linux-distributions)
- LINUX (CentOS, Fedora, Red Hat) : [ici](https://nodejs.org/en/download/package-manager#centos-fedora-and-red-hat-enterprise-linux)

******

### Ensuite installer le package git sur votre distribution : 
```
sudo apt-get install git-all

```

******





# Maintenant il vous faut configurer votre GIT grace à une clef SSH : 

******

### Étape 1 : Vérifier si vous avez une clé SSH existante Ouvrez un terminal et exécutez la commande suivante :

```
ls -al ~/.ssh
```

Cela affichera la liste des fichiers dans votre répertoire .ssh. Si vous voyez des fichiers nommés id_rsaet id_rsa.pub, 
vous avez déjà une clé SSH. Vous pouvez passer à l'étape 3. Sinon, passer à l'étape 2.

******


### Étape 2 : Générer une nouvelle paire de clés SSH Dans votre terminal, exécuter la commande suivante pour générer une nouvelle paire de clés SSH :


```
ssh-keygen -t rsa -b 4096 -C "votre@email.com"

```

******


### Étape 3 : Ajouter votre clé SSH à l'agent SSH L'agent SSH est un programme qui gère vos clés SSH. 

```
eval "$(ssh-agent -s)"
ssh-add ~/.ssh/id_rsa

```

******


### Étape 4 : Ajoutez la clé SSH à votre compte Git Copiez le contenu de votre clé publique en utilisant la commande suivante :

```
cat ~/.ssh/id_rsa.pub
```

Cela affichera la clé publique. Copiez toute la clé.
Ensuite, ouvrez votre compte Git (par exemple, sur GitHub, GitLab, ou Bitbucket) et ouvrez les paramètres du compte ou des clés SSH.
Ajoutez une nouvelle clé SSH et collez la clé publique que vous avez copiée précédemment.

******


### Étape 5 : Tester la connexion SSH Pour tester si votre clé SSH est configurée correctement, exécutez la commande suivante :

```
ssh -T git@github.com

```




******

# La suite ? 

Après avoir fait tous ça vous pouvez suivre le tuto de Guillaume en toutes tranquillités ( enfin presque).
[https://www.pebble.support/50/application-frontend](https://www.pebble.support/50/application-frontend)



******

# Maintenant nous allons voir pour l'authentification et surtout le tuto de Killian ! 
Après avoir suivi tous le tuto il vous manquera quelques informations pour que ça marche complètement

******

## Dans le config .json changer la partie "dev" en : 


```
dev": {
            "pas": true,
            "authServer": "authenticatorlocalonline-utuvyi37ea-ew.a.run.app/licences",
            "tls": true
        }
```

******  

## Dans votre nouveau projet ajouter un nouveau fichier " .env.json puis copier / coller cette configuration :

```
{
    "env": "dev",
    "api": {
        "dev": {
            "pas": true,
            "authServer": "authenticatorlocalonline-utuvyi37ea-ew.a.run.app",
            "tls": true
        }
    }
}
```

