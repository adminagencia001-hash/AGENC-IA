# Architecture (proposition à valider)

## Contrainte
Application **mobile (iOS/Android) et web**, pour une petite communauté (la famille), avec des données privées.

## Option recommandée : une seule base de code
- **Front** : React Native + Expo (Expo Router, `react-native-web` pour la version web), TypeScript
- **Back** : Supabase (PostgreSQL, authentification, stockage de fichiers, règles d'accès par ligne)
- **Recherche** : recherche plein texte PostgreSQL
- **Hors ligne** : cache local pour consulter les fiches sans réseau

Avantages : un seul code pour trois plateformes, peu d'infrastructure à gérer, coût faible.

## Alternatives
| Option | Pour | Contre |
|---|---|---|
| Flutter + Firebase | Interface très homogène | Web moins naturel, autre langage (Dart) |
| PWA seule (web installable) | Le plus simple et le moins cher | Moins de fonctions natives sur mobile, pas de présence dans les stores |

## Points d'attention
- Confidentialité : accès uniquement sur invitation, chiffrement en transit, sauvegardes régulières
- RGPD : les données familiales peuvent inclure des mineurs (consentement, export, suppression)
- Rôles : administrateur / adulte / enfant (droits distincts)

## Décisions à prendre
- [ ] Valider la pile technique
- [ ] Choisir l'hébergement (région UE conseillée)
