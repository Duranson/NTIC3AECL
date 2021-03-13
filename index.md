# API : Les alternatives à l'architecture REST

Ce site web a pour objectif de rendre compte du travail de veille que j'ai réalisé sur 3 mois dans le cadre d'un projet de dernière année à l'École Centrale de Lyon. Il présente les résultats de cette étude. 

Un [document](https://github.com/Duranson/NTIC3AECL) complémentaire présente les outils de veille utilisés, les justifications de ces choix ainsi que les difficultés que j'ai pu rencontrer avec chacun de ces outils.

## Motivations

J'ai choisi ce sujet de veille car je ne connaissais pas assez le domaine et ressentait le besoin de mieux l'étudier et le comprendre. J'ai travaillé avec de nombreuses APIs lors de stages ou de projets personnels mais toutes étaient des API dites "REST". Je connaissais quelques principes qui faisaient d'une API une API "REST" mais **je ne les comprenais pas vraiment car je n'avais jamais vu de contre-exemple**. 

Le vrai déclic pour moi a été lors d'un projet à Centrale. Nous devions créer une API pour un site web utilisant un back-end un petit peu poussé et nous sommes tout de suite parti sur une architecture REST. Je me suis en fait rendu compte que **je ne connaissais aucune autre architecture que REST**, et que je n'étais dans ce contexte pas convaincu de l'utilité d'orienter notre API par rapport aux ressources, mais que je n'avais pas d'autre solution que de partir là dessus par manque de temps pour me renseigner. J'ai alors ressenti une **frustration à faire un choix architectural par habitude plutôt que par pertinence**.

Au cours de cette étude, je voulais prendre du recul sur le concept d'API REST qui est très à la mode et souvent mal utilisé. Je voulais expliciter ses **forces**, ses **faiblesses** et quelles **autres options** un ingénieur développeur a lorsqu'il veut créer une API afin que ce choix soit le plus **éclairé** et **transparent** possible.

## Définitions et point de départ de l'étude

### API

Une **API** (_Application Programming Interface_ ou _Interface de Programmation Applicative_ en français) est une interface entre des usagers et un fournisseur de service. Dans le contexte d'une infrastructure **client-serveur** (qui nous intéresse ici), c'est une norme de communication qui permet à des **client** de communiquer avec un **serveur** qui renverra en retour une réposne intelligible.

L'objectif principal d'une API est de limiter et de clarifier quels sont les actions possibles d'un utilisateur vers un serveur et quelles sont les réponses que l'utilisateur peut espérer.

Une API a pour vocation de lier de multiples usagers provenant d'horizons divers en créant une méthode de communication peut dépendante du contexte d'utilisation et de la manière d'initier la communication.

Un exemple d'API est celle du site https://genius.com. Genius fourni à la fois des paroles de musiques et des explications détaillées de ces paroles par des utilisateurs et/ou les créateurs. Genius fourni une [API](https://docs.genius.com/#/getting-started-h1) qui permet d'accéder à partir d'une application tierce aux données que contiennent leurs serveurs. Une fois un compte développeur créé chez Genius, on peut trouver toutes les informations nécessaire sur leur documentation. Par exemple, si l'on souhaite récupérer toutes les musiques d'un artiste, on s'intéressera à ce [bout de documentation](https://docs.genius.com/#artists-h2) :

<img width="800" alt="genius_screenshot" src="https://user-images.githubusercontent.com/44806936/111026659-b3154180-83eb-11eb-9475-ece6142a1381.png">


On voit ici qu'il suffit de faire une requête HTTP de type GET avec l'id Genius de la musique pour obtenir en retour un objet JSON contenant toutes les musiques de l'artiste et dont on connait le format exact.

### REST

**REST** (Reprensentationnal State Transfer) est une architecure d'API. C'est une convension qui n'a pas de réalité matérielle, on dit qu'une architecture est REST ou RESTful lorsqu'elle répond à ces critères :

Les architectures REST sont omniprésentes car très facilement compréhensibles et documentables. Un exemple est l'API de Spotify permettant de développer des application tierces utilisant des fonctionnalités de Spotify. Voici [un exemple de requête à l'API de Spotify](https://developer.spotify.com/documentation/web-api/reference/#category-artists), c'est un exemple-type de requête à une API REST :

<img width="800" alt="Capture d’écran 2021-03-09 à 22 07 45" src="https://user-images.githubusercontent.com/44806936/110538110-e4f48280-8123-11eb-9194-a3ca8fe5d15f.png">

On voit ici que la requête HTTP est construite sur un schéma logique suivant les ressources disponibles :
* La base est l'url de l'api (https://api.spotify.com/v1)
* On s'interesse aux données d'artistes : /artists
* Lequel ? : /{id}
* Quelle sous-ressource veut-on ? : /albums

La réponse se suffit à elle même et contient toutes les informations de la ressource ciblée : l'artiste et tous ses albums.

## 4 alternatives : SOAP, graphQL, gRPC et les microservices

4 alternatives sont sorties du lot dès le début de mes recherches : **SOAP**, **graphQL**, **gRPC** et les **microservices**. Je vais décrire les **3 premières** alternatives car un **microservice** est le nom donné à un service ad hoc fourni par un serveur et qui ne répond à aucune des autres solutions.

**ATTENTION** : ces alternatives ne sont pas des équivalents de l'architecture REST. Certaines sont des **protocole**, d'autres sont des **framework** ou encore des **infrastructures**. On parle ici d'alternatives dans un **sens large** mais elles ne sont pas strictement équivalentes.

### SOAP

SOAP est un protocole de communication basé sur le language XML. C'est le plus ancien protocole de communication entre machines distantes qui reste d'usage aujourd'hui. Le protocole SOAP est construit pour que **toutes les information à transmettre se trouvent dans le corps XML**.

Les API basées sur le protocole SOAP ont la particularité d'être transparentes au protocole de communication. On peut ainsi construire une API qui utilise le protocole SMTP ou FTP contrairement à tous les autres protocoles qui utilsent TCP.

L'autre conséquence de ce choix est que le protocole SOAP est agnostique au langage. Il est très simple de créer des modules SOAP dans n'importe quel langage car le seul point technique est la création du XML, la communication étant extrêmement basique.

### graphQL

### gRPC

## Bilan : Forces, faiblesses et cas d'usages

| **Type d'API** | **Forces** | **Faiblesses** | **Cas d'Usage** |
| :-: |:-: |:-: | :-: |
| **SOAP** | _Connu, agnostique au language et au protocole_ | _Messages volumineux et complexes à formuler_ |  |
| **graphQL** | _Très flexible, de plus en plus utilisé/documenté_ | _Infrstructure très complexe et couteuse à mettre en place_ |  |
| **gRPC** | _Très rapide, bidirectionnel_ | _Peu flexible sur le modèle de données, Protocol Buffer à définir_ |  |
| **REST** | _Facile à mettre en oeuvre, connu_ | _Lent, peu flexible_ | _Contrainte de temps, pas de grosse contrainte de performance, utilisation de l'API par des développeurs non expérimentés_ |
