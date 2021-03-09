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

### REST

**REST** (Reprensentationnal State Transfer) est une architecure d'API. C'est une convension qui permet 

## 4 alternatives : SOAP, graphQL, gRPC et les microservices

4 alternatives sont sorties du lot dès le début de mes recherches : **SOAP**, **graphQL**, **gRPC** et les **microservices**. Je vais décrire les **3 premières** alternatives car un **microservice** est le nom donné à un service ad hoc fourni par un serveur et qui ne répond à aucune des autres solutions.

**ATTENTION** : ces alternatives ne sont pas des équivalents de l'architecture REST. Certaines sont des protocole, d'autres sont des framework ou encore des infrastructures. On parle ici d'alternatives dans un sens large mais elles ne sont pas strictement équivalentes.

### Decription du fonctionnement

#### SOAP

#### graphQL

#### gRPC

### Bilan : Forces, faiblesses et cas d'usages

| **Type d'API** | **Forces** | **Faiblesses** | **Cas d'Usage** |
| :-: |:-: |:-: | :-: |
| **SOAP** | _Connu, agnostique au language et au protocole_ | _Messages volumineux et complexes à formuler_ |  |
| **graphQL** |  |  |  |
| **gRPC** |  |  |  |
| **REST** | _Facile à mettre en oeuvre, connu_ | _lent_ | _Contrainte de temps, pas de grosse contrainte de performance, utilisation de l'API par des développeurs non expérimentés_ |
