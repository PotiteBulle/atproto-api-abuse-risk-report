# PoC documentaire professionnel  
## Risque d’énumération et d’agrégation massive de données publiques sur un PDS ATProto

**Type :** Proof of Concept documentaire  
**Cadre :** Red Team défensif  
**Sujet :** Risque d’énumération DID / handle et d’agrégation de données publiques  
**Objectif :** Sensibilisation, analyse de risque et signalement responsable  
**Statut :** Public, sans données réelles et sans code opérationnel  

---

## 1. Résumé

Ce dépôt présente un **PoC documentaire professionnel** consacré à un risque d’énumération et d’agrégation massive de données publiques dans un environnement ATProto.

Le risque étudié ne correspond pas à un piratage de compte, à un vol de mot de passe, à une intrusion serveur ou à une compromission de l’infrastructure.

Le problème principal est différent.

Il concerne la possibilité, pour une entité externe ou malveillante, de transformer des informations publiques dispersées en une base structurée, lisible, analysable et réutilisable à grande échelle.

Une information publique isolée peut sembler peu sensible.  
En revanche, lorsqu’un grand volume d’informations publiques est collecté, enrichi, trié et conservé dans un format exploitable, l’ensemble peut devenir sensible.

Ce PoC documente ce risque dans une logique de **Red Team défensif**.

---

## 2. Objectif du PoC

L’objectif de ce PoC est d’expliquer comment un acteur hostile pourrait raisonner face à des données publiques accessibles sur un PDS ATProto.

La question posée est la suivante :

> Que pourrait obtenir une entité externe si elle utilisait uniquement des informations publiques pour cartographier massivement des comptes associés à un PDS ?

Ce document vise à :

- expliquer le risque de manière claire
- vulgariser l’impact pour un public non technique
- documenter la chaîne de risque
- montrer pourquoi l’agrégation change la sensibilité des données
- présenter un scénario Red Team défensif
- proposer des pistes de mitigation
- préparer un signalement responsable aux équipes concernées

Ce PoC ne vise pas à fournir un outil d’exploitation.

---

## 3. Cadre Red Team défensif

Dans ce PoC, l’analyse se place volontairement dans la posture d’une entité malveillante ou d’une entité externe.

Cette posture ne sert pas à attaquer.  
Elle sert à comprendre comment un acteur hostile pourrait détourner des fonctionnalités publiques pour produire du renseignement exploitable.

L’approche Red Team défensive permet d’identifier les risques avant qu’ils ne soient utilisés dans un cadre abusif.

Le cadre de ce document est donc :

- défensif
- pédagogique
- documentaire
- non intrusif
- non opérationnel
- orienté réduction du risque
- orienté signalement responsable

---

## 4. Périmètre

Ce PoC concerne le risque d’agrégation massive de données publiques associées à un PDS ATProto.

Le scénario étudié porte sur la possibilité de produire une base structurée à partir d’informations accessibles publiquement.

Ce document ne contient pas :

- de script complet de collecte
- de cible réelle exploitable
- de données réelles
- de DID réels
- de handles réels
- de résultats de scan
- de fichiers JSON exploitables
- de procédure d’automatisation complète
- de méthode de contournement
- de mécanisme offensif

Le PoC démontre un **risque conceptuel et documentaire**, pas une exploitation technique publiée.

---

## 5. Ce que le PoC démontre

Ce PoC démontre qu’un risque peut exister même sans compromission directe.

Le danger ne vient pas forcément d’une faille classique.  
Il vient de la combinaison entre données publiques, automatisation, volume et structuration.

La chaîne de risque peut être résumée ainsi :

```txt
Données publiques
  ↓
Collecte automatisée
  ↓
Enrichissement
  ↓
Agrégation
  ↓
Export structuré
  ↓
Analyse et croisement
  ↓
Risque de cartographie, surveillance ou ciblage
```

Le point central est que des données publiques, lorsqu’elles sont regroupées en masse, peuvent changer de nature.

---

## 6. Ce que le PoC ne démontre pas

Ce PoC ne démontre pas :

- une prise de contrôle de compte
- une vulnérabilité d’authentification
- une fuite de mot de passe
- une élévation de privilèges
- une exécution de code à distance
- une compromission d’un serveur
- une intrusion dans l’infrastructure
- une exploitation offensive active
- une technique de harcèlement
- une méthode de ciblage opérationnelle

Il s’agit d’un risque d’**abus de données publiques par agrégation**, pas d’une vulnérabilité d’intrusion classique.

---

## 7. Explication simple

La faille, ce n’est pas que le code pirate un compte.

La faille, c’est qu’un processus automatisé peut aspirer une grande quantité de comptes publics, relier des identifiants techniques à des pseudos lisibles, puis créer une base organisée.

Entre de mauvaises mains, cette base peut servir à surveiller, classer ou cibler des personnes à grande échelle.

Autrement dit :

```txt
Une donnée publique isolée peut être peu sensible.
Une base massive de données publiques peut devenir sensible.
```

---

## 8. Analogie

Le risque peut être comparé à un annuaire public.

Consulter une fiche dans un annuaire n’est pas forcément problématique.  
Copier tout l’annuaire, ajouter des colonnes de tri, enrichir les fiches et conserver une base complète devient beaucoup plus sensible.

L’information était déjà publique.  
Mais la mise en base change son potentiel d’usage.

Le danger vient de trois facteurs :

- l’automatisation
- le volume
- la réutilisation

---

## 9. Chaîne de risque

La chaîne de risque observée peut être représentée de manière simplifiée :

```txt
PDS public
  ↓
Identifiants publics
  ↓
Association avec des pseudos lisibles
  ↓
Création d’un export local
  ↓
Tri et analyse
  ↓
Croisement avec d’autres sources publiques
  ↓
Cartographie ou ciblage potentiel
```

Cette chaîne est volontairement décrite sans détails opérationnels.

L’objectif est de comprendre le risque, pas de fournir une procédure de reproduction abusive.

---

## 10. Exemple volontairement non opérationnel

L’exemple ci-dessous est volontairement simplifié et non exploitable tel quel.

```ts
const source = "https://example.invalid";

const publicEntries = await collectPublicMetadata(source);

const documentedEntries = await enrichPublicMetadata(publicEntries);

await writeLocalRiskReport("sample-report.json", documentedEntries);
```

Cet exemple illustre uniquement la logique générale :

```txt
Collecter
  ↓
Enrichir
  ↓
Structurer
  ↓
Documenter
```

Aucune cible réelle, aucun endpoint réel et aucune logique complète ne sont fournis.

---

## 11. Pourquoi l’agrégation augmente le risque

L’agrégation modifie la sensibilité des données.

### Volume

Une information consultée ponctuellement reste limitée.  
Une collecte massive permet d’obtenir une vue d’ensemble.

### Lisibilité

Un identifiant technique peut devenir plus exploitable lorsqu’il est associé à un pseudo public ou à un statut compréhensible.

### Persistance

Une donnée visible à un instant donné peut changer ou disparaître.  
Un export local peut être conservé longtemps.

### Croisement

Une base structurée peut être croisée avec d’autres sources publiques.

### Partage

Un fichier structuré peut être copié, compressé, transmis, importé ou analysé facilement.

---

## 12. Données potentiellement sensibles une fois agrégées

Selon les informations accessibles, une base de ce type pourrait contenir :

- identifiants techniques publics
- pseudos ou handles publics
- source PDS associée
- statut apparent du compte
- date d’observation
- date de résolution
- indicateurs d’activité ou d’inactivité
- informations facilitant le suivi dans le temps

Ces éléments ne sont pas forcément sensibles séparément.  
Ils peuvent le devenir lorsqu’ils sont regroupés, historisés et analysés.

---

## 13. Impact potentiel

Dans un usage hostile, une telle base pourrait permettre :

- la cartographie d’un PDS
- l’identification de comptes liés à une même infrastructure
- le suivi de l’évolution d’une communauté
- le repérage de comptes actifs ou inactifs
- le croisement avec d’autres sources ouvertes
- la constitution de listes de surveillance
- la constitution de listes de ciblage
- le profilage de comptes ou de groupes
- la facilitation de campagnes coordonnées
- la facilitation de harcèlement ciblé

L’impact réel dépend du volume collecté, de la fréquence des collectes, de la durée de conservation et des croisements réalisés.

---

## 14. Risques pour les utilisateurices

Le risque peut être particulièrement important pour les personnes déjà exposées à :

- du harcèlement
- de la surveillance
- de l’intimidation
- des campagnes coordonnées
- du doxxing
- de la répression
- des ciblages communautaires

Même si les données sont publiques, leur regroupement dans une base structurée peut faciliter des usages abusifs.

---

## 15. Risques pour la plateforme

Pour une plateforme ou un opérateur de PDS, le risque concerne :

- la collecte massive de données publiques
- la difficulté à distinguer usage légitime et usage abusif
- la création de bases externes non contrôlées
- la perte de confiance des utilisateurices
- l’absence visible de friction face à certains volumes
- le manque potentiel d’alertes sur les comportements d’inventaire
- la réutilisation des données hors plateforme

Le sujet n’est donc pas uniquement technique.  
Il concerne aussi la confiance, la sécurité et la perception des utilisateurices.

---

## 16. Observation issue du test

Dans le cadre de cette recherche, un test limité a permis d’observer qu’un volume important pouvait être traité sur une durée prolongée sans blocage clairement visible côté client.

Cette observation doit être interprétée avec prudence.

L’absence de blocage visible ne prouve pas l’absence totale de détection côté infrastructure.  
Elle indique cependant qu’un comportement de collecte important peut ne pas générer de friction immédiate perceptible par l’acteur qui réalise l’opération.

Ce point justifie une attention particulière sur les mécanismes de détection, de limitation et d’alerte.

---

## 17. Analyse du risque

| Élément | Évaluation |
|---|---|
| Type de risque | Agrégation massive de données publiques |
| Nature | Abus potentiel de fonctionnalité publique |
| Accès requis | Public ou non privilégié |
| Compromission directe | Non |
| Complexité | Faible à moyenne |
| Impact individuel | Variable |
| Impact collectif | Potentiellement élevé |
| Risque principal | Cartographie, surveillance, profilage, ciblage |
| Sensibilité du PoC | Faible, car non opérationnel et sans données réelles |

---

## 18. Facteurs aggravants

Le risque augmente lorsque :

- le volume collecté est élevé
- la collecte est répétée dans le temps
- les résultats sont conservés longtemps
- les exports sont partagés
- les données sont croisées avec d’autres sources
- les comptes inactifs ou retirés sont conservés
- aucune limitation claire n’est visible
- aucune alerte n’est déclenchée côté opérateur
- les fichiers générés sont directement exploitables

---

## 19. Facteurs limitants

Le risque est réduit lorsque :

- le périmètre est limité
- les données sont minimisées
- les exports sont anonymisés
- les fichiers sont supprimés après analyse
- les résultats ne sont pas publiés
- les endpoints sensibles sont surveillés
- des limites de débit existent
- des alertes sont générées
- les usages légitimes sont distingués des usages abusifs

---

## 20. Signaux d’abus possibles

Plusieurs signaux peuvent aider à identifier une collecte abusive :

- volume anormal de requêtes
- consultation répétée d’endpoints d’inventaire
- résolution massive d’identifiants
- comportement non interactif prolongé
- répétition régulière de collectes similaires
- absence de User-Agent explicite
- usage d’infrastructures anonymisées
- requêtes séquentielles ou exhaustives
- absence de respect des ralentissements
- activité répartie sur plusieurs sources

Ces signaux doivent être analysés dans leur contexte.  
Ils ne prouvent pas automatiquement une intention malveillante.

---

## 21. Mitigations proposées

### Limitation de débit progressive

Mettre en place des limites adaptées aux endpoints permettant l’énumération ou l’inventaire.

Ces limites peuvent prendre en compte :

- l’adresse IP
- la plage réseau
- le User-Agent
- le volume horaire
- le volume quotidien
- la fréquence de résolution
- la répétition des requêtes
- le niveau de confiance du client

### Détection de collecte massive

Mettre en place des règles comportementales capables d’identifier les collectes industrielles.

Exemples :

- volume inhabituel
- scans répétés
- parcours exhaustif
- absence de pause
- résolution massive
- répétition temporelle

### Quotas différenciés

Adapter les quotas selon le type de client.

Exemples :

- relais légitime
- service d’indexation connu
- outil de modération déclaré
- chercheur en sécurité
- client anonyme
- client inconnu

### Alertes côté opérateur

Alerter les opérateurs lorsqu’un comportement d’inventaire massif est détecté.

Exemples :

- alerte sur volume inhabituel
- rapport de requêtes sensibles
- détection de comportement répétitif
- suivi des sources les plus actives

### Minimisation des données

Réduire les métadonnées retournées aux clients anonymes ou non vérifiés lorsque cela est compatible avec le fonctionnement du protocole.

L’objectif n’est pas de casser la fédération.  
L’objectif est de réduire l’abus massif.

### Canal de signalement

Mettre à disposition un canal clair pour transmettre ce type de découverte de manière responsable.

Cela permet aux chercheurices de signaler les risques sans publier de détails sensibles.

---

## 22. Bonnes pratiques appliquées dans ce PoC

Afin de limiter les risques de réutilisation abusive, ce PoC applique plusieurs précautions :

- aucune donnée réelle publiée
- aucun DID réel publié
- aucun handle réel publié
- aucun export JSON réel publié
- aucun script complet publié
- aucun endpoint réel documenté comme cible
- aucune procédure complète fournie
- aucun réglage optimisé pour la collecte
- aucune méthode de contournement fournie

Le document se concentre uniquement sur l’analyse du risque.

---

## 23. Signalement responsable

Ce PoC peut servir de support à un signalement responsable auprès des équipes concernées.

Le signalement peut inclure :

- le résumé du risque
- le cadre défensif de la recherche
- l’impact potentiel
- les observations générales
- les limites du test
- les mesures prises pour ne pas exposer de données réelles
- les pistes de mitigation proposées

L’objectif est de permettre une évaluation du risque sans exposer davantage les utilisateurices.

---

## 24. Formulation synthétique

Le risque principal n’est pas la compromission directe de comptes.  
Le risque principal est l’industrialisation de la collecte et de l’agrégation de données publiques.

Une entité externe pourrait utiliser ces données pour produire une base structurée permettant de cartographier, surveiller, profiler ou cibler des comptes à grande échelle.

---

## 25. Conclusion

Ce PoC documentaire montre qu’un système ouvert peut présenter un risque lorsque des informations publiques peuvent être collectées, enrichies et structurées à grande échelle.

Il ne s’agit pas d’un piratage classique.  
Il s’agit d’un risque d’abus par agrégation.

Le danger principal réside dans la transformation d’informations publiques dispersées en une base organisée, analysable, partageable et réutilisable.

Dans un cadre défensif, ce type d’analyse doit rester limité, anonymisé, non opérationnel et signalé de manière responsable.

Dans un cadre hostile, le même principe pourrait faciliter la surveillance, le profilage, la cartographie ou le ciblage de personnes et de communautés.

---

## 26. Clause d’usage

Ce document est publié uniquement à des fins de sensibilisation, de recherche défensive et de signalement responsable.

Toute utilisation visant à collecter massivement des données, surveiller des personnes, profiler des communautés, cibler des utilisateurices, organiser du harcèlement ou contourner des protections est contraire à l’objectif de ce PoC.

---

## 27. Note finale

Ce PoC est volontairement documentaire.

Il cherche à montrer le risque sans fournir les moyens de l’exploiter.

L’objectif est de favoriser une meilleure compréhension du problème, d’encourager la mise en place de garde-fous et de permettre un échange responsable avec les équipes concernées.
