# Politique de validation

Préférence explicite du propriétaire : **ne pas créer de nouveaux tests unitaires**.

Les tests unitaires déjà présents ne doivent pas être supprimés automatiquement. Ils peuvent être exécutés pour diagnostiquer une régression lorsque nécessaire. Les recommandations de tests produites par un index sont des indices, jamais la preuve d'une exécution.

## Ordre recommandé

1. Contrôles de syntaxe, formatage, typage et lint lorsque pertinents.
2. Parcours fonctionnels réels et vérifications d'intégration ciblées.
3. Build, packaging, démarrage et smoke checks adaptés au projet.
4. Vérifications de compatibilité, déploiement et sécurité selon les risques.
5. Utilisation éventuelle de contrôles préexistants pour diagnostiquer les erreurs.

Documenter les commandes dans `README.md` ou `.ai/project-state.md`. Distinguer les contrôles **exécutés et réussis**, **échoués** et **non exécutés**. Ne jamais déclarer de validation réussie sans preuve d'exécution.

Voir [les 88 règles générales](88-rules.md).
