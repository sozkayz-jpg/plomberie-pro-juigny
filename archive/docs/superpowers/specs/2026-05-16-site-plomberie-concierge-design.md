# Design Spec — Site vitrine plomberie "Concierge de la plomberie"

**Date:** 2026-05-16
**Positionnement:** Urgence (20 min) + Spécialisation (haut de gamme, non destructive, écologique)
**Approche:** Concierge de la plomberie — anti-stereotype du plombier lambda

---

## 1. Objectif & positionnement

Le site doit passer le filtre "oh non encore un site de plombier". Il ne vend pas des tuyaux, il vend un **service premium de conciergerie technique**.

- **Promesse urgence:** "Intervention prioritaire en 20 minutes" présentée comme un service VIP, pas un SOS désespéré.
- **Promesse spécialisation:** 3 univers distincts (haut de gamme, non destructive, écologique) qui crédibilisent le sur-mesure.
- **Ton:** Vouvoiement chaleureux, professionnel, sans jargon. "Nous prenons soin de votre installation" plutôt que "Nous intervenons".

---

## 2. Architecture du site

### Pages

| Page | URL | Rôle |
|------|-----|------|
| Accueil | `/` | Hero conciergerie, urgence VIP, expertises, FAQ, preuve sociale |
| Intervention prioritaire | `/urgence` | Diagnostic rapide, timeline, tarification transparente |
| Nos expertises | `/expertises` | Landing des 3 univers avec liens vers les pages dédiées |
| Expertise détaillée | `/expertises/[slug]` | Page individuelle par spécialisation |
| L'atelier | `/atelier` | Histoire, certifications, équipe, matériaux nobles |
| Journal | `/journal` | Articles techniques accessibles |
| Article | `/journal/[slug]` | Page article individuelle |
| Questions | `/questions` | FAQ complète en accordéon |
| Rendez-vous | `/rendez-vous` | Formulaire structuré comme réservation conciergerie |
| Mentions légales | `/mentions-legales` | Obligatoire France/UE |
| Politique de confidentialité | `/politique-de-confidentialite` | RGPD |

### Flow utilisateur

- **Urgence:** Accueil → Bandeau urgence ou CTA fixe → `/urgence` → Appel direct ou formulaire rapide.
- **Rénovation/Conseil:** Accueil → Expertise carte → `/expertises/[slug]` → `/rendez-vous`.
- **Découverte:** Accueil → L'atelier / Journal → Preuve sociale → Rendez-vous.

---

## 3. Identité visuelle

### Palette

| Token | Hex | Usage |
|-------|-----|-------|
| Encre | `#0A1317` | Titres, texte principal, fond CTA primaire |
| Blanc cassé | `#F7F5F2` | Fond de page |
| Laiton | `#C8A265` | Détails, traits, icônes fines, hover, outline secondaire |
| Émeraude retenue | `#2A5D52` | Badge écologique, accents "green" |
| Grège | `#E8E2DA` | Fonds de cartes, séparations subtiles |

### Typographie

- **Titres:** `Cormorant Garamond` (serif élégant, haut de gamme) ou `Playfair Display`.
  - H1 hero: 48px (desktop) / 32px (mobile), weight 500, line-height 1.15.
  - H2 section: 36px (desktop) / 24px (mobile), weight 500.
  - H3 carte: 24px, weight 500.
- **Corps:** `Inter`, fallback `Helvetica Neue`, `Arial`.
  - Body: 16px, weight 400, line-height 1.60.
  - Body bold: 16px, weight 700.
  - Caption: 14px, weight 400.
- **CTA / Boutons:** `Inter` bold, 14px, tracking -0.14px.

### Formes

- **Boutons:** Pill-shaped (`border-radius: 100px`). Padding primaire `14px 30px`, secondaire `12px 28px`.
- **Cartes photo:** `border-radius: 32px` (rounded.xxxl).
- **Cartes standard:** `border-radius: 16px` (rounded.xl).
- **Inputs:** `border-radius: 8px` (rounded.lg), height 44px.

### Photographie

- **Interdit:** tuyaux rouillés, fuites dramatiques, artisan en salopette, camionnette blanche.
- **Obligatoire:** gros plans robinetterie laiton/cuivre, textures marbre/zellige, mains précises, salles de bain rénovées, lumière naturelle chaude.
- **Urgence:** photo stylisée téléphone sur marbre avec notification "Intervention confirmée — 18 min".

---

## 4. Composants globaux

### Header sticky

- Fond: `Blanc cassé` avec `backdrop-filter: blur(10px)` au scroll.
- Hauteur: ~64px desktop, ~56px mobile.
- Gauche: Logo texte en Cormorant Garamond, lien vers `/`.
- Centre: Navigation — Accueil, Urgence, Expertises, L'atelier, Journal, Questions.
- Droite: CTA fixe *"Intervention prioritaire"* (pill, fond Encre, texte blanc).
- Mobile: Logo + hamburger. Navigation dans un drawer. CTA reste sticky en bas d'écran (`position: fixed; bottom: 16px; left: 50%; transform: translateX(-50%)`).

### Footer

- Fond: `Blanc cassé`, bordure supérieure 1px `Grège`.
- Padding: `80px` top / `40px` bottom desktop.
- 4 colonnes desktop / 1 colonne mobile:
  1. **Marque:** Logo texte + slogan court (1 ligne) + 4 icônes réseaux sociaux.
  2. **Galerie:** 6 vignettes carrées (réalisations), `border-radius: 8px`, gap 8px.
  3. **Adresses:** 1–2 adresses + lien *"Voir sur Google Maps"*.
  4. **Navigation:** Accueil, Urgence, Expertises, L'atelier, Journal, Questions, Mentions légales, Politique de confidentialité.
- Bas: *"© 2026 [NOM_ENTREPRISE] — Tous droits réservés"* en caption `Stone` (couleur à définir: `#8595A4`).

### Boutons

| Variant | Fond | Texte | Bordure | Usage |
|---------|------|-------|---------|-------|
| Primaire | Encre | Blanc cassé | Aucune | CTA principal marketing |
| Primaire pressed | `#1C1E21` | Blanc cassé | Aucune | État actif |
| Secondaire | Transparent | Encre | 2px solid Encre | CTA secondaire |
| Ghost | Transparent | Encre | 1px solid Grège | Tertiaire |
| Urgence | Laiton | Encre | Aucune | CTA urgence spécifique |

---

## 5. Pages détaillées

### Accueil (`/`)

#### Section 1 — Hero
- **Fond:** Photo full-bleed robinetterie laiton sur marbre, `object-fit: cover`.
- **Overlay:** Dégradé subtil `rgba(10,19,23,0.3)` de bas vers haut pour lisibilité du texte.
- **Titre H1:** *"Votre plomberie, traitée comme un art de vivre."* — Blanc, Cormorant Garamond, 48px.
- **Sous-titre:** *"Interventions d'urgence en 20 minutes. Rénovations sans casser les murs. Solutions économies d'eau."* — Blanc, Inter, 18px.
- **Dual-CTA:**
  - *"Demander une intervention prioritaire"* (Primaire)
  - *"Découvrir nos expertises"* (Secondaire)
- **Preuve sociale:** 3 avatars clients superposés + *"127 avis vérifiés — 4.9/5"*.

#### Section 2 — Bandeau Urgence
- **Fond:** Blanc cassé, bordure fine Laiton en haut (2px).
- **3 colonnes:**
  1. Icône téléphone fine + *"Appel pris en direct"*
  2. Icône diagnostic + *"Diagnostic téléphonique immédiat"*
  3. Icône horloge + *"Artisan chez vous en 20 min"*
- **Numéro:** H2 Cormorant Garamond, cliquable `tel:`.

#### Section 3 — À propos (court)
- **Titre H2:** *"Des solutions adaptées à votre cadre de vie"*
- **Texte:** 2-3 lignes sur équipe certifiée, matériaux nobles, démarche éco-responsable.
- **3 points forts:**
  - Professionnels certifiés et assurés
  - Matériel haut de gamme, réparations non destructives
  - Satisfaction et économies d'eau garanties

#### Section 4 — Expertises (grille 3 cartes)
- **Titre H2:** *"Nos expertises"*
- **3 cartes côte à côte** (1 colonne mobile), `border-radius: 32px`, bordure 1px `Grège`, pas de shadow.
  1. **Plomberie haut de gamme** — photo robinetterie design.
  2. **Réparation non destructive** — photo caméra thermique/détection.
  3. **Solutions écologiques** — photo douche économique/matériaux naturels.
- Chaque carte: image top (aspect 4:3, `border-radius: 32px 32px 0 0`), titre H3, description 2 lignes, lien *"Explorer cette expertise →"* en Laiton.

#### Section 5 — Bandeau urgence (CTA contrasté)
- **Fond:** Laiton.
- **Texte:** *"Une situation critique ?"* (Encre, H2)
- **Bouton:** *"Nous contacter"* (Primaire, Encre) → `/urgence`.

#### Section 6 — FAQ (accordéon)
- **Titre H2:** *"Vos questions, nos réponses"*
- **5 items accordéon:**
  1. Vos professionnels sont-ils certifiés et assurés ?
  2. Proposez-vous des devis gratuits ?
  3. Quels moyens de paiement acceptez-vous ?
  4. Proposez-vous des facilités de paiement ?
  5. Comment fonctionne l'intervention non destructive ?
- **Style:** fond Blanc cassé, bordure `Grège` 1px, `border-radius: 16px`. Question en H3, chevron à droite. Réponse en body.
- **CTA:** *"Une autre question ? Contactez-nous"* → `/questions`.

#### Section 7 — Témoignages
- **Titre H2:** *"Ce que disent nos clients"*
- **Carrousel** (swipeable mobile, 3 colonnes desktop) de 4 avis:
  - Photo client (cercle 48px)
  - Nom + source (Google, Trustpilot...)
  - Citation 2-3 lignes
- **Style:** carte `border-radius: 16px`, bordure `Grège`, padding 32px.

#### Section 8 — Journal (3 articles)
- **Titre H2:** *"Nos derniers articles"*
- **3 cartes:** image couverture (aspect 16:9, `border-radius: 16px`), date format français ("8 avril 2026"), titre H3, lien *"Lire l'article →"*.

#### Section 9 — Bandeau CTA final
- **Fond:** Encre.
- **Texte:** *"Besoin d'un professionnel rapidement ?"* (Blanc, H2)
- **Bouton:** *"Appelez-nous au [NUMERO]"* (Urgence, Laiton) — cliquable `tel:`.

---

### Intervention prioritaire (`/urgence`)

- **Hero spécifique:**
  - Titre H1: *"Une situation critique ?"*
  - Numéro en H2, CTA appel direct (Urgence, large pill)
  - Sous-titre: *"Nous sommes disponibles 24h/24 et 7j/7. Appel direct, pas de plateforme."*
- **Timeline visuelle (4 étapes):**
  1. Votre appel — 0 min
  2. Diagnostic téléphonique — 2 min
  3. Confirmation & départ — 5 min
  4. Arrivée sur site — 20 min
- **Tarification transparente (3 niveaux):**
  - Intervention urgente (fuite, bouchon, chauffe-eau) — forfait dépannage.
  - Diagnostic complet (caméra, thermographie, bilan installation).
  - Rénovation sur mesure — devis personnalisé sous 24h.
- **Preuve sociale:** avis spécifiques "intervention urgente".

---

### Expertises (`/expertises`)

- **Hero:**
  - Titre H1: *"Trois expertises, un même exigence."*
  - Sous-titre: *"Haut de gamme, non destructive, écologique."*
- **3 sections verticales** (une par expertise), chacune avec:
  - Image full-bleed à gauche ou droite (alternance), texte opposé.
  - Titre H2.
  - Description 3-4 lignes.
  - 3 avantages (liste avec traits Laiton).
  - CTA: *"Explorer [nom expertise]"* → `/expertises/[slug]`.

---

### Expertise détaillée (`/expertises/[slug]`)

- **Hero spécifique** avec image représentative.
- **Processus** (3-4 étapes visuelles).
- **Réalisations:** galerie photo (grid 2-3 colonnes), `border-radius: 16px`, lazy-loading.
- **Technologies:** icônes + noms (caméra thermique, détecteur acoustique, etc.).
- **FAQ spécifique:** 3-4 questions liées à cette expertise.
- **CTA final:** *"Prendre rendez-vous"* (Primaire) + *"Appeler en urgence"* (Urgence).

---

### L'atelier (`/atelier`)

- **Hero:** photo d'équipe ou d'atelier (pas de salopette, tenue propre et sobre).
- **Histoire:** 2-3 paragraphes sur la création, la vision.
- **Équipe:** photos individuelles (carré, `border-radius: 16px`), nom, rôle, certification.
- **Certifications & assurances:** logos + descriptions.
- **Matériaux nobles:** galerie cuivre, laiton, inox brossé.

---

### Journal (`/journal`)

- **Hero:** Titre H1 *"Journal"* + sous-titre.
- **Grille d'articles:** 2 colonnes desktop, 1 colonne mobile.
- Chaque article: image 16:9 (`border-radius: 16px`), date, catégorie badge, titre H3, extrait 2 lignes.

---

### Article (`/journal/[slug]`)

- **Header:** image couverture full-bleed, titre H1, date, temps de lecture.
- **Corps:** typographie lisible, interligne 1.6, max-width 720px centrée.
- **Partage:** icônes réseaux sociaux.
- **Articles liés:** 3 cartes en bas.

---

### Questions (`/questions`)

- **Hero:** Titre H1 *"Questions"*.
- **Accordéon complet:** 8-10 questions.
- **CTA final:** *"Votre question n'est pas ici ? Contactez-nous directement."* → `/rendez-vous`.

---

### Rendez-vous (`/rendez-vous`)

- **Hero:** Titre H1 *"Prendre rendez-vous"*.
- **Formulaire structuré comme réservation:**
  - Type de demande (radio): Urgence / Diagnostic / Rénovation / Conseil écologique.
  - Nom, email, téléphone.
  - Adresse (si intervention sur site).
  - Message / Description du besoin (textarea).
  - Case à cocher RGPD obligatoire: *"J'accepte que mes données soient traitées..."*
- **CTA:** *"Confirmer ma demande"* (Primaire).
- **Alternative:** *"Préférez-vous appeler ? [NUMERO]"* en dessous.

---

## 6. Responsive & performance

### Breakpoints

| Nom | Largeur | Changements clés |
|-----|---------|-----------------|
| Mobile | < 768px | 1 colonne, hero texte 32px, nav drawer, CTA sticky bottom, cartes empilées |
| Tablette | 768–1023px | 2 colonnes pour expertises et journal, nav complète |
| Desktop | ≥ 1024px | 3-4 colonnes, nav complète, hero 48px |

### Performance cible

- Lighthouse > 90 sur tous les critères.
- LCP < 2.5s.
- Images: format WebP, lazy-loading natif (`loading="lazy"`), tailles responsives (`srcset`).
- Polices: `font-display: swap`.

---

## 7. SEO & accessibilité

### SEO

- **Title + Description** uniques par page, en français.
- **URLs** propres en français (`/a-propos` remplacé par `/atelier`, etc.).
- **Schema.org:**
  - `LocalBusiness` sur homepage (nom, adresse, téléphone, zone géographique).
  - `Service` sur `/expertises` et `/expertises/[slug]`.
  - `FAQPage` sur `/questions` et section FAQ homepage.
  - `Review` sur témoignages.
- **Open Graph + Twitter Cards** pour chaque page.
- **Sitemap.xml** + **robots.txt**.

### Accessibilité

- `alt` descriptifs sur toutes les images (jamais "image1").
- Hiérarchie titres correcte (1 seul H1 par page).
- Contrastes WCAG AA minimum (Encre sur Blanc cassé = OK, vérifier Laiton sur Blanc cassé).
- Navigation clavier complète (focus visible).
- Liens explicites (pas de "cliquez ici").
- `aria-label` sur icônes et boutons sans texte.
- Formulaires: `<label>` associés, erreurs inline, `aria-invalid`.

---

## 8. Conformité légale (France/UE)

- **Mentions légales** complètes (page dédiée).
- **Politique de confidentialité** (RGPD).
- **Bandeau cookies** conforme CNIL si tracking (Google Analytics, etc.).
- Formulaire contact: case de consentement RGPD obligatoire.

---

## 9. Variables à personnaliser

| Variable | Description | Exemple |
|----------|-------------|---------|
| `{{NOM_ENTREPRISE}}` | Nom commercial | "L'Atelier du Flow" |
| `{{VILLE}}` | Zone d'intervention | "Paris" |
| `{{ANNEES_EXPERIENCE}}` | Années d'expérience | "15" |
| `{{TELEPHONE}}` | Numéro de contact | "01 23 45 67 89" |
| `{{NB_AVIS}}` | Nombre d'avis clients | "127" |
| `{{NOTE_AVIS}}` | Note moyenne | "4.9" |
| `{{ADRESSE_1}}` | Adresse principale | "12 Rue de la Paix, 75002 Paris" |
| `{{ADRESSE_2}}` | Adresse secondaire (optionnel) | — |
| `{{EMAIL}}` | Email contact | "contact@atelierduflow.fr" |
| `{{ANNEE}}` | Année courante | "2026" |

---

## 10. Checklist livrables

- [ ] Site fonctionnel (Next.js recommandé pour SSG/SSR, SEO, performance).
- [ ] Toutes les pages listées créées et reliées.
- [ ] Contenu en français intégré (interface, CTA, métadonnées, URLs).
- [ ] Formulaire de contact opérationnel (notification email via service tiers: Resend, SendGrid, ou formulaire netlify).
- [ ] Tests responsive validés (mobile, tablette, desktop).
- [ ] Tests accessibilité validés (contrastes, navigation clavier, lecteur d'écran).
- [ ] Documentation de prise en main pour le client (comment modifier texte, ajouter un article, changer le numéro de téléphone).
