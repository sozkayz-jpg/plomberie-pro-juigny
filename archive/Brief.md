# 📋 Brief de création de site vitrine — Template générique services à domicile

## 🎯 Objectif du projet
Créer un **site vitrine professionnel en français** pour une entreprise de **[SECTEUR D'ACTIVITÉ]** (ex : plomberie, électricité, serrurerie, chauffage, climatisation, jardinage, menuiserie, etc.), destinée à une clientèle locale (particuliers et/ou professionnels).

Le site doit inspirer **confiance, professionnalisme et réactivité**, tout en facilitant la prise de contact rapide.

---

## 🧩 Variables à personnaliser (à remplir avant production)

| Variable | Description | Exemple |
|----------|-------------|---------|
| `{{NOM_ENTREPRISE}}` | Nom commercial | Ex : "PlomberiePro" |
| `{{SECTEUR}}` | Secteur d'activité | Ex : "plomberie" |
| `{{VILLE}}` | Zone d'intervention | Ex : "Paris" |
| `{{ANNEES_EXPERIENCE}}` | Années d'expérience | Ex : "20" |
| `{{TELEPHONE}}` | Numéro de contact | Ex : "01 23 45 67 89" |
| `{{NB_AVIS}}` | Nombre d'avis clients | Ex : "2000+" |
| `{{DELAI_INTERVENTION}}` | Délai d'arrivée | Ex : "30 minutes" |
| `{{SERVICES[]}}` | Liste de 6 services | À définir selon métier |
| `{{ADRESSES[]}}` | 1 à 2 adresses physiques | — |

---

## 🌐 Langue & ton
- **Langue : Français exclusivement** (interface, contenu, CTA, méta-données, URLs)
- **Ton** : professionnel, rassurant, accessible, orienté action
- **Vouvoiement** systématique
- **Vocabulaire** simple, sans jargon technique excessif

---

## 🏗️ Architecture du site

### Pages à créer
- `/` — Accueil
- `/a-propos` — À propos
- `/contact` — Contact
- `/blog` — Liste des articles
- `/services/[slug]` — 6 pages services dédiées
- `/blog/[slug]` — Pages articles individuelles

---

## 📐 Structure de la page d'accueil (sections)

### 1. 🔝 En-tête (Header)
- Logo de l'entreprise (lien vers accueil)
- Menu de navigation : **Accueil / À propos / Contact / Blog**
- Bouton CTA principal : *"Nous contacter"* ou *"Devis gratuit"*
- Header **sticky** (collant au scroll)

### 2. 🦸 Section Héro
- **Titre H1** : `"Votre expert en {{SECTEUR}} de confiance à {{VILLE}}"`
- **Sous-titre** : `"Avec plus de {{ANNEES_EXPERIENCE}} ans d'expérience, nous vous offrons des solutions sur mesure adaptées à vos besoins."`
- **Bouton CTA principal** : *"Demander un devis gratuit"*
- **Preuve sociale** :
  - 3 avatars clients superposés
  - Mention : `"{{NB_AVIS}} avis clients"` (lien vers plateforme d'avis)
- **Visuel de fond** : photo professionnelle métier

### 3. 📞 Bandeau avantages (3 colonnes)
| Icône | Titre | Description |
|-------|-------|-------------|
| 📱 | **Appelez-nous au {{TELEPHONE}}** | Disponibles 24h/24 et 7j/7 |
| 🔍 | **Diagnostic expert** | Nous trouvons la solution adaptée |
| ⏱️ | **Intervention en {{DELAI_INTERVENTION}}** | Équipement complet inclus |

### 4. 🏠 Section À propos (courte)
- 2 photos illustratives (cliquables → `/a-propos`)
- **Titre H2** : `"Des solutions de {{SECTEUR}} adaptées à vos besoins"`
- Paragraphe de présentation (équipe certifiée/qualifiée)
- **3 points forts** :
  - ✅ Professionnels qualifiés et assurés
  - ✅ Matériel haut de gamme
  - ✅ Satisfaction client garantie

### 5. 🛠️ Section Services (grille de 6 cartes)
- **Titre H2** : *"Nos services"*
- **Sous-titre** descriptif
- 6 cartes services cliquables, chacune avec :
  - Icône ou image
  - Titre du service
  - Courte description (1-2 lignes)
  - Lien *"En savoir plus →"*

### 6. 🚨 Bandeau urgence
- Texte : `"Une urgence en {{SECTEUR}} ?"`
- Bouton : *"Nous contacter"* → `/contact`
- Fond contrasté (couleur d'accentuation)

### 7. ❓ Section FAQ
- **Titre H2** : *"Vos questions, nos réponses"*
- 4 à 6 questions en **accordéon** :
  1. Vos professionnels sont-ils certifiés et assurés ?
  2. Proposez-vous des devis gratuits ?
  3. Quels moyens de paiement acceptez-vous ?
  4. Proposez-vous des facilités de paiement ?
- Lien complémentaire : *"Une autre question ? Contactez-nous"*

### 8. ⭐ Section Témoignages
- **Titre H2** : *"Ce que disent nos clients"*
- Carrousel de **4 avis clients** avec :
  - Photo du client
  - Nom
  - Source de l'avis (Google, Trustpilot, Facebook…)
  - Citation courte (2-3 lignes)

### 9. 📰 Section Blog
- **Titre H2** : *"Nos derniers articles"*
- Grille de **3 articles récents** avec :
  - Image de couverture
  - Date de publication (format français : *"8 avril 2024"*)
  - Titre
  - Lien *"Lire l'article →"*

### 10. 🔴 Bandeau CTA final
- Texte : `"Besoin d'un professionnel rapidement ?"`
- Bouton : `"Appelez-nous au {{TELEPHONE}}"` (cliquable `tel:`)

### 11. 🦶 Pied de page (Footer)
**Colonne 1 — Marque**
- Logo
- Slogan court (1 ligne)
- 4 icônes réseaux sociaux (Facebook, Twitter/X, Instagram, YouTube/LinkedIn)

**Colonne 2 — Galerie / Instagram**
- 6 vignettes (feed Instagram ou galerie réalisations)

**Colonne 3 — Adresses**
- 1 à 2 adresses avec lien *"Voir sur Google Maps"*

**Colonne 4 — Navigation**
- Liens : Accueil / À propos / Contact / Blog / Mentions légales / Politique de confidentialité

**Bas de footer**
- `© {{ANNEE}} {{NOM_ENTREPRISE}} — Tous droits réservés`

---

## ♿ Accessibilité (obligatoire)
- ✅ Tous les attributs `alt` renseignés sur les images (descriptifs, non génériques)
- ✅ Hiérarchie correcte des titres (1 seul H1 par page)
- ✅ Contrastes conformes **WCAG AA** minimum
- ✅ Navigation possible **au clavier**
- ✅ Liens explicites (éviter "cliquez ici")
- ✅ Attributs `aria-label` sur icônes et boutons sans texte
- ✅ Formulaires avec `<label>` associés

---

## 🔍 SEO
- **Balises meta** (title + description) uniques par page, en français
- **URLs** propres en français (`/a-propos`, `/services/depannage`, etc.)
- **Données structurées** Schema.org : `LocalBusiness`, `Service`, `FAQPage`, `Review`
- **Sitemap.xml** + **robots.txt**
- **Open Graph** + **Twitter Cards** pour partage social
- Optimisation mots-clés locaux : `{{SECTEUR}} + {{VILLE}}`

---

## 📱 Responsive & performance
- **Mobile-first** : design pensé d'abord pour smartphone
- Breakpoints : mobile (<768px), tablette (768-1024px), desktop (>1024px)
- **Performance cible** :
  - Lighthouse > 90 sur tous les critères
  - LCP < 2,5s
  - Images optimisées (WebP, lazy-loading)

---

## ⚖️ Conformité légale (France/UE)
- **Mentions légales** complètes (page dédiée)
- **Politique de confidentialité** (RGPD)
- **Bandeau cookies** conforme CNIL (si tracking)
- Formulaire contact : case de consentement RGPD obligatoire

---

## 🎨 Direction artistique (à définir)
- **Palette** : 1 couleur primaire métier + 1 couleur d'accentuation (urgence/CTA) + neutres
- **Typographie** : 1 police titre + 1 police corps (lisibles, web-safe)
- **Iconographie** : style cohérent (line ou solid, pas de mélange)
- **Photographies** : authentiques de l'équipe/réalisations (éviter banques d'images génériques)

---

## ✅ Livrables attendus
1. Site fonctionnel sur l'environnement choisi (Framer, Webflow, WordPress, etc.)
2. Toutes les pages listées créées et reliées
3. Contenu en français intégré
4. Formulaire de contact opérationnel (avec notification email)
5. Tests responsive et accessibilité validés
6. Documentation de prise en main pour le client

---

## 🚫 Points de vigilance
- ❌ Éviter la **duplication de blocs** (CTA et footer ne doivent apparaître qu'**une seule fois**)
- ❌ Ne pas laisser de contenu en anglais (boutons, placeholders, messages d'erreur compris)
- ❌ Pas d'images sans `alt` ou avec `alt=""` non décoratif
- ❌ Éviter les numéros de téléphone et adresses fictifs en production
