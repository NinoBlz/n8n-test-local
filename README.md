# Automatisation n8n - Collecte des Besoins pour Création de Site Web

## 📋 Description

Cette automatisation n8n permet de recueillir de manière structurée tous les besoins d'un client (particulier, commerce, entreprise) pour la création d'un site web et génère automatiquement un **prompt complet et détaillé** prêt à utiliser.

## 🎯 Fonctionnalités

### Formulaire de Collecte
Le workflow comprend un formulaire web complet qui collecte :

- **Informations générales**
  - Type d'organisation (Particulier, Commerce, PME, etc.)
  - Nom et secteur d'activité
  - Contact (email, téléphone)

- **Détails du projet**
  - Type de site (vitrine, e-commerce, blog, portfolio, etc.)
  - Objectif principal
  - Public cible
  - Fonctionnalités souhaitées

- **Design et identité visuelle**
  - Charte graphique existante
  - Couleurs préférées
  - Style visuel (moderne, professionnel, créatif, etc.)
  - Sites de référence

- **Contenu**
  - Disponibilité du contenu
  - Nombre de pages estimé
  - Langues du site

- **Aspects techniques**
  - Besoins SEO
  - Intégrations nécessaires (Analytics, CRM, paiement, etc.)

- **Contraintes projet**
  - Budget approximatif
  - Délai souhaité
  - Besoins en maintenance et hébergement

### Génération de Prompt
Le workflow génère automatiquement :
- Un **cahier des charges structuré**
- Un **prompt complet** pour développeur/designer
- Les **données brutes** pour traitement ultérieur

### Options Supplémentaires (désactivées par défaut)
- Sauvegarde dans Google Sheets
- Email de confirmation au client
- Email avec le prompt à votre équipe

## 🚀 Installation

### 1. Importer le Workflow dans n8n

1. Ouvrez votre instance n8n
2. Cliquez sur le menu hamburger (☰) en haut à gauche
3. Sélectionnez **Import from File** ou **Import from URL**
4. Importez le fichier `workflow-besoins-site-web.json`

### 2. Configuration du Formulaire

Le formulaire est prêt à l'emploi ! Une fois activé :

1. Activez le workflow
2. Cliquez sur le nœud "Formulaire de Collecte"
3. Cliquez sur "Test URL" pour obtenir l'URL du formulaire
4. Partagez cette URL avec vos clients

**L'URL ressemblera à :**
```
https://votre-instance-n8n.com/form/collecte-besoins-site-web
```

### 3. Configuration des Options (Facultatif)

#### A. Activer la sauvegarde Google Sheets

1. Activez le nœud "Sauvegarde Google Sheets" (cliquez pour désactiver le mode "disabled")
2. Créez une Google Sheet avec les colonnes suivantes :
   - Date
   - Client
   - Email
   - Type de Projet
   - Budget
   - Délai
   - Statut
3. Configurez les credentials Google Sheets dans n8n
4. Remplacez `VOTRE_GOOGLE_SHEET_ID` par l'ID de votre feuille

#### B. Activer les notifications par email

1. Activez les nœuds "Email au Client" et/ou "Email à l'Équipe"
2. Configurez vos credentials SMTP dans n8n
3. Remplacez les adresses email :
   - `votre-email@domaine.com` → votre adresse d'envoi
   - `equipe@votre-domaine.com` → adresse de votre équipe

## 📝 Utilisation

### Pour le Client

1. Le client accède au formulaire via l'URL fournie
2. Il remplit toutes les informations demandées
3. Il soumet le formulaire
4. Il reçoit une confirmation (si email activé)

### Pour Vous

1. Le workflow génère automatiquement :
   - Un prompt structuré et complet
   - Un cahier des charges détaillé
2. Vous recevez les informations par email (si activé)
3. Les données sont sauvegardées dans Google Sheets (si activé)
4. Vous pouvez récupérer le prompt pour :
   - Le donner à votre équipe de développement
   - L'utiliser avec des outils IA (ChatGPT, Claude, etc.)
   - L'intégrer dans votre système de gestion de projet

## 📤 Format du Prompt Généré

Le workflow génère un prompt en 2 parties :

### 1. Cahier des Charges Complet
Structure détaillée avec toutes les informations collectées organisées par section.

### 2. Prompt Synthétique
Version condensée et actionnable pour un développeur/designer, incluant :
- Contexte du projet
- Objectifs et public cible
- Fonctionnalités clés
- Style et design
- Contraintes (budget, délai, etc.)
- Inspirations et références

## 🔧 Personnalisation

### Ajouter des Questions

Dans le nœud "Formulaire de Collecte", section `formFields.values`, ajoutez :

```json
{
  "fieldLabel": "Votre question",
  "fieldType": "text",
  "requiredField": true,
  "placeholder": "Texte d'aide"
}
```

**Types de champs disponibles :**
- `text` : Texte court
- `textarea` : Texte long
- `email` : Email
- `number` : Nombre
- `dropdown` : Liste déroulante
- `date` : Date

### Modifier le Prompt

Dans le nœud "Génération du Prompt", modifiez le code JavaScript pour personnaliser le format du prompt généré.

## 💡 Exemples d'Utilisation

### Cas 1 : Agence Web
- Utilisez ce workflow comme formulaire de premier contact
- Sauvegardez automatiquement dans Google Sheets pour suivi
- Envoyez le prompt à votre chef de projet

### Cas 2 : Freelance
- Intégrez le formulaire sur votre site web
- Recevez directement le prompt par email
- Utilisez-le pour générer des devis précis

### Cas 3 : IA/Développement
- Collectez les besoins clients
- Générez un prompt structuré
- Utilisez-le avec ChatGPT/Claude pour générer du code initial

## 🆘 Support

### Problèmes Courants

**Le formulaire ne s'affiche pas**
- Vérifiez que le workflow est activé
- Vérifiez l'URL du webhook

**Le prompt n'est pas généré**
- Vérifiez que tous les champs requis sont remplis
- Consultez les logs d'exécution dans n8n

**Les emails ne sont pas envoyés**
- Vérifiez vos credentials SMTP
- Vérifiez que les nœuds email sont activés

## 📄 Licence

Ce workflow est fourni tel quel, libre d'utilisation et de modification.

---

**Version :** 1.0
**Dernière mise à jour :** 2025-11-13
