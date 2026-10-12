---
name: app-reference-rea
description: Étudier les applications existantes avant de créer ou refondre une app Android, avec REA, catalogue d'APK vérifiés et spécifications originales.
---

# Références d'applications — REA

Workflow opérationnel **par défaut** pour les nouvelles applications Android et les refontes majeures. Il complète, sans le modifier, le catalogue immuable des [88 règles](../../standards/88-rules.md). Ne pas le déclencher pour une simple correction sans impact produit.

## 1. Découvrir les alternatives avant de coder

- Décrire utilisateur cible, tâches, fonctionnalités, plateforme, contraintes et distinction recherchée.
- Identifier de préférence **3 à 5 produits comparables** : nom, éditeur, URL officielle, fiche Google Play/FDroid/GitHub du véritable éditeur, version/date observable, prix, UX, fonctionnalités, points faibles et preuves.
- Comparer les parcours observables (onboarding, états vides/erreurs, navigation, hors-ligne, performances, accessibilité, vie privée). Les avis et les captures ne sont pas des preuves de fonctionnement interne.
- Pour une fonctionnalité complexe, choisir au moins une référence à étudier en profondeur, en justifiant ce choix. Ne pas bloquer le projet si aucune APK légitime n'est disponible : noter la limite et poursuivre avec sources officielles/open source.

## 2. Acquisition traçable et licite

Catalogue et point de dépôt existants : [dbrckk/zombie-apk](https://github.com/dbrckk/zombie-apk). Utiliser ses `scripts/reference_intake.py`, `references/catalog.json` et ses rapports `analysis/`; ne pas créer un stockage d'APK parallèle.

1. Chercher **d'abord** un APK téléchargeable directement sur le domaine de l'éditeur, sa release GitHub vérifiée ou un canal explicitement autorisé (ex. F-Droid pour une appli libre). La page Google Play seule ne fournit généralement pas de fichier APK direct.
2. Télécharger uniquement depuis un canal que l'on peut attribuer à l'éditeur et utiliser légitimement ; sinon renseigner `unavailable`, `store_only` ou `third_party_unverified`. Ne pas qualifier un miroir tiers d'officiel.
3. Avant analyse, conserver URL exacte, date, nom de package, version, taille, SHA-256 des octets, certificat de signature vérifié indépendamment (`apksigner`) et droits/licence lorsque disponibles. Lier à la fiche du catalogue. **Une empreinte seule ne prouve pas l'authenticité.**
4. Mettre les fichiers localement dans le dossier ignoré `reference-apks/` de `zombie-apk`, ou sur un stockage privé autorisé. Une pièce jointe de release publique est admissible uniquement avec licence/autorisation explicite de redistribution. Ne jamais pousser par défaut d'APK propriétaire, de dump, de code décompilé ou de secrets.
5. Si l'éditeur fournit seulement une installation via le store, respecter ce mode de distribution et les conditions du service. Un export depuis son propre appareil, lorsqu'il est autorisé, doit être identifié comme export local, **pas comme APK officiel téléchargé**.

## 3. Inspection technique avec REA

REA : [morluto/rea](https://github.com/morluto/rea), guide [Android](https://github.com/morluto/rea/blob/main/docs/android-analysis.md). Prérequis à vérifier : REA installé, **JDK complet 17+** et moteur headless JADX compatible ; REA n'installe pas le JDK/JADX à notre place. Épingler les versions exécutées et contrôler les prérequis avant d'affirmer une analyse réussie.

```sh
rea doctor --json
rea inspect-android-package /chemin/prive/verified.apk --json > /chemin/prive/rea-package.json
rea search-android-classes /chemin/prive/verified.apk MainActivity --json > /chemin/prive/rea-classes.json
```

L'examen peut porter sur manifeste, permissions, navigation/activités, architecture, moteurs/librairies, stockage local, formats et performances. Signaler l'obfuscation et les conclusions hypothétiques ; relier chaque observation à une preuve et à la version/hash **exacts**. Éviter de lancer l'application ou d'accéder à des comptes/données personnelles sans autorisation explicite.

## 4. Reconcevoir sans copier

Créer une fiche par produit selon [le modèle](../../templates/app-reference-intake.md) et une matrice `fonction de référence → mécanisme observé → enseignement → implémentation originale → amélioration proposée → critère de validation`. Prioriser les gains réels : tâches simplifiées, robustesse, accessibilité, consommation batterie/données, personnalisation, sécurité et design propre. **Pas de copier-coller de code propriétaire, d'assets, de marques, de clés, de logique de protection ou d'API privées.** Réutiliser directement du code uniquement si sa licence et l'attribution le permettent.

## 5. Vérification et sortie

- Exécuter les parcours fonctionnels existants, builds/QA autorisés. Ne pas créer de nouveaux tests unitaires par défaut.
- Consigner dans `.ai/project-state.md` le périmètre comparatif, les hashes/versions, les outils réellement exécutés, ce qui est confirmé vs non vérifié, et la décision produit.
- Livrer : matrice concurrentielle, fiche(s) sourcées, **état d'acquisition explicite** (succès ou blocage), rapport REA résumé sans contenu propriétaire et plan de réalisation original. Ne jamais inventer APK, résultat d'analyse ou contrôle qualité.

**Sécurité et conformité :** analyse statique autorisée uniquement, pas de contournement de DRM, anti-triche, authentification, verrouillage ou protections. Les conditions applicables et droits de copie/redistribution sont vérifiés au cas par cas. Respecter minimisation des données et licences.
