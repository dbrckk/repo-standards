# Wiki pédagogique — utiliser les 88 règles

Les [88 règles officielles](../standards/88-rules.md) ne sont pas toutes à exécuter à chaque changement. Les fondamentales **[F]** forment le socle ; les conditionnelles **[C]** sont choisies selon le projet. Le [skill](../skills/repo-excellence-88/SKILL.md) donne une procédure de travail.

## Pourquoi ne pas appliquer toutes les règles systématiquement ?

Une correction mineure de texte ne justifie pas l'audit complet d'un système de paiement ni un benchmark IA. L'agent identifie d'abord les risques et ne sélectionne que les vérifications utiles. Ce filtrage accélère le travail sans faire baisser le niveau d'exigence.

## Exemple 1 — Corriger une connexion qui échoue

1. Vérifier la branche, l'état projet, la reproduction de l'erreur et les logs (4, 6, 21).
2. Inspecter sessions, API et permissions (10, 65).
3. Corriger à la source avec un diff limité (11, 27).
4. Vérifier un parcours de connexion réel, la déconnexion et le build (1, 9, 13).
5. Documenter la cause et les commandes utiles (2, 3, 6).

## Exemple 2 — Déployer un workflow IA multi-agents

1. Définir rôle et limites de chaque agent (25, 46).
2. Traiter fichiers, issues et pages externes comme non fiables (31, 49).
3. Tracer identifiant, étapes, erreurs et reprise (21, 63).
4. Comparer la qualité, la latence et le coût des modèles (24, 50).
5. Vérifier un workflow de bout en bout ; documenter clairement les parties non exécutées (9, 13, 82).

## Exemple 3 — Application d'économies alimentaires

1. Dater les offres, prix et remboursements, puis revalider leur disponibilité (67).
2. Vérifier les licences, conditions commerciales et obligations locales (33, 62).
3. Concevoir un parcours mobile compréhensible (12, 39).
4. Calculer les économies sans double comptage (22, 38).
5. Gérer les pannes d'une source d'offres et la connexion instable (21, 40).

## Exemple 4 — Publier une fonctionnalité

1. Vérifier les critères de livraison et les impacts existants (13, 32).
2. Exécuter les contrôles fonctionnels, lint et build applicables sans créer de tests unitaires (1, 45).
3. Vérifier le déploiement, les migrations et le retour arrière si nécessaire (11, 23, 36).
4. Actualiser les notes de projet et consigner ce qui reste non vérifié (6, 82).

## FAQ

**Quand peut-on dire « terminé » ?** Lorsque le parcours essentiel fonctionne réellement dans les conditions vérifiables, que les critères de fin sont remplis, et que les limites restantes sont indiquées.

**Les tests existants sont-ils supprimés ?** Non. La règle n° 1 interdit de *créer* de nouveaux tests unitaires ; elle ne demande pas de supprimer les tests existants. La validation d'intégration reste possible.

**Comment reprendre avec « continue » ?** Consulter le dernier commit et l'état du projet, comparer ce qui est écrit avec le code réel, puis reprendre le premier blocage ou objectif inachevé.

**Comment transmettre ces règles aux autres dépôts ?** Faire pointer leur `AGENTS.md` vers la version du standard réellement adoptée. Une ancienne référence épinglée ne se met pas automatiquement à jour lorsque `main` évolue.
