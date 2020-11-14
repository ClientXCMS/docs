### Base de données

## Introduction 
Pour stocker les données, CLIENTX utilise le système relationnel MySQL. Une base est obligatoire (vierge ou non) pour contenir les tables nécessaires au CM. PDO (PHP Data Objets) est utilisé pour interagir avec la base. Il faut donc que l'extension ainsi que PDO MySQL soit installé sur votre système.

## Connecxion
Les informations de connection à la base sont demandés dans le ```.env```. Ce fichier ne doit pas être versionner. Voici un exemple
```
DB_HOST=127.0.0.1
DB_PORT=3306
DB_NAME=clientx
DB_USER=root
DB_PASS=root
DB_CHARSET=utf8
```
## Tester la connection

Pour vérifier que la connection entre CLIENTX et MySQL soit bien opérationnelle. Ouvrez une page de l'application :
Si la page vous renvoi le message d'erreur :
`Erreur de connexion à la base de données` la connexion n'a pas eu lieu. Pour plus de détails, modifiez dans le ```.env``` l'environnement de l'application (APP_ENV) à "dev".
Attention, les identifiants peuvent apparaitre sur la page. Mais ça peut vous aidez à résoudre le problème.

## Migration

Pour gérer les migrations de la base de données (pour le développement ou la mise en production). ClientXCMS utilise [phinx.org](https://phinx.org/). Vous pouvez vous référer à leur documentation pour approfondir son fonctionnement.

### Commandes importantes 
- Migrate
    Cette commande permet de migrer les migrations manquantes.
    ```./vendor/bin/phinx migrate```

- Create
    Cette commande est importante en développement, elle permet de créer une migration.
    ```./vendor/bin/phinx create PremièreMigration```
- Seed
    Cette commande permet de remplir votre base avec des données prêt définit ou générer dynamiquement via la librairie [faker](https://github.com/fzaninotto/Faker)
    ```./vendor/bin/phinx seed:run```
    ou
    ```./vendor/bin/phinx seed:create PremierSeeding```