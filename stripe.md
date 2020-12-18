### Stripe

## Introduction

Stripe vous permet d'accepter les paiements par carte bancaire directement sur ClientX CMS [Site de Stripe](https://stripe.com).

## Mise en Place de Stripe

La mise en place de Stripe est très simple : il vous suffit de vous rendre sur votre [Dashboard Stripe](https://dashboard.stripe.com/dashboard) puis de créér des identifiants API.

![image](https://raw.githubusercontent.com/ClientXCMS/docs/master/images/stripe/dashboard.png "Dashboard - Clef API")

Un Webhook Stripe est aussi nécéssaire à la mise en place de Stripe sur ClientX, pour cela rendez-vous dans la [gestion des webhook](https://dashboard.stripe.com/webhooks) puis crééz en un nommé ClientX (par exemple).

Dans URL d'endpoint il suffit de mettre : ```votredomaine/api/stripe``` (https://demo.clientx.fr/api/stripe).

La description est facultative.

Il faudrat aussi ajouter ces 3 options dans évènements à envoyer : ```checkout.session.completed``` ```checkout.session.async_payment_succeeded``` ```checkout.session.async_payment_failed```.

![image](https://raw.githubusercontent.com/ClientXCMS/docs/master/images/stripe/webhook.png "Dashboard - Webhook")

## Intégration à ClientX

Une fois que Stripe est configuré, il suffit de l'intégrer à ClientX est c'est la partie la plus simple ! 

Il vous suffit de télécharger le module Stripe sur [Le Marketplace](https://clientx.fr/market) (*préalablement acheté*).

Vous avez juste à glisser les fichiers téléchargés dans la racine de votre hébergement WEB (liste des hébergeurs officiellement compatibles [ici](https://clientx.fr/docs/installation)).

Il faudrat ajouter la ligne ```->addModule(App\Stripe\StripeModule::class)``` dans index.php.

![image](https://raw.githubusercontent.com/ClientXCMS/docs/master/images/stripe/index.png "Index")

Actualisez la page de votre panel admin ClientX et l'option Stripe apparaîtra dans les options Administrateurs, il vous suffira juste de remplir les champs avec : la Clée Stripe, le Secret du Client Stripe et le Secret de l'ENDPOINT Stripe.

## Conclusion

Et voilà, Facile, n'est-ce pas ? Vous êtes prêt à utiliser **Stripe** avec **ClientX** ! 
