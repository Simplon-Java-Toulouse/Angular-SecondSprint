Angular/2ème Sprint 
===

<h2>Lundi</h2>

**Retour Alternance**

**Nouvelles consignes**

**MasterClass Synthèse Angular**

**Point sur le 1er Sprint**

**Constitution des groupes pour le 2ème Sprint**

**Mise en oeuvre collective d'un process de résolution de blocage**

**before starting !**

En prévision de l'évaluation d'octobre et de manière générale, afin de vous habituer à travailler dans des conditions réelles, vous aurez des spécifications fonctionnelles et techniques ici.

A vous de faire le job en équipe (scrum, wireframe, modélisation, dev, test, git...)

**SPECIFICATION GENERALE**

Dans le prolongement du premier sprint, vous devez dans ce second sprint, réaliser une application de vente en ligne complète qui s'appuie sur vos acquis précédent mais il faudra, cette fois-ci, refaire en groupe un projet complet, back + front en répondant aux spécifications fonctionnelles ci-dessous.

L'appli propose d'afficher tous les produits classés par catégories accessibles via notre api, d'en selectionner un ou plusieurs pour constituer un caddy avec la possibilitée de passer commande à tout moment à condition d'être aunthentifié, enfin de "régler en ligne".

Vous devez distinguer 3 rôles dans votre appli : 
- utilisateur non connecté ou individu lambda qui peut naviguer sur votre site et consulter les infos des produits proposés par catégorie
- utilisateur connecté donc authentifié qui peut réaliser un panier constitué d'un ou plusieurs produits puis passer commande
- administrateur qui peut changer les photos des produits, modifier les infos.

**SPECIFICATIONS TECHNIQUES / CONCEPTION** 

- Spring au niveau du back (java 8, api Rest)
- Vous pourrez dans un premier temps utiliser une bdd virtuelle mais il faudra in fine utiliser un sgbd type mysql ou mariadb une fois arrivé à la phase commande.
- Comme à notre habitude, ne réinvontons pas la roue aussi utiliser Spring data pour gérer vos entités Jpa une fois crées puis spring data rest pour la gestion des web services associés
- De même, laisser de côté spring security que vous devrez naturellement gérer en fin de dev
- Angular 8 pour le front (bootstrap3, jquery) 
- Intégration continue avec Git d'un workflow par équipe, 2 repos (back & front)
- Gestion des photos : elles ne seront pas stocké en base pour ne pas alourdir celle-ci, chaque produit aura un attribut qui pointe sur le fichier correspondant (chemin)
- Pour des raisons de sécurité, ne pas stocker les photos dans le rep static, l'accès sera définitivement verrouillé une fois spring security activé !
- la gestion de l'authentification se fera côté front avec des données fictives locales (tableau avec noms des utilisateurs et leurs rôles : USER et(ou) ADMIN) "3ème Sprint : il faudra le gérer côté back"
- L'utilisateur ou token (user + roles) sera stocké en local storage afin de permettre la navigation sans déconnexion
- "3ème sprint : Mise en oeuvre d'https au niveau du back (changer application.properties, keytool...)
- "3ème sprint : JWT pour la phase d'authentification / utiliser keyclock"

<h2>Mardi</h2>

**veille**

**SPECIFICATIONS FONCTIONELLES -> POUR LES VISITEURS DU SITE, l'appli doit :**

- afficher la liste des produits selectionnable (ou accessible) au niveau du back (page d'accueil ou home)
		-> afficher les photos de chaque produit, prévoir une photo de substitution
- afficher la liste des produits correspondant à une catégorie par le simple clic sur celle ci	
- afficher le pointer vers la catégorie ou produit survolée avec la souris (pour clic)
- afficher la liste des produits d'une catégorie cliqué
- les catégories non selectionnés doivent apparaitre en grisées
- afficher sous chaque produit des icones signifiant s'ils sont selectionnés, en promotion ou disponible
- lorsqu'on clic sur une photo, afficher les informations détaillées sur le produit correspondant 
		-> (nom, description, prix, promotion o/n, selection o/n, dispo o/n)

<h2>Mercredi</h2>

**veille**

**SPECIFICATIONS FONCTIONELLES -> POUR LES ADMINISTRATEURS DU SITE, l'appli permet :**

- considérant ici, qu'ils ont déjà un compte, il faut proposer un formulaire d'authentification (côté front uniquement)
- une fois authentifié, il doit le rester tant qu'il ne se déconnecte pas (stockage dans le local storage)
- de changer la photo d'un produit par l'accès à l'explorateur de fichiers côté front :
		-> cela provoquera l'envoi de la photo au niveau du back ou elle sera stocké
		-> la nouvelle photo devra instantanément être affiché sur le front
- l'admin peut acceder naturellement aux infos d'un produit mais en plus, il peut les modifier, ce qui met à jour le back...
- les photos des produits seront stockés dans un dossier respectant ce chemin : "user.home" + /ecom/products
- les photos des catégories seront dans : "user.home" + /ecom/categories
- vous ne devez pas accepter les photos de plus de 2.5MB (back)

<h2>Jeudi</h2>

**veille**

**SPECIFICATIONS FONCTIONELLES -> POUR LES UTILISATEURS donc authentifiés, l'appli doit :**

- considérant ici, qu'ils ont déjà un compte, il faut proposer un formulaire d'authentification (côté front uniquement)
	"la création d'un compte utilisateur inexistant pourra faire l'objet d'un 3ème sprint (à gérer en base côté back]"
- une fois authentifié, il doit le rester tant qu'il ne se déconnecte pas (stockage dans le local storage)
- permettre de créer un panier/caddy dans le local storage, composé d'un ou plusieurs produits
- afficher le contenu d'un caddy (id,liste des produits, quantité, prix(qté*prix produit), total caddy)
- prévoir un bouton pour supprimer un ou plusieurs éléments de notre caddy
- revenir à tout moment sur la liste des produits pour ajouter dans le caddy en cours
		-> si l'ajout concerne un produit déjà présent dans le caddy, il faut juste augmenter la quantité de celui-ci
- passer une commande d'un caddy pour l'utilisateur ou une tierce personne :
		-> prévoir de remplir tous les champs de la fiche client : nom adresse tel email => NEXT
		-> afficher une fiche récapitulative de la commande avec toutes les infos : Client + N° cde + date cde + total
		-> une fois la commande validé, il faut la céer au niveau du back avec id, numéro de commande, date puis l'indiquer côté front instantanément
		-> passer à la phase paiement bien qu'elle soit fictive ici (pour l'ex, nous n'utiliserons pas de vraies plate forme de paiement en ligne)

<h2>Vendredi</h2>

**Demo du projet de chaque groupe**

**Préparation du Titre :**

- Referentiel de certification 
- http://www.dossierprofessionnel.fr/

<h2>Ressources</h2>

[YouTube](https://youtu.be/xpMGCZw0UBA)

**DERNIERES CONSIGNES :**

- Ne réinventez pas la roue, si le framework propose déjà des méthodes, utiliser les au lieu de refaire les choses
- Vous travaillez en groupe de 3/4 dev et compte tenu des différentes fonctionnalités à développer en très peu de temps, la répartition des taches est incontournable aussi vous devez repérer les composants ou services à développer, en faire des users stories et les répartir entre vous sur un tableau de bord visible.
- DOCUMENTER VOTRE CODE
- L'utilisation de Git impose de communiquer dans un groupe
- Astuce ici : la partie back peut être développé par une seule personne, une fois lancé, les micro services seront accessibles 		uniquement sur son pc tel un serveur dédié au groupe, attention ici il faut gérer le cas ou le pc plante !!!

**PHASE DE TEST ET VALIDATION** (en prévision de la mise en prod)

- prévoir des tests unitaires pour chaque composant
- finaliser les tests d'intégration
- il s'agit dans cette phase de vérifier si l'ensemble des fonctionnalités sont bien présente dans les spéc
- il faudra vérifier les autres chemins de nav et y apporter des solutions

**LE SAVIEZ VOUS ?**

---> NOTRE APPLI UTILISE LA SPECIFICATION JPA POUR LE MAPPING OBJET RELATIONNEL, SPRING UTILISE PAR DEFAUT HYBERNATE QUI EST UNE IMPLEMENTATION DE CELLE-CI MAIS EN REALITE ON PEUT EN UTILISER D'AUTRE DANS LA CONFIGURATION DE NOTRE APPLI...

---> NOTRE APPLI UTILISE LA SPECIFICATION JAXRS POUR LES SERVICES WEB DE TYPE RESTFUL, JERSEY EST UNE IMPLEMENTATION DE CELLE-CI...

---> NB CONCERNANT LE DEPLOIEMENT : Si votre hébergeur a déjà un serveur d'appli tel "Tomcat", vous devez générer un war, s'il n'en dispose pas (ex : serveur dédié), le jar est indispensable, dans ce cas, en démarrant l'appli, celle-ci démarre tomcat...

---> S'AGISSANT DE LA SECURITE, il y a 2 modes :
	- Sécurité basée sur les sessions et le cookies (stateful) / une session est stockée côté serveur qui envoi un cookie côté client
	- s'agissant des applis basées sur des api rest, on utilise JWT (stateless), on envoi username + pwd, on reçoit un token sécurisé


**WHAT ABOUT THE FUTURE ?**

NOUS VERRONS PROCHAINEMENT LES NOTIONS DE DEPLOIEMENT, SECURITE, PERFORMANCE et ROBUSTESSE d'une appli web mais avant tout, une pause appli mobile après l'éval d'octobre !
