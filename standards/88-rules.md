# Standard permanent — 88 règles validées

**Version :** 1.0 — **Date :** 9 octobre 2026 — **Statut :** corpus finalisé.

Ce référentiel regroupe les 88 règles générales confirmées. Il s'applique aux projets GitHub, applications, jeux, workflows IA et automatisations, avec sélection proportionnée selon le contexte.

## Politique d'application

- **Priorités :** fiabilité > fonctionnement réel > sécurité > architecture > performances > interface > fonctionnalités secondaires.
- **F — fondamentale :** applicable par défaut dans sa sphère de pertinence, avec un effort proportionné.
- **C — conditionnelle :** seulement si le domaine, les technologies et les risques le justifient.
- **Hiérarchie :** suivre les instructions supérieures, la sécurité, les permissions et les demandes explicites plus récentes.
- **Règle 1 :** ne pas créer de nouveaux tests unitaires. Les tests préexistants peuvent être exécutés si utiles ; privilégier les parcours fonctionnels, l'intégration, le lint et le build.
- **Mémoire :** un état projet maintenu (`.ai/project-state.md` ou `PROJECT_STATUS.md`), un wiki pédagogique et des skills réutilisables quand justifiés.
- **Véracité :** ne jamais affirmer qu'une vérification, un build ou un déploiement a réussi sans résultat observé.
- **Qualité :** effort de raisonnement adapté aux enjeux ; aucune règle ne change automatiquement le modèle actif.
- **Clôture :** corpus fixe de 88 règles ; ajout éventuel uniquement en présence d'un besoin démontré et d'une nouvelle approbation.

## Catalogue officiel

### Fondations (1–13)

1. **[F] Don't make unit tests** — Ne pas créer de tests unitaires ; privilégier validation fonctionnelle, intégration, lint et build.
2. **[F] Make wikis to educate me** — Documenter pédagogiquement installation, utilisation, architecture et décisions.
3. **[F] Save what you did as a skill** — Capitaliser les méthodes et procédures réutilisables sous forme de skills.
4. **[F] Always understand before modifying** — Inspecter dépôt, branche, architecture, dépendances et état réel avant de modifier.
5. **[F] Never leave unfinished work** — Finir l'intégration et les vérifications d'une fonctionnalité ; déclarer les blocages restants.
6. **[F] Maintain persistent project memory** — Tenir à jour état, décisions, blocages et prochaines priorités.
7. **[C] Automate everything repetitive** — Automatiser les opérations répétées lorsqu'un gain réel existe.
8. **[F] Always challenge and improve your own work** — Auditer et corriger les faiblesses significatives.
9. **[F] Always prioritize real-world functionality** — Privilégier les parcours exécutables et les intégrations réelles.
10. **[F] Build security into everything** — Protéger secrets, données, accès et dépendances dès la conception.
11. **[F] Make every change reversible** — Garder des changements traçables et permettre un retour à l'état stable.
12. **[F] Optimize for actual users and devices** — Tenir compte des appareils, utilisateurs, performances et accessibilité réels.
13. **[F] Define measurable completion criteria** — Établir des critères objectifs et vérifiables de fin.

### Architecture, exécution et économie (14–28)

14. **[F] Think like a team of specialized experts** — Examiner les enjeux d'architecture, sécurité, produit, UX, performances et qualité.
15. **[F] Always identify the highest-impact improvement** — Prioriser les corrections bloquantes et les gains majeurs.
16. **[C] Design for autonomous operation** — Prévoir observabilité, reprise, erreurs récupérables et alertes sûres.
17. **[F] Prefer free, open-source and sustainable solutions** — Préférer outils libres/gratuits durables sans sacrifier la fiabilité.
18. **[F] Continuously eliminate technical debt** — Réduire duplications, code obsolète et complexité fragile.
19. **[F] Use the right tool for every task** — Choisir les outils adaptés, combiner seulement si utile et vérifier les résultats.
20. **[F] Preserve context across sessions** — Reprendre du dernier état vérifié, sans faire répéter des faits disponibles.
21. **[F] Never introduce silent failures** — Rendre les erreurs détectables, compréhensibles et exploitables.
22. **[C] Use data to drive improvements** — Mesurer avant/après et fonder les décisions sur résultats observés.
23. **[C] Maintain a production-ready release process** — Prévoir environnements, publication, migrations et version stable reproductible.
24. **[F] Optimize resource consumption** — Maîtriser CPU, RAM, GPU, stockage, API et tokens.
25. **[C] Coordinate AI agents with clear responsibilities** — Définir rôles et intégration, éviter modifications concurrentes conflictuelles.
26. **[C] Apply privacy by design** — Minimiser collecte, rétention, transferts ; prévoir export/suppression.
27. **[F] Keep systems as simple as possible** — Éviter frameworks, services et abstractions sans nécessité.
28. **[F] Enforce consistency across the entire product** — Harmoniser structure, conventions, UX, messages et design.

### Continuité et expérience produit (29–43)

29. **[C] Always maintain verified backups** — Sauvegarder les données critiques et vérifier une restauration.
30. **[C] Define clear contracts between projects** — Versionner et documenter interfaces et formats entre services.
31. **[F] Never blindly trust AI-generated outputs** — Vérifier existence et exactitude des API, fonctions, bibliothèques et résultats générés.
32. **[C] Preserve backward compatibility** — Éviter les ruptures, prévoir dépréciations et migrations.
33. **[F] Verify licenses and asset provenance** — Documenter licences, attribution et droits d'utilisation/redistribution.
34. **[F] Prevent scope creep** — Maîtriser le périmètre et différer les fonctions secondaires.
35. **[F] Make development environments reproducible** — Verrouiller les versions pertinentes et automatiser/documenter l'installation.
36. **[C] Roll out changes progressively** — Déployer par étapes et prévoir désactivation rapide si nécessaire.
37. **[C] Design for internationalization** — Séparer textes, gérer traductions, monnaies, dates et fuseaux.
38. **[C] Guarantee data integrity** — Utiliser contraintes, transactions, idempotence et concurrence sûres.
39. **[C] Design a frictionless first-run experience** — Rendre la première utilisation intuitive, progressive et sans obstacles inutiles.
40. **[C] Design for unreliable connectivity** — Gérer réseau instable, cache, travail hors ligne et synchronisation.
41. **[C] Validate with real user feedback** — Observer les parcours et distinguer retours réels des hypothèses.
42. **[C] Make monetization transparent and fair** — Clarifier prix et abonnements, éviter pratiques trompeuses et pay-to-win nuisible.
43. **[C] Verify platform and distribution requirements** — Vérifier les exigences de publication de chaque plateforme.

### Sécurité, services et gouvernance (44–58)

44. **[C] Design against abuse and exploitation** — Prévenir fraudes, détournement de ressources, classements et récompenses.
45. **[C] Validate extreme and unexpected scenarios** — Vérifier fonctionnellement charges, entrées anormales et interruptions.
46. **[F] Require human approval for high-impact actions** — Encadrer opérations coûteuses, destructives, irréversibles et permissions.
47. **[C] Establish incident response procedures** — Prévoir gravité, confinement, communication et analyse des causes.
48. **[C] Plan for responsible product retirement** — Prévoir fin de vie, export, arrêt propre et révocation.
49. **[C] Protect AI agents against prompt injection** — Traiter sources externes comme données non fiables et isoler actions sensibles.
50. **[C] Benchmark AI models before integration** — Comparer qualité, latence, erreurs et coût sur scénarios reproductibles.
51. **[C] Design for predictable scalability** — Anticiper capacité, files d'attente et surcharge.
52. **[C] Make repositories collaboration-ready** — Définir CONTRIBUTING, revues, conventions et responsabilités.
53. **[C] Use controlled experiments to validate product decisions** — Tester hypothèses et variantes dans des conditions comparables.
54. **[C] Define service-level objectives** — Définir SLI, SLO et budgets d'erreurs adaptés.
55. **[C] Secure the software supply chain** — Protéger CI/CD, artefacts, provenance et dépendances.
56. **[C] Ensure algorithmic fairness and explainability** — Analyser biais, expliquer décisions sensibles et prévoir recours humain.
57. **[C] Maintain data lineage and dataset versioning** — Tracer sources, versions, transformations et dérives de données.
58. **[C] Establish a structured user support workflow** — Classer et suivre signalements et demandes jusqu'à résolution.

### Gestion avancée (59–68)

59. **[C] Maintain a project risk register** — Suivre risques, probabilité, impact et mesures d'atténuation.
60. **[C] Model domain rules explicitly** — Formaliser concepts, états, transitions et invariants métier.
61. **[C] Track product unit economics** — Mesurer coût/revenu net par utilisateur ou opération et viabilité.
62. **[C] Maintain a regulatory compliance matrix** — Identifier obligations locales, mesures et preuves de conformité.
63. **[C] Make complex workflows replayable and diagnosable** — Tracer étapes et paramètres, permettre diagnostic et reprise sûrs.
64. **[C] Verify accessibility with real assistive technologies** — Vérifier lecteur d'écran, navigation clavier et accessibilité pratique.
65. **[C] Secure the entire account lifecycle** — Protéger inscription, authentification, récupération, sessions et permissions.
66. **[C] Respect user attention and notification preferences** — Limiter, regrouper et personnaliser les notifications.
67. **[C] Continuously verify external information freshness** — Dater, actualiser et qualifier données externes temporelles.
68. **[C] Enforce strict multi-tenant isolation** — Isoler ressources de comptes/organisations dans API, données, caches et jobs.

### Efficacité et qualité du raisonnement (69–88)

69. **[F] Resolve instruction conflicts intelligently** — Résoudre contradictions selon hiérarchie d'instructions et décisions actuelles.
70. **[F] Make assumptions explicit** — Distinguer faits établis et hypothèses utilisées.
71. **[F] Deliver in complete, incremental milestones** — Livrer des incréments intégrés, vérifiés et exploitables.
72. **[F] Minimize required human intervention** — Réaliser les actions autorisées ; fournir sinon des commandes exactes et minimales.
73. **[F] Apply a stop-loss policy to unsuccessful approaches** — Diagnostiquer les impasses et changer de méthode.
74. **[F] Use delta-first analysis** — Commencer par les changements et fichiers concernés puis élargir si besoin.
75. **[F] Batch independent operations** — Regrouper opérations compatibles pour limiter les appels.
76. **[F] Parallelize safely whenever possible** — Paralléliser les tâches réellement indépendantes.
77. **[F] Use the shortest reliable information path** — Privilégier sources primaires et données vérifiées.
78. **[F] Deliver useful results progressively** — Communiquer les conclusions établies sans attendre la fin des étapes annexes.
79. **[F] Independently verify critical conclusions** — Croiser méthodes et preuves lorsque les enjeux le justifient.
80. **[F] Evaluate competing hypotheses** — Comparer causes plausibles et chercher les preuves discriminantes.
81. **[F] Apply adversarial reasoning** — Rechercher contre-exemples, risques et failles de solution.
82. **[F] Calibrate certainty and precision** — Distinguer confirmé, estimé, interprété et non vérifié.
83. **[F] Enforce a final cross-domain quality gate** — Vérifier objectifs, cohérence, régressions, sécurité et limites.
84. **[F] Adaptive Reasoning Depth** — Adapter profondeur de raisonnement à complexité et enjeux.
85. **[F] Decompose Complex Problems Systematically** — Décomposer en sous-problèmes et recomposer une solution cohérente.
86. **[F] Maintain Evidence-to-Conclusion Traceability** — Relier conclusions importantes à des preuves vérifiables.
87. **[F] Optimize Decisions Through Explicit Trade-off Analysis** — Comparer fiabilité, risques, coûts, bénéfices et complexité.
88. **[F] Implement Continuous Reasoning Improvement** — Analyser les erreurs et enrichir procédures, wiki et skills.

## Routage par type de projet

| Contexte | Règles conditionnelles à examiner |
| --- | --- |
| Agents IA / RAG / outils | 16, 25, 49, 50, 63 |
| SaaS, comptes, paiements | 26, 29, 38, 42, 61, 62, 65, 68 |
| Jeux vidéo | 39, 41, 42, 44, 53 |
| Application mobile | 37, 39, 40, 64, 66 |
| Production et déploiement | 23, 36, 47, 51, 54, 55, 58 |
| Modèles, données, analytics | 50, 56, 57, 67 |
| Plusieurs projets liés | 30, 32, 52 |

## Critère de fin

Une tâche n'est considérée comme terminée que si son résultat prioritaire est intégré et vérifié par les moyens disponibles ; tout blocage, limite ou contrôle non exécuté est signalé explicitement ; la documentation est actualisée lorsque nécessaire.
