# Guide de dépouillement des contenus de manuscrits

## But du travail

Dans ce projet, vous transformerez des descriptions de manuscrits tirées de catalogues de bibliothèques en une liste structurée des textes contenus dans chaque manuscrit. Vous partirez de la table **« Contents listings for Bischoff Items »**, qui vous indique quel manuscrit examiner, dans quel catalogue il est décrit, et où trouver la notice. Vous enregistrerez ensuite les résultats dans la table **« Manuscript Contents »**.

La règle fondamentale est la suivante : **une ligne dans « Manuscript Contents » correspond à un texte, une oeuvre, ou une unité textuelle dans un manuscrit donné**. Si un manuscrit contient plusieurs items distincts, il faudra donc créer plusieurs lignes.

Il faut toujours privilégier la prudence. Les champs **« as catalogue »** servent à conserver le libellé du catalogue aussi fidèlement que possible ; les champs **« normalised »** ne doivent être remplis que si l’identification est raisonnablement sûre. En cas d’incertitude, il vaut mieux **laisser le champ vide** ou **poser une question à M. Pollard**, plutôt que de deviner. Le but n’est pas de reconstruire le manuscrit de manière spéculative, mais de produire des données fiables, explicites et réutilisables.

---

## Règles essentielles à retenir

- **Une ligne = un item textuel dans un manuscrit donné.**
- **Mieux vaut laisser vide que deviner.**
- **Mieux vaut poser une question que créer une fausse certitude.**
- Conservez le libellé du catalogue dans les champs `as catalogue`.
- Ne remplissez les champs `normalised` que si l’identification est sûre ou presque sûre.
- N’inventez jamais un auteur, un titre normalisé, un numéro `CPL`, `BHL` ou autre.
- Si la notice est confuse, faites simple et prudent.

---

## Aperçu du travail

Vous travaillerez à partir de deux tables Airtable :

### 1. `Contents listings for Bischoff Items`
Cette table sert de **point de départ**. Elle indique :

- quel manuscrit vous devez examiner ;
- dans quel catalogue il est décrit ;
- où trouver la notice ;
- parfois aussi une image ou un extrait du contenu.

### 2. `Manuscript Contents`
C’est la table où vous enregistrez les **items de contenu** trouvés dans les notices.

---

## Workflow général

## Étape 1 : repérer le bon manuscrit

Dans la table `Contents listings for Bischoff Items`, repérez le manuscrit à l’aide des champs suivants :

- `Archive Location`
- `Archive Name`
- `Shelfnumber`
- `Bischoff #`
- `Catalogue source URL`

Ouvrez ensuite la notice du catalogue.

## Étape 2 : lire la notice attentivement

Lisez la description complète du manuscrit.

Essayez d’identifier les différents **items distincts** qu’elle décrit :

- un texte ;
- un fragment ;
- un sermon ;
- une prière ;
- une série de sentences ;
- un glossaire ;
- des extraits ;
- etc.

## Étape 3 : créer une ligne par item

Dans `Manuscript Contents`, créez **une ligne par item**.

Si la notice décrit 10 items distincts, il faudra normalement créer 10 lignes.

---

## Comment décider ce qui constitue un item distinct ?

Créez une nouvelle ligne quand :

- le catalogue donne un **nouveau titre** ;
- le catalogue donne un **nouvel incipit** ;
- le catalogue change clairement d’**auteur** ou de **texte** ;
- la notice passe visiblement à une **autre pièce** ou à un **autre ensemble textuel**.

Ne créez **pas** artificiellement plusieurs lignes si :

- la notice reste vague ;
- le catalogue ne permet pas vraiment de séparer plusieurs textes ;
- vous devriez spéculer pour le faire.

> **Règle simple : on ne découpe que ce que la notice permet réellement de distinguer.**

---

## Champs à remplir

## A. Champs à remplir presque toujours

### `Bischoff Item`
Lien vers le manuscrit concerné.

### `Sequence in MS`
Ordre de l’item dans le manuscrit : `1`, `2`, `3`, `4`, etc.

### `Extent type`
Choisir la valeur qui convient le mieux :

- `Single item listed` : le catalogue ne donne qu’un seul item pour le manuscrit ;
- `Whole manuscript` : l’ensemble du manuscrit correspond manifestement à un seul texte ou une seule unité ;
- `Partial` : l’item n’occupe qu’une partie du manuscrit, parmi d’autres.

### `Work Name (as catalogue)`
Titre ou désignation du texte **tel que le catalogue le donne**, ou aussi près que possible de son libellé.

### `Source catalogue`
Le catalogue utilisé pour cette ligne.

---

## B. Champs à remplir si l’information est donnée

### `Author (as catalogue)`
L’auteur tel qu’il apparaît dans le catalogue.

### `Translator (as catalogue)`
Seulement si le catalogue en donne un.

### `Incipit`
Très utile surtout pour :

- les textes anonymes ;
- les titres vagues ;
- les fragments ;
- les notices du type « Incipit... ».

### `Folio/page start`
### `Folio/page end`
À remplir si la notice donne une localisation.

### `Work notes`
À utiliser pour :

- une précision utile du catalogue ;
- une hésitation ou un doute formulé dans la notice ;
- une remarque sur l’état du texte ;
- un commentaire bref qui ne rentre pas ailleurs.

---

## C. Champs à remplir seulement si l’identification est sûre

### `Author (normalised)`
Nom normalisé de l’auteur.

### `Translator (normalised)`
Seulement si l’identification est sûre.

### `Work (normalised)`
Titre normalisé moderne ou contrôlé.

### `CPL #`
### `BHL #`
### `In Principio #`
À remplir **uniquement** si vous êtes raisonnablement certain de l’identification.

> Si vous hésitez : **laissez vide**.

---

## Différence essentielle : `as catalogue` et `normalised`

Cette distinction est fondamentale.

### `as catalogue`
On y met ce que dit le catalogue, ou une reprise très proche de son libellé.

### `normalised`
On y met une identification plus standardisée, moderne, stable.

### Exemple
- `Work Name (as catalogue)` : `Sententiae sancti Gregorii`
- `Work (normalised)` : à remplir seulement si l’identification est claire

### Règle de prudence
Si vous n’êtes pas sûr :

- remplissez le champ `as catalogue` ;
- laissez le champ `normalised` vide ;
- ajoutez au besoin une remarque dans `Work notes`.

---

## Comment traiter les notices difficiles

Certaines notices sont claires et régulières. D’autres sont abrégées, confuses, ou mêlent titres, incipits, extraits, commentaires, anciennes attributions, remarques érudites, etc. C’est normal.

Le cas d’**Angers, BM, Ms. 275** est un bon exemple : la notice contient des titres nets, des désignations vagues, des extraits, des gloses, des textes attribués de manière incertaine, et des pièces repérées surtout par leur incipit.

Dans ce genre de cas, il faut procéder avec prudence.

---

## 1. Titres vagues

Exemples :

- `Fragment de pénitentiel`
- `Prières, dont une notée en neumes`
- `Extraits de gloses sur la Bible, sous forme de dictionnaire`

Que faire ?

- créez quand même une ligne ;
- mettez ce libellé dans `Work Name (as catalogue)` ;
- ne cherchez pas à inventer un « vrai titre » ;
- laissez `Work (normalised)` vide si nécessaire.

---

## 2. Auteur absent, vague ou douteux

Exemples :

- texte attribué anciennement à un auteur ;
- texte « emprunté à Isidore » ;
- attribution probable mais non certaine ;
- pseudo-auteur ;
- aucun auteur indiqué.

Que faire ?

- remplissez `Author (as catalogue)` seulement si le catalogue donne un nom ;
- si la notice hésite, mentionnez ce doute dans `Work notes` ;
- ne remplissez `Author (normalised)` que si vous êtes sûr.

> Une formule comme « cela paraît emprunté à des ouvrages d’Isidore » ne suffit pas forcément pour faire d’Isidore un auteur certain.

---

## 3. Incipit plus utile que le titre

Dans certaines notices, le texte est surtout identifiable par son début.

Exemples :

- `Audi, Christe, tristem fletum`
- `Deus, omnium mirabilium auctor...`
- `Alléluia in latinum sonat Lauda Dominum...`

Que faire ?

- utilisez l’incipit dans `Incipit` ;
- gardez dans `Work Name (as catalogue)` le titre ou l’intitulé donné par le catalogue ;
- ne normalisez pas à tout prix.

---

## 4. Notices parlant d’« extraits »

Exemples :

- `Extraits des Quaestiones in Genesim, etc.`
- `Extraits de gloses sur la Bible...`
- `Excerpta de libro Ysodi`

Que faire ?

- créez une ligne si le catalogue traite l’ensemble comme une unité ;
- ne divisez pas en plusieurs lignes si la notice ne le permet pas vraiment ;
- utilisez `Work notes` pour préciser qu’il s’agit d’extraits.

> On ne sur-interprète pas une notice vague.

---

## 5. Notices mêlant titre, incipit et commentaire

Dans ce cas :

- le **titre principal** va dans `Work Name (as catalogue)` ;
- les **premiers mots** vont dans `Incipit` ;
- les **remarques secondaires** vont dans `Work notes`.

Exemple :

- `Work Name (as catalogue)` : `Glosae`
- `Incipit` : `Abavus, pater preavi...`
- `Work notes` : `Sorte de lexique, anciennement attribué à Isidore...`

---

## 6. Notice ancienne ou désordonnée

Certaines notices de catalogues anciens présentent les informations dans un ordre peu régulier :

- folio ;
- incipit ;
- commentaire ;
- remarque érudite ;
- édition moderne ;
- attribution ancienne ;
- etc.

Dans ce cas, procédez calmement :

1. identifiez l’unité textuelle ;
2. notez son emplacement si la notice le donne ;
3. relevez le titre ou l’intitulé principal ;
4. notez l’incipit si utile ;
5. mettez le reste dans `Work notes`, si nécessaire.

---

## Comment utiliser les folios/pages

Remplissez les champs de localisation seulement si l’information est donnée.

Exemples valides :

- `20`
- `23v`
- `44v`
- `127v`

Si seul le début est donné :

- remplissez `Folio/page start` ;
- laissez `Folio/page end` vide.

Si rien n’est donné :

- laissez les deux champs vides.

> N’inventez jamais une plage de folios.

---

## Exemples pratiques

## Cas simple : un seul texte dans le manuscrit

Si le catalogue décrit manifestement un seul texte :

- `Sequence in MS` = `1`
- `Extent type` = `Single item listed` ou `Whole manuscript`
- `Work Name (as catalogue)` = titre donné
- `Author (as catalogue)` = si indiqué
- `Folio/page start` / `end` = seulement si donnés

---

## Cas plus complexe : Angers, BM, Ms. 275

Pour ce manuscrit, la notice énumère de nombreux items distincts. On créera donc plusieurs lignes.

### Ligne 1
- `Sequence in MS` : `1`
- `Work Name (as catalogue)` : `Sententie generales de opusculis sancti Hieronimi`
- `Author (as catalogue)` : `Hieronymus` / `saint Jérôme` / selon le catalogue
- `Extent type` : `Partial`

### Ligne 2
- `Sequence in MS` : `2`
- `Work Name (as catalogue)` : `Sententiae sancti Augustini episcopi`
- `Author (as catalogue)` : `Augustinus`
- `Folio/page start` : `20`
- `Extent type` : `Partial`

### Ligne 3
- `Sequence in MS` : `3`
- `Work Name (as catalogue)` : `Sententiae sancti Gregorii`
- `Author (as catalogue)` : `Gregorius`
- `Folio/page start` : `22`
- `Extent type` : `Partial`

### Exemple plus délicat
- `Work Name (as catalogue)` : `Fragment de pénitentiel`
- `Incipit` : `Edidit sanctus Bonefacius...`
- `Author (normalised)` : laisser vide
- `Work (normalised)` : laisser vide
- `Work notes` : ajouter une remarque si cela aide

### Exemple encore plus délicat
- `Work Name (as catalogue)` : `Extraits des Quaestiones in Genesim, etc.`
- `Author (as catalogue)` : seulement si la notice le justifie clairement
- `Work (normalised)` : probablement vide
- `Work notes` : signaler qu’il s’agit d’extraits et que la notice est vague

---

## Erreurs fréquentes à éviter

Ne pas :

- mettre plusieurs textes distincts dans une seule ligne ;
- découper un item vague en plusieurs lignes hypothétiques ;
- inventer un auteur ;
- normaliser un titre par intuition ;
- ajouter un numéro `CPL`, `BHL` ou `In Principio` sans certitude ;
- corriger silencieusement le catalogue ;
- remplir les champs normalisés « pour qu’il y ait quelque chose ».

Toujours préférer :

- une information partielle mais sûre ;
- un champ vide ;
- une question posée à M. Pollard.

---

## Que faire en cas de doute ?

Si vous hésitez :

1. laissez le champ vide ;
2. ajoutez une remarque brève dans `Work notes` si nécessaire ;
3. posez une question.

### Formule à retenir
> **Mieux vaut laisser vide que deviner.**  
> **Mieux vaut poser une question que créer une fausse certitude.**

---

## Résumé en une phrase

Votre tâche consiste à lire une notice de catalogue, à en dégager les différents items textuels, et à créer **une ligne par item** dans `Manuscript Contents`, en conservant fidèlement le libellé du catalogue et en ne normalisant que ce qui peut l’être avec sûreté.

---

## Checklist rapide

Avant de considérer une ligne comme terminée, vérifiez :

- [ ] Le bon `Bischoff Item` est lié
- [ ] `Sequence in MS` est rempli
- [ ] `Extent type` est cohérent
- [ ] `Work Name (as catalogue)` est rempli
- [ ] Le `Source catalogue` est indiqué
- [ ] Les champs `normalised` ne contiennent rien de conjectural
- [ ] Les numéros (`CPL`, `BHL`, etc.) sont sûrs
- [ ] En cas de doute, le champ a été laissé vide ou une question a été signalée
