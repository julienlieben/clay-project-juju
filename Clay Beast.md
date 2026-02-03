# Clay Beast - Guide Expert Complet

## Qu'est-ce que Clay?

Clay est une plateforme de data enrichment et d'automatisation pour les équipes sales et marketing. Elle permet de:
- Sourcer des leads depuis multiples sources
- Enrichir les données avec 75+ providers
- Créer des workflows automatisés
- Personnaliser l'outreach à grande échelle
- Synchroniser avec les CRMs

---

## 1. CORE CONCEPTS

### Tables
La base de Clay. Chaque table contient des données (personnes, entreprises, etc.) que tu peux enrichir et manipuler.

**Types de tables:**
- People tables (contacts)
- Company tables (entreprises)
- Custom tables (données personnalisées)

**Actions sur les tables:**
- Rename, Duplicate, Delete
- Edit descriptions
- Convert formats
- Create from template
- Import files (CSV, etc.)
- Export/Download

### Colonnes
Chaque colonne représente un type de données.

**Limites:**
- 70 colonnes max par table
- 30 action/integration columns max (40 avec waterfall)
- 8,000 caractères max par cell

**Operations sur les colonnes:**
- Rename, Pin, Duplicate, Delete
- Insert left/right
- Hide, Reorder, Sort, Filter, Merge
- Data type selection (crucial pour le bon fonctionnement)
- AI-powered columns
- Colored columns pour organisation

### Rows (Lignes)
Chaque ligne = un record (une personne, une entreprise, etc.)

**Gestion des rows:**
- Add rows manuellement
- Import depuis fichiers
- Import depuis intégrations
- Format rows (starting point, limits)
- Inspect cell details

### Workbooks
Connectent et visualisent plusieurs tables ensemble. Utile pour les workflows complexes qui passent d'une table à l'autre.

### Folders
Organisation des tables par catégories/projets.

---

## 2. DATA IMPORT & SOURCING

### Sources d'import

**Fichiers:**
- CSV
- Excel
- Google Sheets

**Intégrations CRM:**
- HubSpot
- Salesforce
- Pipedrive
- Close

**LinkedIn:**
- LinkedIn Sales Navigator
- LinkedIn URLs
- LinkedIn Company Pages

**Autres sources:**
- Apollo.io
- Google Maps
- Yelp
- GitHub
- Hacker News
- Google Scholar

### Chrome Extension
Deux extensions disponibles:

**1. Clay for Chrome:**
- Extraire des données structurées des pages web
- Auto-detect lists sur les pages
- Map your own lists (cliquer 2 items → selector automatique)
- Map Page Recipes (templates pour pages similaires)
- Export vers Clay table, CSV, ou clipboard

**2. Clip to Clay:**
- Sauvegarder des pages entières vers les tables Clay

---

## 3. DATA ENRICHMENT

### Concept du Waterfall
Le waterfall permet d'enchaîner plusieurs providers d'enrichissement. Si le premier ne trouve pas la donnée, le suivant prend le relais. Accès à 150+ databases.

**Avantages:**
- Maximise la couverture (triple la couverture typiquement)
- Optimise les coûts (arrête dès qu'une donnée est trouvée)
- Améliore la qualité des données
- Crédits refundés si aucune donnée trouvée

**Comment ça fonctionne:**
1. Provider 1 cherche → trouvé? Stop. Pas trouvé? Suivant.
2. Continue jusqu'à données trouvées ou providers épuisés
3. Validation automatique intégrée (ZeroBounce par défaut)

**Inputs recommandés:**
- Principal: Company Domain
- Améliore précision: Personal Social Profile URLs
- Fallback: Full Name + Company Name

**Custom Waterfall:**
Tu peux créer tes propres combinaisons d'intégrations pour maximiser qualité et couverture.

### Providers d'enrichissement (296+ intégrations)

**Email Discovery:**
- Hunter
- Prospeo
- Apollo.io
- RocketReach
- FindyMail
- LeadMagic
- DropContact
- Icypeas
- Nimbler
- Mixrank
- Wiza
- FullEnrich

**Company Research:**
- Apollo.io
- Clearbit
- PredictLeads
- Harmonic.ai

**Données fournies:**
- Firmographics
- Technology stacks
- Fundraising data
- Employee headcount

**Email Validation:**
- NeverBounce
- Debounce
- Enrichley
- Zero Bounce
- FindyMail
- LeadMagic

**Location & Local Business:**
- Google Maps
- Yelp
- Mapbox
- Lob

**Web Scraping:**
- Bright Data
- Zenrows
- Apify
- PhantomBuster
- Clay Scrapers

---

## 4. AI & FORMULAS

### Claygent
L'agent AI de Clay. Combine Google Search, ChatGPT, et web scraping en un outil.

**Modèles disponibles:**
- Claygent Neon (flagship, optimisé pour extraction/formatting)
- GPT-4 (raisonnement profond)
- Claude Opus (raisonnement profond)

**Coûts:**
- Questions simples: 1 crédit
- Analyses profondes: 2-3 crédits

**Claygent vs AI Integrations:**
Claygent = recherche web autonome, scraping, extraction
AI Integrations (OpenAI, Claude, etc.) = génération de texte, analyse de données existantes

### AI Integrations disponibles
- OpenAI/GPT
- Google Gemini
- Anthropic Claude
- Tavus (video generation)

**Use cases:**
- Text generation
- Image creation
- Data analysis
- Personalized messaging

### Formulas
Manipulent les données sans dépenser de crédits. Basées sur **Clayscript** (JavaScript).

**Bibliothèques supportées:**
- JavaScript standard (Math, String, Array, Date, etc.)
- Lodash (`_`) pour manipulation avancée
- Moment.js (`moment`) pour dates
- FormulaJS (VLOOKUP, IF, SUM, CONCATENATE, etc.)

**Types de formulas:**
- String manipulation
- Data formatting
- Calculations
- Conditional logic

**AI Formula Generator:** Tape tes instructions en langage naturel → génère automatiquement

### Conditional Formulas
Définissent des conditions pour exécuter des enrichissements.

**Exemple:**
"Run this enrichment only if Company Size > 50"

---

## 5. OUTBOUND & CRM SYNC

### Push to Email Sequencers
Clay s'intègre avec:
- Instantly.ai
- lemlist
- Smartlead.ai
- HeyReach
- Sendspark
- Salesloft
- Outreach

### CRM Enrichment
Clay fonctionne comme une couche d'enrichissement avec sync bidirectionnelle.

**CRMs supportés:**
- HubSpot
- Salesforce
- Pipedrive
- Close
- Attio

**Types d'actions:**

*Lookup (read-only):*
- Pull data FROM CRM INTO Clay
- Ne modifie rien dans le CRM
- Sans risque, expérimenter librement

*Create & Update (write):*
- Push data FROM Clay TO CRM
- Modifications permanentes
- Être prudent et méthodique

**Fonctionnement:**
- Import depuis CRM
- Enrichissement dans Clay
- Push back vers CRM
- Sync automatique

**Note Salesforce:** Reports limités à 2,000 records, préférer imports depuis listes

---

## 6. JOB CHANGE TRACKING

### Fonctionnalité clé
Surveille les changements de poste de tes contacts.

### Deux méthodes

**1. Monitor existing table:**
- Actions > Monitor for Job Changes
- Spécifier la colonne LinkedIn URL
- Save and run

**2. Create new tracking table:**
- +Create New > Table > Track Job Changes
- Ou copier un template

### Historical vs Future Tracking

**Historical:**
- Inclure "Company LinkedIn URL"
- Vérifie si le contact a changé d'entreprise

**Future:**
- Seulement "Person LinkedIn URL"
- Surveille les changements futurs

### Comportement
- Nouvelle row créée pour chaque changement détecté
- Historique complet maintenu
- Délai de quelques minutes à plusieurs heures selon volume

---

## 7. ACCOUNT SETTINGS

### Account
- API Key (pour intégrations tierces)
- Account name

### Workspace
- Rename workspace
- Organization settings

### Team
- Invite members
- Share access to tables
- Share integrations

### Connections
- Public accounts (pas de credentials nécessaires)
- External accounts (75+ providers)

### Referrals
- Invite friends = earn credits

---

## 8. AUTO-UPDATE & AUTO-DEDUPE

### Auto-Update
Active les mises à jour automatiques des tables.
- Les enrichissements se relancent périodiquement
- Données toujours fraîches
- Contrôle à deux niveaux: table ET colonne
- Table OFF = rien ne tourne auto (override tout)
- **Attention:** Consomme des crédits à chaque refresh

### Auto-Dedupe
Supprime automatiquement les doublons.
- Basé sur email, LinkedIn URL, ou autre identifiant unique
- Maintient la propreté des données
- Économise des crédits (pas d'enrichissement double)
- **Limitation:** Garde la row la plus ANCIENNE, supprime les plus récentes
- Deduplication est case-sensitive ("Clay" ≠ "clay")
- Whitespace compte ("Clay " ≠ "Clay")

---

## 9. HTTP API ACTIONS

### Utilisation
Pour les intégrations non-natives, utiliser HTTP API actions.

**Configuration:**
1. Créer un compte HTTP API (Headers)
2. Ajouter les headers (Authorization, Content-Type)
3. Configurer l'endpoint
4. Définir le body (JSON)
5. Mapper les colonnes

**Exemple beehiiv:**
```
Method: POST
Endpoint: https://api.beehiiv.com/v2/publications/{pub_id}/subscriptions
Headers:
  - Authorization: Bearer {API_KEY}
  - Content-Type: application/json
Body: {"email": {{Email}}}
```

### Run Settings
- Auto-update: ON/OFF
- Only run if: condition (ex: {{Email}} exists)

---

## 10. VIEWS & VISUALIZATION

### Views
Combinaisons sauvegardées de filtres, tris, et customisations.
- Switch entre views via dropdown
- Add/Duplicate/Delete views
- Chaque view = différente perspective sur les mêmes données

### Filters
- AND logic: toutes conditions vraies
- OR logic: au moins une condition vraie
- Jusqu'à 2 niveaux de profondeur de filter groups
- Types: equal to, not equal to, is empty, is not empty, boolean

### Sorting
- Ascending: A→Z, petit→grand
- Descending: Z→A, grand→petit
- Par type de données (alpha, numérique, date)

### Column Management
- Show/Hide colonnes individuellement
- Drag & drop pour réorganiser
- "Show all" / "Hide all" pour bulk operations

### Table History
- Track changes
- Access previous versions
- Audit trail

---

## 11. WORKFLOW PATTERNS

### Pattern 1: Lead Sourcing
```
Source (LinkedIn/Apollo) → Enrichment (Email/Phone) → Validation → Push to CRM/Sequencer
```

### Pattern 2: Account Research
```
Company List → Firmographic Enrichment → Tech Stack → Decision Makers → Outreach
```

### Pattern 3: Intent-Based Outreach
```
Job Change Monitor → Filter (ICP fit) → Personalization → Sequencer
```

### Pattern 4: Data Hygiene
```
CRM Import → Dedupe → Re-enrich → Validate Emails → Update CRM
```

### Pattern 5: Waterfall Enrichment
```
Lead → Provider 1 → (if empty) Provider 2 → (if empty) Provider 3 → Output
```

---

## 12. BEST PRACTICES

### Credits Management
- Formulas = 0 credits
- Enrichments = variable credits (1-25 credits depending on action)
- Use conditional logic to avoid wasting credits
- See Section 16 for detailed credit costs

### Data Quality
1. Always validate emails before outreach
2. Use waterfall for maximum coverage
3. Dedupe regularly
4. Set up auto-update for fresh data

### Workflow Design
1. Start simple, add complexity gradually
2. Test with small batches first
3. Use conditions to control enrichment flow
4. Document your workflows

### Integration Tips
1. Use native integrations when available
2. HTTP API for custom needs
3. Zapier/n8n as middleware when needed
4. Always test with one row first

---

## 13. COMMON USE CASES

### Sales Development
- Lead sourcing from ICP criteria
- Contact enrichment (email, phone)
- Personalization data gathering
- Push to sales engagement tools

### Account-Based Marketing
- Target account list building
- Buying committee mapping
- Intent signal tracking
- Multi-channel outreach coordination

### Recruiting
- Candidate sourcing
- Contact information finding
- Company research
- Outreach automation

### Market Research
- Company database building
- Technology landscape mapping
- Competitive intelligence
- Industry analysis

---

## 14. INTEGRATIONS COMPLÈTES (296+)

### Email & Contact Discovery
Hunter, Prospeo, Apollo.io, RocketReach, FindyMail, LeadMagic, DropContact, Icypeas, Nimbler, Mixrank, Wiza, FullEnrich

### CRM & Sales
HubSpot, Salesforce, Pipedrive, Close, Salesloft, Outreach, Attio

### Email Campaign
Lemlist, Smartlead.ai, Instantly, HeyReach, Sendspark

### Company Research
Apollo.io, Clearbit, PredictLeads, RocketReach, Harmonic.ai

### Email Validation
NeverBounce, Debounce, Enrichley, Zero Bounce, FindyMail, LeadMagic

### AI & Content
OpenAI/GPT, Google Gemini, Anthropic Claude, Tavus

### Location & Business
Google Maps, Yelp, Mapbox, Lob

### Web Scraping
Bright Data, Zenrows, Apify, PhantomBuster, Clay Scrapers

### Database & Webhooks
Postgres, Snowflake, Airtable, Coda, Google Sheets, Zapier, n8n

### Social & Dev
GitHub, LinkedIn, Instagram, Hacker News, Google Scholar

### Intent & Signals
Common Room, Teamfluence, Midbound

---

## 15. CLAY INTERNAL TOOLS

Operations internes sans crédits:
- String matching
- Deduplication
- URL validation
- Filtering operations
- Data formatting
- Conditional logic

---

## 16. CREDITS - DÉTAILS COMPLETS

### Ce qui coûte des crédits

**Enrichissements (coûts variables):**
- Email discovery: 2-5 crédits selon le provider (Hunter = 2, People Data Labs = 5)
- Mobile phone numbers: 2-25 crédits (données plus difficiles à obtenir)
- Company revenue, LinkedIn profiles, contact research: variable
- AI features: basé sur le modèle sélectionné et usage de tokens

**Points importants:**
- Chaque row traitée par AI coûte des crédits, peu importe la qualité du résultat
- Auto-Update activé déclenche des enrichissements = crédits consommés
- Duplicate enrichments (re-run ou re-enable columns) = nouveaux crédits
- **Recherches échouées coûtent aussi** - tu paies pour la tentative, pas le résultat

### Ce qui est GRATUIT

**Prospection & List Building:**
- Prospecting ne coûte pas de crédits - seulement l'enrichissement
- Google Maps, GitHub, CRM imports, web scraping sources = gratuit

**Utiliser tes propres API Keys:**
- Si tu as ta propre clé API (ex: OpenAI), connecte-la et utilise gratuitement
- Sources externes (Zoominfo, Cognism, 6Sense) via HTTP/API = gratuit
- Plans externes existants avec un provider = utilisables gratuitement dans Clay

**Actions Clay internes:**
- Formulas (toutes manipulations de données)
- Cleaning/formatting data
- CRM connections (sur Pro Plan!)
- Emailer connections (sur Pro Plan!)

### Tips pour économiser des crédits

1. **Désactiver Auto-Update** quand pas nécessaire
2. **Pause/supprimer AI columns** qui ne produisent pas de bons résultats
3. **Vérifier les settings** avant de re-run des enrichissements
4. **Utiliser "Lookup"** si les données existent déjà dans une autre table Clay ou CRM
5. **Custom budgets** pour contrôler les dépenses par run
6. **Ne pas supprimer** colonnes/tables pendant que des actions tournent

### Rollover Policy

**Plans mensuels:**
- Les crédits non utilisés se cumulent
- Maximum: 2× ta limite mensuelle (ex: 50K/mois → max 100K)

**Plans annuels:**
- 15% rollover des crédits non utilisés
- Condition: renouveler sur le même plan ou supérieur

---

## 17. PLANS & PRICING

### Free Plan
- **Prix:** Gratuit
- **Crédits:** 100/mois
- **Usage:** Test de la plateforme, petites explorations

### Starter Plan
- **Prix:** $149/mois ($134/mois en annuel)
- **Crédits:** 2,000/mois (24K-36K/an)
- **Features:**
  - Jusqu'à 5,000 recherches people/company
  - Phone number enrichments
  - Utiliser ses propres API keys

### Explorer Plan
- **Prix:** $349/mois ($314/mois en annuel)
- **Crédits:** 10,000/mois (120K-240K/an)
- **Features (tout de Starter +):**
  - Jusqu'à 10,000 recherches
  - HTTP API integration
  - Webhooks Clay
  - Email sequencing integrations (Outreach, Salesloft)

### Pro Plan
- **Prix:** $800/mois ($720/mois en annuel)
- **Crédits:** 50,000/mois (600K-1.8M/an)
- **Features (tout d'Explorer +):**
  - CRM integrations (Salesforce, HubSpot)
  - Coût par crédit jusqu'à 7x moins cher que Starter
  - CRM connections gratuites
  - Emailer connections gratuites

### Enterprise Plan
- **Prix:** Custom (médiane ~$30,400/an, jusqu'à $154,000/an)
- **Crédits:** Personnalisables
- **Features (tout de Pro +):**
  - Passthrough Tables (rows illimitées)
  - Jusqu'à 40 column actions par table
  - AI prompting support dédié
  - Snowflake integration
  - Slack support dédié
  - Credit reporting analytics
  - SSO

### Coût par crédit par plan
- Starter: ~$75 / 1,000 crédits
- Pro: ~$16 / 1,000 crédits (jusqu'à 7x moins cher)

---

## 18. FORMULAS - GUIDE COMPLET

### Clayscript
Les formulas Clay utilisent **Clayscript**, un langage basé sur JavaScript qui évalue des expressions row par row.

### Bibliothèques supportées

**JavaScript standard:**
- Math, String, Array, Date, RegExp, Number, Object

**Lodash:**
- Accès complet via `_` pour manipulation de données avancée

**Moment.js:**
- Opérations date/time via `moment`

**FormulaJS:**
- Fonctions spreadsheet familières: VLOOKUP, IF, SUM, CONCATENATE, etc.

### Syntaxe de référence

**Mode Describe:** Utiliser `/field` pour référencer les colonnes
**Mode Raw formula:** Utiliser `{{FieldName}}`

### AI Formula Generator

**Comment l'utiliser:**
1. Ajouter une nouvelle colonne → sélectionner Formula
2. Taper les instructions dans la box AI Formula Generator
3. Utiliser "/" pour référencer les colonnes
4. Cliquer "Generate Formula"
5. Vérifier le sample output
6. Cliquer "Save Formula"

### 3 Use Cases principaux

1. **Conditional Formula:** Exécuter si une condition est vraie
2. **Formatting Data:** Mettre en forme les données
3. **Cleaning Data:** Nettoyer les données

### Tips importants

- Remplacer les smart quotes " " par des straight quotes ""
- Les noms de colonnes doivent correspondre exactement
- Ajouter `|| ""` pour éviter les erreurs sur null
- Pas de définition de fonctions ou variables custom supportée

---

## 19. CLAYGENT - GUIDE COMPLET

### Qu'est-ce que Claygent?

Agent AI de recherche qui combine Google Search, ChatGPT, et web scraping en un seul outil. Il navigue le web, trouve des données publiques, et rapporte les résultats.

### Comment y accéder

1. Ouvrir une table
2. Aller dans le panneau Enrichment (droite)
3. Sélectionner "Claygent" sous la section AI

### Options de modèles

- **Claygent Neon:** Flagship de Clay, optimisé pour extraction/formatting en colonnes
- **GPT-4:** Pour raisonnement plus profond
- **Claude Opus:** Pour raisonnement plus profond

### Coût en crédits
- Questions simples (yes/no): 1 crédit
- Analyses plus profondes: 2-3 crédits

### Output Formatting
Formats disponibles: text, number, URL, true/false, custom

### Exemple de prompt
```
Visit this company's homepage. Does it offer a free trial?
Return 'Yes' if they mention free trial, demo, or trial period.
```

### Best Practices

**Quand utiliser Claygent:**
- Les données n'existent pas dans les databases
- Besoin de contexte en temps réel
- Information très spécifique/nuancée

**Tips:**
- Demander à Claygent de spécifier la source de l'info
- Préciser la plateforme source (Google, LinkedIn) dans le prompt
- Utiliser les templates built-in pour les tâches communes
- Itérer sans dépenser de crédits dans le builder

---

## 20. WATERFALL ENRICHMENT - GUIDE DÉTAILLÉ

### Setup Step-by-Step

**1. Ajouter l'enrichissement**
- Cliquer "Add enrichment"
- Chercher "Work Email" (ou autre)

**2. Configurer la séquence**
- Sous Waterfalls, sélectionner le waterfall
- Réordonner, ajouter, ou supprimer les providers
- Toggle switch pour skip un provider spécifique

**3. Sélectionner les colonnes input**
- Input principal: Company Domain
- Idéal: Personal Social Profile URLs (améliore la précision)
- Fallback: Full Name + Company Name ou Full Name + Personal Email

**4. Choisir les settings de validation**
- Default: ZeroBounce
- Autres validateurs disponibles

**5. Comment ça fonctionne**
- Clay passe dynamiquement à travers le waterfall
- Si un provider trouve un email valide → stop
- Si aucun email trouvé → crédits refundés, passe au provider suivant
- Continue jusqu'à email trouvé ou tous providers épuisés

### Conditional Runs (économiser des crédits)

1. Ajouter un nouvel enrichissement
2. Cliquer "Run Settings" → "Conditional Run"
3. Utiliser l'AI pour générer une formule
4. Exemple: "Only run if existing email field is blank"

---

## 21. CHROME EXTENSION

### Deux extensions disponibles

**1. Clay for Chrome (principale)**
- Extraire des données structurées des pages web
- Capturer: single page, listes multi-pages, structures custom
- Export: vers Clay table, CSV, ou clipboard

**2. Clip to Clay**
- Sauvegarder des pages entières vers tes tables Clay

### Features principales

**Auto-Detected Lists:**
- Ouvrir l'extension sur une liste
- Vérifier si auto-détectée
- Ajouter à Clay en un clic

**Map Your Own Lists:**
- Si pas détecté automatiquement
- Cliquer sur 2 items dans la liste
- Le selector apparaît automatiquement
- Choisir les attributs (nom, location, etc.)
- Preview des données scrapées
- Sauvegarder la recipe

**Map Page Recipes:**
- Créer des templates pour pages similaires
- Extraire les attributs avec juste une URL
- Éviter le copy-paste manuel

### Use Cases
- Directories d'agences
- Pages concurrents
- Case studies
- Listes de participants à des conférences
- Experts directories

---

## 22. VIEWS, FILTERS & SORTING

### Views

Les Views sont des combinaisons sauvegardées de filtres, tris, et customisations de colonnes.

**Gérer les Views:**
- Switch: dropdown menu en haut de la table
- Add New View: même dropdown
- Duplicate: copier une view existante
- Delete: supprimer les views inutiles

### Filters

**Comment ajouter:**
1. Cliquer le bouton Filters
2. Sélectionner "+ Add filter"
3. Choisir: colonne, opérateur, valeur

**Filter Groups (AND/OR Logic):**
- AND: toutes les conditions doivent être vraies
- OR: au moins une condition vraie
- Jusqu'à 2 niveaux de profondeur

**Types de filtres:**
- Text/numbers: "equal to", "not equal to", "is empty", "is not empty"
- Boolean: true/false filtering

### Sorting

**Comment trier:**
1. Dropdown sort
2. Sélectionner la colonne
3. Ascending (A→Z, petit→grand) ou Descending (Z→A, grand→petit)

### Column Management

**Show/Hide:**
- Bouton Columns → toggle chaque colonne
- "Show all columns" / "Hide all columns"

**Rearranging:**
- Menu Columns → drag & drop l'icône reorder

---

## 23. RUN SETTINGS & CONDITIONAL RUNS

### Qu'est-ce que les Conditional Runs?

Exécuter des actions/enrichissements uniquement si certaines conditions sont remplies.

### Comment y accéder

1. Ajouter un enrichissement
2. Dans le side panel, trouver "Run Settings"
3. Trouver la box "Only run if"
4. Utiliser "Use AI" ou écrire manuellement

### Utiliser l'AI Assistant

1. Cliquer "Use AI"
2. Taper la condition en langage naturel
3. Utiliser "/" pour référencer les colonnes
4. Cliquer "Generate Formula"

**Exemple:** "Only run if /headcount is greater than 40"

### Opérateurs logiques

- **AND:** Toutes les conditions doivent être vraies
- **OR:** Au moins une condition vraie
- **NOT:** Inverse une condition (ex: `NOT {{status}} == "Closed"`)

### Use Cases communs

- Upload to CRM only if valid email
- Ajouter à sequence si lead_score > 80 AND industry == "SaaS"
- Run personal email waterfall only if work email not found

### Vérifier le statut d'une colonne

```javascript
Clay.getCellStatus(#{{field_id}}) == "completed" AND {{previous_column}} == ""
```

---

## 24. CRM SYNC - HUBSPOT & SALESFORCE

### HubSpot Actions

**Lookup (read-only):**
- Pull data FROM HubSpot INTO Clay
- Ne modifie rien dans ton CRM
- Expérimenter librement sans risque

**Create & Update (write):**
- Push data FROM Clay TO HubSpot
- Modifications réelles et permanentes
- Être plus prudent et méthodique

### Setup HubSpot
1. Cliquer "Import"
2. Sélectionner "HubSpot"
3. Authentifier ton compte
4. Permissions accordées automatiquement

### Setup Salesforce
1. Naviguer vers import action
2. Sélectionner Salesforce
3. Login et accorder les permissions
4. Choisir: liste ou static report
5. **Note:** Reports limités à 2,000 records

### Best Practices
- Matcher par HubSpot ID
- Utiliser "ignore blank values" pour protéger les champs clean
- Automatiser via API connections pour sync continue

---

## 25. AUTO-UPDATE & AUTO-DEDUPE - DÉTAILS

### Auto-Update

**Activer:**
- Cliquer le nom de la table → settings
- Enable/Disable auto-update

**Contrôle niveau colonne:**
- Cliquer le nom de la colonne → Edit column
- Toggle auto-update on/off sous Run settings
- Sauvegarder

**Interaction Table/Colonne:**
| Table | Colonne | Résultat |
|-------|---------|----------|
| OFF | Any | Rien ne tourne automatiquement |
| ON | OFF | Cette colonne ne tourne pas auto |
| ON | ON | La colonne tourne automatiquement |

### Auto-Dedupe

**Activer:**
1. Cliquer l'icône Auto-dedupe (bas droite de la table)
2. Sélectionner "Enable automatic deduplication"
3. Choisir la colonne pour dedupe
4. Sauvegarder

**Avantages:**
- Données propres (supprime les doublons)
- Économie de crédits (pas d'enrichissement double)

**Limitation importante:**
- Garde uniquement la row la plus ancienne
- Supprime automatiquement les entries plus récentes
- Pas de setting pour garder la plus récente

**Dedupe manuel:**
- Right-click colonne → Dedupe → Delete Duplicate Row

---

## 26. DATA TYPES & COLUMNS

### Types de données disponibles
- Text
- Number
- Date
- Text with tokens (default)
- Message drafting
- Enrichment waterfall
- Formula

### Changer le data type

**Méthode 1:**
Right-click header → Edit Column → Select Data Type → Save

**Méthode 2:**
Cliquer titre colonne → hover sur le type actuel → dropdown → sélectionner

### Limites importantes

- **8,000 caractères par cell** maximum
- **70 colonnes par table** maximum
- **30 action/integration columns** maximum (40 avec waterfall)

### Tips colonnes

- **Couleurs:** Grouper les colonnes liées par couleur (ex: tout email en bleu)
- **Deduplication:** Case-sensitive ("Clay" ≠ "clay"), whitespace compte ("Clay " ≠ "Clay")
- **Child columns:** Créer des colonnes enfants pour mapper des endpoints spécifiques d'enrichissement

---

## 27. TEMPLATES

### Créer une table depuis un template

1. +Create New → Table → Use Template
2. Choisir le template
3. Cliquer "Add to Workspace"

**Note:** Les tables créées deviennent indépendantes du template original.

### Sauvegarder ton propre template

**Usage personnel:**
1. Dupliquer ta table
2. Déplacer vers un workbook séparé
3. Ajouter "[Template Do Not Delete]" au titre

**Pour partager:**
1. Actions → Share as template
2. Turn on sharing
3. Crée un template public (structure + 1 row seulement)

### Column Group Templates

1. Dans une table, cliquer "Add enrichment"
2. Sélectionner "Templates"
3. Chercher ton template

### Sauvegarder des templates

- **AI prompts:** Save custom prompts comme templates dans "Use AI"
- **Group columns:** Sélectionner plusieurs colonnes → "Save as Template"
- **Waterfall sequences:** Build custom waterfalls → save as template

---

## 28. EXPERT TIPS - ERIC NOSKI (Plus gros utilisateur Clay: 37M rows/semaine)

*Source: Eric Noski - Clay's earliest employee, runs the largest Clay usage (37M rows/week, 6M+ emails/month)*

### Les 6 Règles pour les Tables Clay

**Règle 1: Conditional Formula sur TOUTES les intégrations payantes**
- Même si c'est juste "first name must not be empty"
- Toujours prendre cette habitude pour éviter le gaspillage de crédits
- C'est non-négociable

**Règle 2: Utiliser les Functions (feature avancée)**
- Envoyer les données à une table séparée → run workflow → renvoyer les données
- Permet de changer un workflow une seule fois pour 15+ tables
- Évite de modifier chaque table individuellement

**Règle 3: Sauvegarder TOUTES les données payantes**
- Vers ton CRM ou une plateforme comme Supabase
- Supabase: $30/mois pour 11.4M+ records
- Clay ne sauvegarde pas tes données comme Apollo/ZoomInfo
- Tu vas réutiliser ces données, sauvegarde-les

**Règle 4: Utiliser les Scheduled Sources pour les campagnes evergreen**
- Mettre tout le TAM dans HubSpot ($15/mois)
- Créer un segment/liste active
- Laisser la campagne tourner automatiquement
- Plus de CSV manuels à uploader

**Règle 5: Ne pas utiliser l'AI quand les Formulas suffisent**
- Cleaning data → Formula
- Combining data → Formula
- If/then statements → Formula
- Scoring leads → Formula
- Abréviations (New Jersey → NJ) → Formula
- Tout ce que JavaScript peut faire = Formula

**Règle 6: Formulas = JavaScript**
- Si tu as besoin d'une formule complexe: screenshot → ChatGPT
- L'AI formula generator est puissant mais parfois ChatGPT fait mieux

---

## 29. RÈGLES DE PROMPTING AI - ERIC NOSKI

### Règle 1: La règle des 10 minutes de recherche manuelle
- Demande-toi: "Qu'est-ce que je ferais si je recherchais cette personne pendant 10 minutes?"
- Quelles informations je chercherais?
- PUIS automatise ça avec Clay
- Ne jamais deviner ce qu'on pourrait faire avec Clay

### Règle 2: L'AI ne fait qu'UNE SEULE chose à la fois
**Mauvais:**
- Claygent qui check le contenu du site + décide si e-commerce + classifie l'industrie

**Bon:**
- Claygent #1: Récupère le contenu du site
- Use AI #2: Est-ce un CPG?
- Use AI #3: Quels produits vendent-ils?
- Use AI #4: Quelle industrie?

L'AI "fart" si tu lui donnes trop de tâches. GPT-4 mini coûte presque rien, sépare les tâches.

### Règle 3: Safeguards quand il n'y a pas assez de contexte
- Utiliser un mot-clé comme **"purple"** quand rien n'est trouvé
- "Si pas de case study trouvée, output 'purple'"
- Facilite le filtrage downstream
- L'AI va sinon dire "No information found" de 100 façons différentes

### Règle 4: TOUJOURS utiliser des exemples dans les prompts
- Même un prompt moyen devient excellent avec des exemples
- Recherche manuellement 3-4 exemples
- Les inclure dans le prompt
- Montre à l'AI exactement ce que tu veux

### Règle 5: Utiliser le Metaprompter
1. Va sur ChatGPT
2. Explique ce que tu veux accomplir
3. Demande: "Crée un prompt pour ça"
4. Puis demande: **"Quelles questions as-tu pour améliorer ce prompt?"**
5. Réponds aux questions
6. Prompt amélioré

### Règle 6: Pour les prompts difficiles (classification industrie), demander le raisonnement AVANT la réponse
- "Tell me the reasoning why you think it's this kind of company before you give me the final answer"
- L'AI prédit le mot suivant
- En expliquant d'abord, elle a le temps de mieux répondre

### Règle 7: Préparation aux edge cases
- 20% = mettre les intégrations ensemble
- **80% = ajuster l'AI**
- La plupart échouent parce qu'ils pensent l'inverse
- Review constamment, dès qu'un output ne plaît pas → ajuster le prompt

### Règle 8: Utiliser GPT-4 mini pour TOUT
- Les modèles avancés sont benchmarkés pour résoudre du calcul
- Tu veux juste dire "I saw on your website you help fitness enthusiasts breathe better"
- GPT-4 mini gère ça parfaitement
- Fix everything with prompts, pas avec des modèles plus chers

---

## 30. COLD EMAIL MASTERY - 25 LEÇONS (10M+ emails envoyés)

*Source: Growth Engine X - 1.5-2M emails/mois pour 40-50 clients*

### Infrastructure Email

**Volume par inbox:**
- 30 emails max par inbox
- Scale horizontalement (plus d'inboxes, pas plus de volume)

**Open rates cibles:**
- 40-60% = bon
- <30% = problème de délivrabilité
- Solution: nouveaux domaines, réchauffer 3 semaines, recommencer

**Ne pas perdre de temps:**
- Si <1% reply rate → pas besoin de seed tests ou Glock apps
- Résultat sera toujours: nouveaux domaines + nouvelle copy + restart

**Max 3 emails par séquence:**
- Email 1 = meilleure performance toujours
- Email 2 & 3 = diminishing returns
- Plus de 3 = tu énerves et te fais marquer spam

### Réutilisation du TAM

**Règle d'or:** Réutiliser ta liste tous les 3 mois
- Les gens ne se souviennent pas de ton email d'il y a 20 minutes
- Leurs priorités/business changent
- Calcule: combien d'emails/jour pour recycler le TAM en 3 mois

### Filtering & Golden ICP

**Le problème:**
- Director Marketing dans une banque de 20 personnes ≠ Director Marketing dans une banque de 500 personnes
- Les filtres génériques (20-500 employees) ne marchent pas

**Solution - Golden ICP:**
Empiler les signaux avec Clay:

| Niveau | Signal | Exemple |
|--------|--------|---------|
| 1 | Fondée récemment | < 2 ans |
| 2 | Funded | A levé des fonds |
| 3 | CEO first-time | Jamais été CEO avant |

**Waterfall les signaux:**
- Run le signal le plus important EN PREMIER
- Conditional formulas pour ne pas enrichir si signal #1 échoue
- Changer le messaging selon combien de signaux sont vrais

### Meilleurs Triggers

**2023: Recently Joined Company**
- "Hey congrats on the new role, as you're taking over..."
- Toujours fiable mais un peu usé maintenant

**2024: Social Signals (LE MEILLEUR)**
- LinkedIn posts
- Content engagement
- Posts sur certains keywords

*Exemple réel:* Offshore staffing company - le trigger "LinkedIn post" a battu tous les autres triggers "logiques" (nouveau, funded, international hiring, etc.)

### Framework des Emails

**Email 1: Introduction de l'offre**
```
Ligne 1: Why you, why now (pourquoi je te contacte maintenant)
Ligne 2: Ton offre clairement expliquée (court!)
Ligne 3: Social proof (tu n'es pas leur premier client)
Ligne 4: CTA (Would you want to chat next Thursday?)
```

**Email 2: Ajouter le contexte**
- Tout ce que tu as dû supprimer de l'email 1
- C'est threadé, ils peuvent scroller pour voir email 1
- Toujours court mais plus de détails

**Email 3: Baisser la friction**
- Ils n'ont pas répondu 2 fois → ils ne sont pas convaincus
- Lead magnet gratuit
- Custom Loom audit
- Autre call to action moins engageant

**Délai entre emails:** 3-5 jours (1 jour = trop court)

### Breakup Emails = STOP

**Ce qui ne marche pas:**
- "You must be getting chased by an alligator..."
- Mendier une réponse

**Ce qui marche:**
- "Am I reaching the right person?"
- "Is there someone else in the company who handles this?"
- Bonus Clay: nommer d'autres personnes du département automatiquement

### Changer les Value Props

**Entre les emails:**
- Email 1: Save money
- Email 2: Make money
- Email 3: Save time

**Le "So What":**
- "We help you save 3 hours/month" → pas assez
- "We help you save 3 hours/month so your SDRs can spend more time actually selling" → MIEUX

### Utiliser l'AI Correctement

**Show your work:**
- Mauvais: "I see you get 50,000 visitors/month"
- Bon: "According to SimilarWeb, you get 50,000 visitors/month"
- Si c'est faux, c'est SimilarWeb qui est faux, pas toi

**Case studies du client:**
- Claygent peut scraper les case studies de leur site
- "I noticed you worked with Intercom and helped them with XYZ"
- PS line: "Even if we never connect, saw the case study... really impressive, kudos"

**Ne pas faire écrire tout l'email par l'AI:**
- Contrôler le messaging pour split-tester
- Utiliser l'AI pour UNE partie spécifique
- Le reste = static text

### Small TAM Strategy (<20,000 personnes)

**Omni-channel (vraiment):**
1. Cold email tout le monde
2. Cold call tout le monde
3. LinkedIn message tout le monde
4. Direct mail le reste

**PAS de threading complexe:**
- Email jour 1 → Call jour 3 → DM jour 5 = trop de stress
- Faire un channel à la fois, exhaustivement
- Même résultats, moins de complexity

---

## 31. BEGINNER WORKFLOW - STEP BY STEP

*Source: Matt - Agency owner, 100K+ cold emails/month*

### Le Workflow Complet

```
1. IMPORT DATA
   ↓
2. ENRICH MISSING EMAILS (waterfall ou single provider)
   ↓
3. MERGE COLUMNS
   ↓
4. VALIDATE EMAILS
   ↓
5. GET COMPANY SUMMARY (cheap AI)
   ↓
6. CHECK IF FIT (better AI)
   ↓
7. PUSH TO SEQUENCER
```

### Étape 1: Importer les données

**Options:**
- CSV upload
- HubSpot/Salesforce sync
- Apollo integration
- Clay's native "Find People"

**Note:** Les données externes (Apollo) sont souvent de meilleure qualité que Clay native

### Étape 2: Enrichir les emails manquants

**Waterfall intégré:**
- Add enrichment → Work Email Waterfall
- Multiple providers: LeadMagic, Prospeo, etc.
- S'arrête dès qu'un email est trouvé

**Provider externe (économie):**
- Utiliser sa propre clé API
- Connecter Prospeo directement
- Économise des Clay credits

### Étape 3: Merge columns

- Fusionner les emails de différentes sources
- Une colonne "Email Final" propre

### Étape 4: Valider les emails

**Providers natifs Clay:**
- Debounce, Enrichly, Hunter, LeadMagic, NeverBounce

**Via API (recommandé pour catchalls):**
- ListKit/Listman.io = valide les catchalls avec précision
- Configurer un HTTP API call

**CRITIQUE - Conditional Formula:**
```
Only run if /work_email is not empty
```
→ Ne pas gaspiller de crédits sur des cells vides

### Étape 5: Company Summary (AI cheap)

**Modèle:** GPT-4 mini (0.00126$/call)

**Prompt:**
```
I want you to visit this website /company_domain and give me
an exhaustive summary of what the company does in as many
paragraphs as possible.
```

**Pourquoi séparer:**
1. Réutilisable pour d'autres prompts
2. Modèle cheap pour le scraping intensif
3. Modèle smart pour l'interprétation

**Conditional Formula:**
```
Only run if /listkit_results equals "valid" OR "catchall valid"
```

### Étape 6: Check Fit (AI smart)

**Modèle:** Claude 3.5 Sonnet (meilleure interprétation)

**Prompt:**
```
I'm going to feed you a company description and I want you
to tell me if the company is a B2B company or a B2C company.

If they are a B2B company then output "B2B"
If they are a B2C company then output "B2C"

Only output B2B or B2C, nothing else.

Here is the company summary: /company_summary
```

**IMPORTANT:** "Only output X or Y, nothing else"
- Facilite le filtrage
- Pas de paragraphes de justification

**Conditional Formula:**
```
Only run if /company_summary exists
```

### Étape 7: Push to Sequencer

**Intégrations natives:**
- SmartLead
- Instantly
- Autres via API

**Conditional Formula:**
```
Only run if /company_type equals "B2B"
```

**Mapping:**
- First name, Last name, Email
- Company domain, LinkedIn profile
- Custom fields

### Best Practices du Workflow

**Toujours tester petit:**
- Run 10 rows d'abord
- Vérifier les outputs
- Puis run all

**Économiser les crédits:**
- AI cheap (GPT-4 mini) pour le scraping
- AI smart (Claude) pour l'interprétation
- Conditional formulas partout

**Erreurs courantes:**
- Oublier de feed les données au prompt (ex: /company_summary)
- Run avant de vérifier la conditional formula
- Utiliser AI expensive pour tout

---

## 32. QUICK REFERENCE - COMMANDES UTILES

### Conditional Formulas Communes

```javascript
// Email existe
/email is not empty

// Email valide ou catchall valide
/validation_result equals "valid" OR equals "catchall valid"

// Company type match
/company_type equals "B2B"

// Score minimum
/lead_score is greater than 50

// Combiné
/email is not empty AND /company_fit equals "true"
```

### Prompts Templates

**Company Summary:**
```
Visit /company_domain and give me an exhaustive summary
of what the company does.
```

**Fit Check:**
```
Based on this summary: /company_summary
Is this company a [TYPE]?
Output "true" if yes, "false" if no.
Only output true or false, nothing else.
```

**LinkedIn Post Summary:**
```
Here is a LinkedIn post: /linkedin_post
Summarize what they're talking about in one sentence.
If it's about politics, religion, or controversial topics,
output "SKIP".
```

**Case Study Extraction:**
```
Visit /company_domain/case-studies and find their customer
case studies. For each case study, extract:
- Customer name
- What they helped them achieve
- Any metrics mentioned

If no case studies found, output "purple".
```

---

---

## 33. CLAY POSITIONING - POURQUOI LE HYPE?

*Source: Patrick - The Kiln, Clay Agency ($1.2B valuation, ~$100M raised)*

### Ce que Clay remplace vraiment

**Avant Clay - 2 options seulement:**

1. **Outreach templated à grande échelle:**
   - "Hi {{first_name}}, I wanted to reach out to {{company_name}}..."
   - Emails ignorés immédiatement
   - Aucune personnalisation réelle

2. **Légion de SDRs/BDRs:**
   - Recherche manuelle sur chaque prospect
   - LinkedIn, 10-K, Google
   - Coûteux, lent, non-scalable

**Avec Clay:**
- 2-3 SDRs peuvent envoyer **100,000 emails/mois**
- Chaque email = hyper-personnalisé, recherché, pertinent
- Semble écrit par un humain
- Échelle d'une Fortune 500 avec une équipe de startup

### Clay = Data Intermediary

```
[INBOUND]                    [CLAY]                    [OUTPUT]
LinkedIn Ads      →          ┌─────────┐              → HubSpot
Organic Content   →          │ Enrichir│              → Salesforce
Newsletter        →          │ Scorer  │              → SmartLead
Webinars          →          │ Nettoyer│              → Instantly
Events            →          │ Qualifier              → Outreach
CRM Stale Data    →          └─────────┘              → Salesloft
```

**Principe clé:** Données entrent → Transformation dans Clay → Données sortent vers autre outil

**Ce que Clay N'EST PAS:**
- Pas un remplacement CRM (HubSpot/Salesforce)
- Pas un remplacement email finder (ZoomInfo/Apollo)
- C'est une **couche complémentaire** qui maximise tous les outils

---

## 34. SOURCES DE LEADS - GUIDE COMPLET

### 3 Catégories de Leads

**1. Inbound Leads (Marketing Initiatives)**
- LinkedIn Ads responses
- Organic LinkedIn engagement
- Newsletter subscribers
- Form fills on website
- Webinar attendees
- In-person event attendees

**2. Warm/High Intent Leads**
- LinkedIn post engagers (via Triggery)
- Website visitors (via RB2B, Clearbit, etc.)
- Slack community joiners
- Reddit threads mentioning your product
- Product trial signups

**3. Cold Outreach Lists**
- Build directly in Clay
- Import from Apollo, ZoomInfo, Sales Navigator
- Scrape from Google Maps (local businesses)

### Find People (GRATUIT dans Clay)

1. New → Table → Find People
2. Filters disponibles:
   - Job Titles (founder, CEO, VP Sales...)
   - Location (New York City, France...)
   - Keywords in profile
   - Min connections/followers
   - Certifications
   - Past experiences

**Note:** Logo générique = scraping LinkedIn (gratuit)

### Sources Avancées

| Source | Use Case | Coût |
|--------|----------|------|
| Find People | ICP list building | Gratuit |
| Find Companies | Company lists | Gratuit |
| HG Insights | Tech stack | Payant |
| Google Maps | Local businesses | Gratuit |
| Social Media | Influencers | Variable |
| RSS Feeds | Content monitoring | Gratuit |
| Apify/PhantomBuster | Custom scraping | Variable |
| Webhooks | Live data streams | Gratuit |

### Webhooks - Live Data

**Use case:** Triggery → Clay (LinkedIn engagement)
- Quelqu'un like/commente ton post LinkedIn
- Webhook envoie les données à Clay en temps réel
- Clay enrichit et route automatiquement

---

## 35. ENRICHISSEMENT - NIVEAU AVANCÉ

### Le Crédit System Expliqué

**Comment ça fonctionne:**
- Clay = marketplace d'enrichment providers
- Tu paies en Clay Credits
- Clay paie les providers pour toi
- Pas besoin de contrats individuels

**Avantages:**
1. Accès à des outils enterprise (HG Insights = $100K+/an normalement)
2. Pas de signup pour chaque provider
3. Waterfall = max couverture au min coût

### Waterfall Deep Dive

**Exemple Find Work Email (Enterprise Waterfall):**

```
Provider 1: LeadMagic (2 credits) → Found? STOP
     ↓ Not found
Provider 2: Prospeo (2 credits) → Found? STOP
     ↓ Not found
Provider 3: Hunter (2 credits) → Found? STOP
     ↓ Not found
Provider 4: Apollo (3 credits) → Found? STOP
     ↓ Not found
Provider 5: RocketReach (3 credits) → Found? STOP
     ↓ Not found
Provider 6: FindyMail (2 credits) → STOP (pas d'email trouvé)
```

**Coût si trouvé au Provider 4:** 2+2+2+3 = 9 credits (pas 14)

**Key insight:** Tu paies seulement les providers utilisés, pas tous

### AI Enrichment avec Claygent

**Deux approches:**

**1. Prompt direct:**
```
Find me the contact page URL for /company_domain
```

**2. AI-generated prompt:**
- Décris ce que tu veux en français
- Clay génère le prompt optimisé
- Utilise les colonnes de ta table automatiquement

**Output formatting:**
- URL (pour les liens)
- Text (pour les descriptions)
- Number (pour les chiffres)
- True/False (pour les yes/no)

---

## 36. CAMPAIGN PLAYBOOKS - THE KILN

*Source: The Kiln Gitbook - Clay Agency*

### 1. AI Personalized Video Campaign (Sendspark)

**Concept:**
- Vidéo AI qui dit "Hi {{first_name}}"
- Background = scroll du site web du prospect
- Reste de la vidéo = templatized

**Setup:**
1. Clay enrichit les données prospect
2. Sendspark génère la vidéo custom
3. HTTP API connecte les deux
4. Push vers sequencer

### 2. DynaPictures - Custom Images

**Exemple CVS Campaign:**
- Client vend pub dans les CVS
- Scrape les Facebook/Google Ads des prospects
- Layer leur ad sur une image du mini-billboard CVS
- Envoie l'image personnalisée par email

**Setup:**
1. Ad library scraping → Clay
2. DynaPictures API (HTTP API action)
3. Génération image custom par prospect
4. Push vers campaign

### 3. Lookalike Campaigns

**Types:**
- Lookalikes de closed-won clients
- Lookalikes de positive responders
- Lookalikes de newsletter engagers

**Comment:**
1. Import tes best customers dans Clay
2. Enrichis pour trouver les patterns communs
3. Utilise ces critères pour build des listes similaires
4. Outreach avec messaging "companies like yours..."

### 4. LinkedIn Follower Campaign (Battle Cards)

**Concept:**
- Scrape les followers d'un competitor (via ScrapeApp)
- Import dans Clay
- Crée des battle cards (ton produit vs competitor)
- Outreach personnalisé

**Exemple:**
```
Hey {{first_name}},

I noticed you follow {{competitor_name}} on LinkedIn.

Here are 3 reasons why companies switch from {{competitor}} to us:
1. [Downside 1 of competitor]
2. [Downside 2]
3. [Downside 3]

Would you be open to a quick comparison call?
```

### 5. Job Opening Intent Signal

**Signal:** Company hiring for specific role = need for your solution

**Workflow:**
1. Monitor job postings (via LinkedIn, Indeed scraping)
2. Filter by relevant roles
3. Find decision makers
4. Outreach: "I saw you're hiring for X, companies in this phase usually need Y..."

### 6. Ad Library Scraping Campaign

**Platforms:**
- Facebook Ad Library
- Google Ads transparency
- LinkedIn Ad Library

**Use cases:**
- Reference their current ads in outreach
- Use their ad creative in custom images
- Analyze their messaging for personalization

---

## 37. OUTBOUND EXAMPLE - CLICKUP BRAIN CAMPAIGN

*Case study détaillé d'une vraie campagne*

### Context
- Product: ClickUp Brain (AI workspace)
- Target: Fortune 500 managers (product, project, senior managers)
- Goal: Bottom-up adoption → Enterprise upsell

### Clay Table Structure

**Table 1: Fortune 500 Companies**
| Colonne | Source | But |
|---------|--------|-----|
| Company Name | Import | Base |
| LinkedIn URL | Enrich Company | Matching |
| Headcount Growth YoY | Enrichment | Intent signal #1 |
| +10% Growth? | Formula (checkbox) | Filtering |
| Recent News | Find Recent News | Intent signal #2 |
| Acquisition? | Formula (checkbox) | Filtering |
| Contact Page URL | Claygent | Backup data |
| Fundraising Data | Enrichment | Context |

**Table 2: People at Fortune 500**
| Colonne | Source | But |
|---------|--------|-----|
| Person Name | Find People | Contact |
| Job Title | Find People | Targeting |
| Department | AI Classification | Personalization |
| LinkedIn Profile | Enrich Person | Data |
| Example Docs | AI Generation | Personalization |
| Custom Use Cases | AI (ClickUp features + company context) | Email copy |
| Work Email | Waterfall | Outreach |
| Custom First Line | AI (based on intent signals) | Email copy |

### Email Copy Structure

```
FIRST LINE (intent-based):
- If +10% growth: "Congrats on {{company}}'s recent growth..."
- If acquisition: "I saw {{company}} recently acquired {{acquired_company}}..."
- Else: Generic but personalized line

VALUE PROP:
"Have you ever wished you could create a bot out of {{company}}'s
{{department}} docs and ask a question whenever you had one?"

USE CASES:
"For example, at {{company}} you could use ClickUp Brain to:
{{custom_use_cases_based_on_their_docs}}"

SOCIAL PROOF + CTA
```

### Key Takeaways

1. **Multi-signal intent:** Stack headcount growth + acquisition news
2. **Department-based personalization:** Different docs for different roles
3. **AI-generated use cases:** Based on company description + ClickUp features
4. **Formula-based email assembly:** Merge all pieces proprement

---

## 38. INBOUND EXAMPLE - TRIGGERY + GOOGLE REVIEWS

*Case study: Local business outreach from LinkedIn engagement*

### Workflow Overview

```
LinkedIn Post Engagement (Triggery webhook)
          ↓
    Clay Table
          ↓
    Enrich Company
          ↓
    Match to Service Offering
          ↓
    Find Google Reviews
          ↓
    Extract Reviewer Name + Review Content
          ↓
    Generate Custom Message
          ↓
    Push to SmartLead
```

### Table Structure

| Colonne | Source | But |
|---------|--------|-----|
| First Name | Webhook (Triggery) | Personalization |
| Last Name | Webhook | Personalization |
| Engagement Type | Webhook | Context (like/comment) |
| Post URL | Webhook | Reference |
| Post Summary | AI (LinkedIn scrape) | Context |
| Company | Enrich | Matching |
| Industry | Enrich | Case study matching |
| Matched Service | Formula | Which offering to pitch |
| Industry Case Study | Formula (industry → case study) | Social proof |
| Google Review | Claygent (Google Maps) | Deep personalization |
| Reviewer Name | AI Extract | Personalization |
| How Company Helped Reviewer | AI Summary | Email content |
| Work Email | Waterfall | Outreach |
| Final Message | Formula/AI | Campaign |

### Email Example

```
Hey {{first_name}},

Saw you engaged with our post about {{post_summary}}.

I noticed on Google that {{reviewer_name}} left a great review
about how {{company}} helped them with {{review_summary}}.

We help {{industry}} companies like yours with exactly that.
For example, {{matched_case_study}}.

Would you be open to a quick chat?
```

### Power Moves

1. **Reviewer name in email** = Proves you actually researched
2. **Industry-specific case study** = Relevant social proof
3. **Post reference** = Warm intro (they engaged first)
4. **Local business focus** = Google Maps data where LinkedIn fails

---

## 39. CRM ENRICHMENT EXAMPLE - SALESFORCE CLEANUP

*30,000 records enriched and cleaned*

### Problem
- 30K Salesforce records
- Only: Company Name, Billing State, Company Owner
- No website, no LinkedIn, no revenue, no contacts

### Solution Workflow

```
Salesforce Import (30K records)
          ↓
    Google Search: "[Company Name] LinkedIn"
          ↓
    Extract LinkedIn Company URL
          ↓
    Enrich Company from LinkedIn
          ↓
    Find Company Domain
          ↓
    Revenue Waterfall
          ↓
    Find Marketing Contacts
          ↓
    Tech Stack (HG Insights)
          ↓
    Find Investors
          ↓
    Update Salesforce (push enriched data back)
```

### New Data Added

| Champ | Source | Value |
|-------|--------|-------|
| Company LinkedIn URL | Google Search | Matching |
| Description | LinkedIn Enrich | Context |
| Industry | LinkedIn Enrich | Segmentation |
| Location | LinkedIn Enrich | Routing |
| Employee Count | LinkedIn Enrich | Sizing |
| Revenue | Waterfall (PDL, HG, Clearbit) | Qualification |
| Marketing Leaders | Find People | Contacts |
| Tech Stack | HG Insights | Targeting |
| Investors | Enrichment | Context |

### Key Insight

**Clay comme couche de nettoyage CRM:**
- Import from Salesforce
- Enrich everything
- Push back to Salesforce
- Auto-refresh on schedule
- CRM always clean and complete

---

## 40. SEQUENCING TOOL RECOMMENDATIONS

### Email Sequencing (Automated Outbound)

| Tool | Best For | Volume |
|------|----------|--------|
| **SmartLead** | High volume, AI warmup | 1000s/day |
| **Instantly** | Ease of use, good deliverability | 1000s/day |
| **Lemlist** | Multi-channel, images | Medium |
| **Apollo** | All-in-one (data + sending) | Medium |

### LinkedIn Sequencing

| Tool | Best For |
|------|----------|
| **HeyReach** | Automated LinkedIn outreach |
| **Expandi** | LinkedIn automation |
| **Dripify** | LinkedIn sequences |

### Multi-Channel Sequencing

| Tool | Channels |
|------|----------|
| **LaGrowthMachine** | Email + LinkedIn + Twitter |
| **Lemlist** | Email + LinkedIn |
| **Reply.io** | Email + LinkedIn + Calls |

### Integration Pattern

```
Clay Table
    ↓
[Add to SmartLead Campaign]
    ↓
Map variables:
- first_name → {{First Name}}
- last_name → {{Last Name}}
- email → {{Work Email}}
- first_line → {{AI First Line}}
- company → {{Company Name}}
- custom_1 → {{Use Case}}
```

---

## 41. HTTP API - EXTERNAL TOOLS

### Quand utiliser HTTP API

- Tool sans intégration native Clay
- Custom API endpoints
- Tools avec ton propre API key

### Exemple: DynaPictures

**Setup:**
1. Créer compte HTTP API dans Clay
2. Copier API key de DynaPictures
3. Configurer l'endpoint

```
Method: POST
Endpoint: https://api.dynapictures.com/v1/images
Headers:
  - Authorization: Bearer {{DYNAPICTURES_API_KEY}}
  - Content-Type: application/json
Body:
{
  "template_id": "your_template",
  "modifications": {
    "company_logo": "{{Company Logo URL}}",
    "person_name": "{{First Name}}",
    "background_image": "{{Ad Creative URL}}"
  }
}
```

### Exemple: Zapier Webhook

**Use case:** Slack notification quand lead ajouté à sequence

```
Method: POST
Endpoint: https://hooks.zapier.com/hooks/catch/xxxxx/yyyyy/
Body:
{
  "lead_name": "{{Full Name}}",
  "company": "{{Company}}",
  "email": "{{Work Email}}",
  "added_to_campaign": "{{Campaign Name}}"
}
```

---

## 42. LEARNING CLAY - REALISTIC EXPECTATIONS

### La Courbe d'Apprentissage

**Jours 1-3:**
- Confusion sur les enrichments
- "Pourquoi ça ne marche pas comme dans les vidéos?"
- Beaucoup de squirming

**Semaines 1-2:**
- Comprendre les formulas
- Premiers workflows qui marchent
- Erreurs de crédits (oups)

**Mois 1:**
- Workflows solides
- Comprendre le waterfall
- Sauver des crédits avec conditional formulas

**Mois 2+:**
- Créativité débloquée
- Combiner les composants de façons nouvelles
- Vraie maîtrise

### Analogie Piano

> "Tu regardes quelqu'un jouer, ça a l'air facile. Tu essaies, ça semble impossible. Quelques semaines plus tard, t'es décent."

### Ressources Recommandées

1. **Clay University** (sur clay.com) - Officiel, gratuit, complet
2. **The Kiln Gitbook** - Playbooks et templates
3. **YouTube tutorials** - Visual learning
4. **Hands-on practice** - La seule vraie façon d'apprendre

### Tips pour Accélérer

1. **Start with templates** - Ne pas réinventer la roue
2. **Test sur 10 rows** - Avant de run 10,000
3. **Conditional formulas PARTOUT** - Économise tes crédits
4. **Un enrichment à la fois** - Debug plus facile
5. **Save tes prompts qui marchent** - Build ta library

---

*Document mis à jour avec les learnings de:*
- *Eric Noski (Clay's largest user)*
- *Growth Engine X (10M+ cold emails)*
- *Matt's Agency (100K+ cold emails/month)*
- *Patrick - The Kiln (Clay Agency, tutorial 1h)*
