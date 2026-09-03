Ce qui change d'une version à l'autre – décrit du point de vue de
l'application, pas de ses rouages internes. Qui veut savoir *de quoi*
elle est construite trouvera cela dans
[LIZENZEN.md](LIZENZEN.md) ; ici figure ce qui change pour le travail avec
elle.

La numérotation suit la convention habituelle : le **premier** chiffre
change quand quelque chose ne fonctionne plus comme avant, le **deuxième**
pour de nouvelles fonctionnalités, le **troisième** pour des corrections de
bugs.

---

## 0.10.52-alpha.20260903 – 3 septembre 2026

- Un lot de plus de quatre fichiers ne reste plus bloqué après plusieurs
  réponses dans les fenêtres d'aperçu. D'autres documents continuent d'être
  préparés en arrière-plan ; après une réponse, le fichier correspondant est
  désormais finalisé de manière fiable et la place suivante dans le lot est
  libérée.
- La mise en correspondance des logos courts d'entreprise dans les PDF est
  désormais limitée aux textes reconnus dans les images. Dans le texte
  ordinaire d'une page, une longue détection du modèle s'étendant sur plusieurs
  lignes n'entraîne donc plus le masquage supplémentaire d'un mot identique à
  un autre endroit.

## 0.10.51-alpha.20260903 – 3 septembre 2026

- La liste des modifications s'affiche désormais dans la langue de
  l'utilisateur – sur maskuro.com/neuigkeiten et dans le programme sous
  « Modifications », ainsi que dans « Nouveautés » après une mise à jour.
  Jusqu'à présent, les dix-huit versions linguistiques y affichaient un texte
  allemand sous un titre traduit. Quand une traduction manque encore, la
  version concernée reste en allemand au lieu de disparaître ; la liste des
  versions est identique partout.

## 0.10.50-alpha.20260903 – 3 septembre 2026

- Les logos d'entreprise récurrents dans les PDF sont désormais nettoyés de
  manière cohérente, même lorsque la reconnaissance de texte lit le
  lettrage différemment d'une page à l'autre ou omet entièrement l'emblème
  rond. Une désélection explicite dans l'aperçu reste alors contraignante
  et ne peut être annulée par aucune reprise ultérieure.
- Les prix sans devise dans des tableaux numérisés sont désormais
  intégralement caviardés même lorsque l'en-tête de tableau et les valeurs
  se trouvent dans des images PDF différentes qui se chevauchent. Les
  quantités, heures, poids et pourcentages restent en place ; des nombres
  très éloignés ne sont plus reliés par erreur en un seul montant.
- La recherche de signatures détecte désormais aussi les traits bleus
  pâles avérés et les sigles de signature rouges étroits. Les diagrammes
  pointillés, courbes de mesure, tampons, logos et larges marquages
  d'édition rouges restent exclus de cette reprise ciblée.
- Les caviardages dans des images PDF pivotées, mises en miroir, cisaillées
  ou rognées touchent désormais le véritable polygone de l'image. Les
  rôles techniques dans les postes de prestation, les valeurs techniques
  de véhicules et de pneus ainsi que la « compensation » technique sont en
  même temps délimités plus strictement contre les faux positifs ; les
  rôles de contact explicitement libellés et les numéros d'appel restent
  protégés.
- Le contrôle visuel avant l'enregistrement d'un PDF ne fait plus geler la
  fenêtre : pour les documents volumineux comportant de nombreuses
  occurrences, elle restait auparavant plusieurs secondes sans retour ;
  désormais un indicateur affiche que le contrôle est en cours, et la
  fenêtre continue de se redessiner.
- La récupération d'une valeur depuis une image dans l'éditeur de reprise
  ne lit plus chaque image originale qu'une seule fois par reconnaissance
  de texte ; auparavant elle s'exécutait à nouveau à chaque nouvelle
  reprise pour les mêmes images.
- Le rechargement du niveau élevé et du modèle de signature nécessite à
  peine plus de mémoire vive : le paquet de 596 Mo était jusqu'ici
  entièrement conservé en mémoire, vérifié et décompressé là – plus d'un
  gigaoctet de pic dans le programme en cours d'exécution, le moment où
  tout commençait à ralentir sur les machines à 8 Go. Il s'écoule
  désormais par blocs sur le disque et y est vérifié et décompressé.
- La recherche dans l'éditeur de reprise ne fait plus geler les PDF
  volumineux : la première lettre saisie dans le champ de recherche lisait
  auparavant toutes les pages d'un coup – pour 200 pages, la fenêtre
  restait bloquée deux secondes, et de nouveau après chaque caviardage.
  Les pages sont désormais lues par petits blocs ; jusque-là, le compteur
  affiche « Lecture en cours … », le résultat est identique.
- Les pages PDF rastérisées – après une reconnaissance de texte ou lorsque
  du texte n'a pas pu être retiré proprement – sont désormais enregistrées
  nettement plus petites et sans perte d'image : au lieu d'être toujours
  au format JPEG, chaque page est aussi encodée sans perte, et la version
  la plus petite est intégrée au fichier. Un scan nettoyé passe ainsi de
  248 à 48 Ko, le document d'exercice avec reconnaissance de texte de 913 à
  702 Ko ; le texte reste parfaitement net.
- Les modèles rechargés (niveau élevé, signatures, visages, seconde
  reconnaissance de texte) sont libérés de la mémoire vive après dix
  minutes sans nettoyage. Auparavant, ils restaient chargés jusqu'à la fin
  du programme – quiconque avait utilisé une fois la recherche de
  signatures et le niveau élevé occupait durablement plus de deux
  gigaoctets. Le prochain lancement les recharge en une à deux secondes ;
  la ligne d'état l'indique.
- PowerPoint : les noms génériques des mises en page de diapositives et
  des masques de diapositives (« Vide », « Diapositive de titre ») ne sont
  plus remplacés comme donnée. « Vide » est aussi un lieu et était
  caviardé à tort dans chaque présentation allemande et anglaise ; seuls
  les noms attribués manuellement aux diapositives elles-mêmes sont
  désormais nettoyés.
- Dans les PDF, le lissage de ligne n'attire plus le début de la ligne
  suivante dans une occurrence : le numéro du point de liste suivant après
  une date était considéré comme un numéro d'appel, un en-tête de champ
  comme « Code » ou « Numéro de commande » après un chiffre comme un code
  postal avec localité, et la ligne de localité sous l'adresse doublait la
  localité. L'occurrence correcte, plus courte, était de ce fait
  supplantée. Sur 132 PDF du corpus, sur 24 occurrences de lissage
  supplémentaires, les deux véritables subsistent ; dans le corpus de
  pratique, les faux positifs passent de 29 à 21 pour un taux de détection
  identique.
- « Parcourir et caviarder un dossier de PDF » dans l'éditeur de reprise ne
  bloque plus la fenêtre : le traitement s'exécute en arrière-plan, la
  progression et le bouton d'annulation réagissent, et les menus ou
  onglets ne peuvent plus être actionnés en pleine écriture d'un fichier à
  moitié terminé.
- Les pages numérisées comportant des occurrences ne sont désormais
  réécrites qu'une seule fois au lieu de deux lors du caviardage :
  auparavant, le programme remplissait les cadres des occurrences et ceux
  des justifications en deux passes, et la seconde recompressait une
  nouvelle fois l'image de scan qui venait d'être enregistrée. Cela
  économise du temps sur les grands scans et une perte de qualité sur
  l'image.
- Le défilement, le zoom et les miniatures dans l'éditeur de reprise
  réagissent plus vite : chaque page rendue passait jusqu'ici par une
  compression PNG puis en sortait aussitôt, uniquement pour être affichée –
  sur les écrans haute résolution, environ un dixième de seconde par page.
  L'image arrive désormais directement, pixel pour pixel identique.
- Le contrôle visuel avant l'enregistrement d'un PDF (« épreuve de
  sortie ») est environ trois fois plus rapide, pour un résultat identique.
- La fenêtre principale s'affiche encore environ un quart de seconde plus
  tôt : la vérification que la reconnaissance de texte est prête sur cette
  machine s'exécutait auparavant lors de la construction de la fenêtre –
  sur Mac avec en plus une requête d'essai à la reconnaissance système –,
  et la page de réglages des composants supplémentaires interrogeait à
  cette occasion l'état des 48 langues. Les deux se produisent désormais
  en arrière-plan, respectivement seulement lorsque la liste des langues
  est réellement ouverte ; jusque-là, « Vérification de la reconnaissance
  de texte … » s'affiche.
- Après une recherche de signatures, le programme occupe environ 300 Mo de
  mémoire vive en moins : le modèle de reconnaissance était jusqu'ici en
  mémoire en double – une fois pour vérifier son authenticité, une fois
  pour le calcul. Il est toujours vérifié, simplement sans la seconde
  copie.
- La reconnaissance de texte dans les PDF est sensiblement plus rapide :
  pour chaque en-tête de champ d'une page (« Date de naissance : »,
  « Numéro fiscal : »), un test distinct par type de donnée était
  auparavant envoyé à la reconnaissance – sur chaque page à nouveau, même
  si le même en-tête figurait déjà dix pages plus tôt. La réponse est
  désormais mémorisée ; un cahier des charges de deux pages posait ainsi
  324 questions, aujourd'hui seulement les différentes. Les résultats sont
  identiques.
- Les grands tableaux sont de nouveau nettoyés en secondes au lieu de
  minutes : en mode anonymisant – la valeur par défaut –, la comparaison
  des valeurs déjà connues devenait plus lente à chaque nouvelle cellule
  car une mémoire intermédiaire était rejetée et reconstruite à chaque
  correspondance. 5 000 cellules nécessitaient environ 18 secondes pour
  cela, désormais une demi-seconde ; le résultat est identique caractère
  pour caractère.
- La fenêtre principale apparaît encore nettement plus vite : la liste des
  pays des réglages faisait passer toute la bibliothèque de reconnaissance
  au premier plan lors de la construction de la fenêtre – environ
  0,7 seconde sur Mac, davantage en conséquence sur Windows –, bien que
  seuls les noms des pays soient nécessaires pour cela. La liste provient
  désormais d'un catalogue léger ; la bibliothèque se charge comme prévu
  en arrière-plan, pendant que la fenêtre est déjà affichée. Cela vaut
  aussi après chaque changement de langue ou d'apparence qui relance le
  programme.
- Le laboratoire de documents traite désormais entièrement les en-têtes de
  champs rognés, les ombres locales de valeurs et les forts rognages de
  scan à travers les conteneurs PDF, DOCX et ODT. La matrice comprend
  680 fichiers issus de 40 familles de documents et 17 axes de conteneurs.
  Maskuro retire dans les nouveaux profils ainsi que dans les profils de
  base et de caractéristiques complets toutes les valeurs cibles, sans
  faux positif mesuré, sans atteinte à une valeur à conserver ni
  interruption.

- Les scans utilisés à plusieurs reprises sont désormais vérifiés et
  nettoyés sur chaque emplacement visible : le laboratoire de documents
  partage le même objet image sur différentes pages, tailles et
  orientations dans un PDF et référence la même partie d'image plusieurs
  fois dans un DOCX et un ODT. Les noms de cadre ODT techniques comme
  « Scan de formulaire petit paysage » ne sont plus considérés comme une
  personne ; les noms et lieux libres au début similaire restent protégés.
  Une supposition générale de formulaire du passage final sur les pages
  PDF ne peut plus produire de fausse détection d'adresse majeure sur une
  zone d'image déjà lue indépendamment. Les 120 nouveaux conteneurs
  atteignent dans le profil de base et de caractéristiques la totalité des
  813, respectivement 840 valeurs cibles sans faux positif, atteinte à une
  valeur à conserver ni interruption ; la réception complète de
  caractéristiques sur 800 fichiers confirme 5 600/5 600.

- Le laboratoire OCR allemand comprend désormais 560 scans issus de
  40 familles de documents. De nouvelles variantes rognent les bords
  d'en-têtes de champ et de page ou posent une ombre directement sur une
  valeur. Maskuro protège ainsi aussi les noms, adresses, dates de
  naissance, codes médicaux et numéros d'identification libellés avec un
  libellé partiellement endommagé. En même temps, les restes de champs de
  formulaire, les titres officiels ainsi que les termes juridiques et
  informatifs factuels ne sont plus remplacés comme personnes ou lieux.
  Les profils de base et de caractéristiques complets atteignent
  3 794/3 794, respectivement 3 920/3 920 valeurs cibles sans faux positif
  mesuré ni interruption.

- La sélection automatique d'images PDF ne retire plus les grandes photos
  de produits, étiquettes énergétiques et rangées de portraits pour la
  seule raison qu'elles commencent en haut de la page. Les véritables
  images plates d'en-tête/pied de page et les en-têtes de lettre débutant
  au bord de la feuille tombent toujours. Dans les répertoires
  d'employés, les noms sont désormais aussi reconnus à partir d'entrées
  structurellement répétées lorsque le titre visible du document n'existe
  que sous forme d'image. La reconnaissance n'est plus limitée à deux
  mots de rôle précis et au sigle « DW » : une à quatre lignes de rôles
  coupées ainsi que « Durchwahl », « Nebenstelle », « Ext. » et
  « Extension » sont déduits de la forme commune. Les rôles et en-têtes de
  section restent en place, même lorsque le modèle de langue ne laisse
  qu'un adjectif de rôle après la résolution des chevauchements. Les
  grilles de rôles horizontales ne sont plus considérées à tort comme des
  colonnes de noms. Si l'OCR de page colle plusieurs cartes en un mot en
  majuscules interne extrêmement large, un contre-regard local étroit
  sépare les véritables cadres de mots ; ni un nom isolé ni une large
  barre erronée ne subsistent ainsi. Les logos d'entreprise répétés sur
  plusieurs lignes sont désormais caviardés à partir d'un modèle de
  pixels identique déjà confirmé, même sur des pages sans texte OCR
  utilisable et avec un écart de position allant jusqu'à deux pixels ; les
  secondes lectures OCR locales plus courtes ne peuvent plus non plus
  ajouter une zone d'en-tête plus grande comme nom inventé. Les numéros de
  page devant un en-tête d'entreprise ne font plus partie du nom
  d'organisation, les véritables noms de marque commençant par un chiffre
  restent protégés. Plusieurs mots de produit, spécialisés et de
  formulaire mesurés ne sont plus proposés comme des personnes.

- La recherche de signatures dans les PDF s'exécute désormais seulement
  après le nettoyage d'image OCR, visite aussi les pages sans occurrence
  de texte habituelle et recalcule correctement les cadres de résultats
  des pages pivotées dans l'espace du document. Les photos de produits
  denses ne sont plus caviardées comme signature. Au-dessus de champs de
  signature clairement libellés, un recours étroit à la ligne comble de
  fines lacunes de modèle ; des lignes vides avec date préimprimée ne le
  déclenchent pas. Les scans purs comportant exclusivement des résultats
  OCR/signature ne s'interrompent plus dans cette phase à cause d'un
  caviardeur d'image chargé seulement dans la branche texte.

- De nombreux documents ouverts simultanément restent différenciables dans
  l'éditeur de reprise : les onglets ne rétrécissent plus jusqu'à un
  simple signe de points de suspension, et un bouton de liste à droite
  affiche tous les noms de fichiers complets les uns sous les autres. Les
  onglets peuvent être réordonnés par glissement et retirés avec leur
  croix depuis la même liste que dans la fenêtre principale ; le travail
  non enregistré est toujours clarifié en premier. Un clic droit propose
  en outre « Fermer », « Fermer les autres onglets » et « Fermer les
  onglets à droite ».

- Un verrouillage temporaire de Windows par un antivirus ou l'index de
  recherche ne fait plus échouer avec « Accès refusé » le dossier de
  modèle de langue, respectivement de dictionnaire, entièrement chargé au
  moment de son insertion finale. Maskuro réessaie désormais ce dernier
  changement de dossier pendant un court instant.

- Le laboratoire de documents allemand vérifie désormais aussi les
  conteneurs avec rotation de page PDF variable, images PDF pivotées
  indépendamment ainsi que des images de tableau mises à l'échelle et
  rognées dans DOCX et ODT. Les valeurs de champ dans des images
  visiblement pivotées sont de nouveau entièrement reconnues, les
  désignateurs de colonne techniques ne sont plus remplacés comme lieux et
  les noms partageant un même nom de famille ne sont plus décomposés en
  résultats partiels doublés par le passage de cohérence. La matrice
  doublée à 320 fichiers atteint, avec la reconnaissance de date, d'argent
  et médicale activée, 2 240/2 240 valeurs cibles sans faux positif mesuré
  ni interruption.

- Les PDF image multipages, les PDF mixtes texte/image et les scans
  intégrés dans un DOCX ou un ODT sont désormais vérifiés dans un
  laboratoire propre de 160 fichiers couvrant les 40 familles de documents
  allemandes. Les noms de cadre ODT techniques et les codes d'appareil
  libellés ne sont plus remplacés comme lieux ; les véritables noms, lieux
  et adresses dans les mêmes structures restent protégés. Avec la
  reconnaissance médicale ou monétaire activée, un dosage directement
  suivant, respectivement un intervalle de paiement, sont en outre
  entièrement retirés. Les passages sur conteneur, base de texte,
  caractéristiques de texte et caractéristiques OCR atteignent ensemble
  leurs états complets respectifs sans faux positif mesuré ni
  interruption.

- Le contrôle de sécurité avant l'enregistrement affiche désormais les
  emplacements PDF suspects sous forme de liste sélectionnable
  individuellement. « Vérifier dans l'éditeur » ouvre exactement la page
  choisie et marque la zone ; les résultats partiels qui se chevauchent au
  même endroit n'apparaissent plus qu'une seule fois. Les nouveaux textes
  d'interface sont intégralement présents dans les 17 langues d'interface
  traduites.

- Les fichiers Markdown conservent leur syntaxe de liens, de mise en
  valeur et de notes de bas de page lors du remplacement. Maskuro lit pour
  cela une version de longueur identique en caractères sans les marqueurs
  Markdown ; les tirets bas dans les adresses e-mail, les astérisques de
  calcul et les liens ordinaires sans donnée personnelle restent
  inchangés.

- Plusieurs entrées manuscrites sur la même page PDF sont désormais
  recherchées en jusqu'à trois passes. Les traits déjà trouvés ne sont
  masqués que dans l'image de travail, afin qu'ils ne supplantent plus les
  signatures plus faibles ; sur les pages pivotées, les zones de
  caviardage retombent de nouveau sur l'emplacement visible détecté. Les
  remplissages d'image des phases de sécurité précédentes sont conservés
  lors de la réécriture ultérieure.

- « Réinitialiser tous les réglages » englobe désormais aussi « Texte dans
  les images ». Si le composant OCR n'est pas disponible, l'interrupteur
  reste techniquement désactivé, sans être marqué à tort comme s'écartant
  de l'état de livraison.

- Les grands fragments d'image en haut de page ne sont plus considérés
  comme en-tête pour la seule raison de leur position. De ce fait, les
  descriptions d'articles à base d'image et les contenus de tableau sont
  notamment conservés. Les résultats e-mail et formulaire nouvellement
  reconnus, exacts par type, ne sont en outre plus filtrés hors du
  contrôle visuel final sur une zone d'image déjà vérifiée.

- Les lignes de position et d'article techniques dans les offres de
  climatisation et d'électricité sont désormais distinguées plus
  strictement des personnes, lieux et organisations. Cela concerne
  notamment les types de câble, l'alimentation CA, les numéros de position
  ainsi que les codes de produit en majuscules ; les véritables noms et
  adresses restent protégés.

- Le contrôle de PDF réellement nettoyés ne confond plus des éléments de
  prix comme `1 699,59` avec des numéros de téléphone et ne découpe plus
  de prétendue donnée de carte à partir d'une date complète comme
  `08.05.2025`. Les noms après une formule de politesse s'arrêtent au
  saut de ligne au lieu de se poursuivre dans la rue suivante ; les noms
  de lieu dans les noms de fichiers en pièce jointe sont limités au lieu
  réel. Les couleurs de véhicule, valeurs d'état techniques, désignations
  professionnelles et formes juridiques de produit restent également
  conservées. Les lectures de placeholder endommagées comme `|PLLZ` ne
  sont plus traitées comme donnée personnelle lors d'un second passage
  OCR.

- Les images PDF enregistrées latéralement reçoivent lors du contrôle
  visuel final un regard supplémentaire dans leur position d'image
  inchangée. Celui-ci ne peut caviarder a posteriori que des valeurs que
  Maskuro a déjà reconnues avec certitude sur la même page. Ainsi, par
  exemple, un petit tampon d'adresse pivoté est entièrement recouvert,
  sans inventer de nouveaux mots comme données personnelles à partir de
  titres d'image ou de dessins techniques.

- Dans les textes OpenDocument, les initiales de l'auteur d'une note
  (commentaire) sont désormais effacées en même temps que l'auteur.
  LibreOffice les dépose à côté du nom complet comme forme abrégée propre
  et affiche exactement celle-ci en marge de page ; jusqu'ici, « SO »
  restait affiché alors que « Sieglinde Ortner » à côté était depuis
  longtemps un placeholder. L'effacement n'a lieu que si l'auteur a
  effectivement été remplacé – la note d'un service conserve son
  marquage.

- Dans les lettres commerciales italiennes, les formules standard en
  début de phrase ne sont plus considérées comme nom ou lieu :
  « Restiamo a disposizione », « Rimaniamo », « Attendiamo », « Alleghiamo »,
  « Comunichiamo » et « Auguriamo buon lavoro » restaient jusqu'ici
  accrochés comme prétendue personne ou donnée de lieu. Les véritables
  noms au même endroit (« Rossi Mario ») continuent d'être reconnus.

- Les scans à deux colonnes protègent désormais les identifiants et
  données de lieu libellés même lorsque la reconnaissance de texte livre
  d'abord tous les en-têtes de champ puis toutes les valeurs.
  L'affectation suit la ligne de pixels visible et fonctionne aussi sur
  des pages pivotées de 90 degrés. Les parties étroitement séparées d'un
  identifiant de passeport ou de contrat sont caviardées ensemble ; les
  dates de naissance libellées et les codes ICD et PZN sont également
  couverts, les mots factuels suivants restent en place. Les noms courts
  et noms d'utilisateur sont protégés dans des champs exacts ; les
  adresses e-mail décomposées en plusieurs mots OCR seulement en cas de
  proximité étroite et de grammaire e-mail complète. Une correction liée
  au champ de caractères prêtant à confusion ainsi que la relecture
  locale d'un champ personne encore vide referment les scans endommagés
  et pivotés, sans étendre les champs factuels ou les valeurs déjà
  occupées. Les marges de sécurité suivent la taille du mot, et le profil
  de caractéristiques inclut les unités de dosage et intervalles de
  paiement immédiatement voisins. Les formulaires légèrement de travers
  lors de la numérisation sont reprojetés géométriquement à partir de
  plusieurs lignes OCR de même direction ; un bruit d'arrondi ou des
  témoins contradictoires ne suffisent pas. Les préfixes de lettre courts
  restent conservés avant un identifiant à trait d'union, et un résultat
  d'adresse libellé complet ne remplace que son résultat partiel de rue de
  même nature. Un en-tête de champ de rôle mal lu ne tombe que dans une
  colonne de formulaire occupée par au moins trois en-têtes connus ; les
  noms de chat restent protégés. Un rognage de bord serré et une
  surexposition locale avec reflet lumineux diagonal complètent la
  matrice d'images. Les résultats de personnes, lieux et entreprises
  s'étendant sur plusieurs lignes de formulaire sont limités à la valeur
  respective dans une colonne de champ occupée plusieurs fois. Une valeur
  de position technique ne tombe qu'avec un en-tête de position et une
  forme d'identifiant correspondante ; les véritables noms restent
  protégés. Les valeurs e-mail interrompues même par un reflet lumineux
  sont également retirées derrière un en-tête de champ e-mail explicite
  avec une marge d'image étroite et limitée aux voisins. Deux paires
  champ-valeur de la même ligne visible sont désormais évaluées
  indépendamment ; les valeurs sur une ligne de base plus profonde ne sont
  couplées qu'après trois témoins géométriques concordants. De ce fait,
  les numéros d'identification, dates de naissance et adresses restent
  entièrement protégés même dans des mises en page de formulaire denses.
  La rue, le code postal et la localité ne sont réunis qu'à l'intérieur du
  même champ d'adresse et avec une grammaire postale correspondante. Les
  champs factuels étroitement délimités pour les moyens de
  travail/auxiliaires et l'état dentaire ne produisent plus de faux
  positifs de lieu ou de répertoire ; les véritables noms et champs
  nommés de façon similaire restent protégés. Le laboratoire de documents
  allemand comprend désormais 440 scans et atteint 2 981/2 981 dans le
  profil de base ainsi que 3 080/3 080 dans le profil de
  caractéristiques. Les onze mutations d'image et les 40 familles de
  documents sont toutes à 100 pour cent, toujours sans faux positif
  mesuré, atteinte à une valeur à conserver ni interruption.

- Les couches de texte PDF ayant perdu leurs séparateurs de cellules
  délimitent désormais les résultats d'organisation, d'adresse et de lieu
  à l'aide de la structure champ-valeur répétée. Les en-têtes de champ
  devant des valeurs d'entreprise et les flèches techniques comme `=>` ou
  `->` ne font plus partie du résultat. La vue supplémentaire pour les
  sauts de ligne souples ne doit plus étendre les résultats de forme
  juridique et de lieu sur plusieurs lignes de tableau ; une adresse déjà
  complète se termine avant le prochain en-tête de champ accompagné de sa
  valeur. Le passage final sur les 1 600 documents TXT, HTML, PDF et DOCX
  retire 10 840/10 840 valeurs cibles pour zéro faux positif, zéro
  atteinte à une valeur à conserver et zéro interruption.

## 0.10.44-beta.1 – 1er septembre 2026

- La construction du paquet produit des versions séparées pour Windows x64
  et ARM64, macOS sur Apple Silicon et Intel ainsi que Linux x64 et ARM64.
  Les noms de paquet, la sélection de mise à jour et les publications
  distinguent l'architecture ; une publication reste bloquée tant que l'une
  des six cibles ou son attestation de dépendances manque. Linux ARM64
  nécessite au moins glibc 2.39 à cause de Qt. Seuls Windows x64 et macOS
  sur Apple Silicon ont pour l'instant été entièrement réceptionnés sur du
  matériel réel ; les autres paquets d'architecture doivent être clairement
  désignés comme des versions préliminaires pour l'expérimentation, non
  pour un usage productif.

- Pour plusieurs fichiers, la reconnaissance continue désormais de
  travailler pendant qu'un aperçu attend d'être examiné. Jusqu'à trois
  aperçus préparés sont affichés l'un après l'autre ; en parallèle, un seul
  document continue d'être calculé, et un fichier de résultat n'apparaît
  qu'après sa validation. Une exception permanente choisie dans l'aperçu
  vaut aussi pour les documents suivants déjà préparés.

- Les certificats de rédaction peuvent désormais être vérifiés à tout
  moment directement dans le menu Fichier par rapport au document caviardé.
  Maskuro distingue alors un fichier signé correspondant, une preuve
  correspondante mais non signée, une signature invalide et un document
  n'appartenant pas au certificat. Une licence ou le compte système
  d'origine n'est pas nécessaire pour la contre-vérification.
  Pour les points de contrôle automatiques, la même comparaison est
  disponible via `--zertifikat-pruefen` ; les codes de retour distinguent
  correspondance, erreur d'utilisation et preuve invalide.
  La contre-vérification compare en outre l'identifiant Maskuro intégré au
  certificat ; un identifiant étranger librement saisi se remarque ainsi
  même avec une preuve non signée.
  En cas de signature valide, le résultat de vérification affiche en outre
  l'éditeur activé par l'administration avec le compte système,
  l'identifiant de compte technique et la plateforme. Les données non
  confirmées provenant de preuves non signées ou invalides ne sont pas
  affichées.

- Un nouveau laboratoire de documents allemand produit 160 documents TXT,
  HTML, PDF et DOCX entièrement synthétiques issus de dix domaines et
  quatre variantes de structure. Le manifeste distingue désormais
  explicitement les données qui doivent disparaître des textes techniques,
  respectivement des identifiants factuels, qui doivent être conservés ;
  la famille de documents, la mutation et la source de structure publique
  sont consignées de manière traçable.

- Le laboratoire de documents allemand a été étendu à 280 fichiers, sept
  formes de structure, 1 540 valeurs cibles et 1 036 ancrages de
  conservation. Sont désormais vérifiés des formulaires numérotés, des
  champs PDF/masqués entre crochets et des affectations techniques `=>`.
  L'état complet étendu atteint 100 pour cent en TXT, HTML, PDF et DOCX
  respectivement, sans faux positif. Les champs de date et de numéro
  d'identification entre crochets, les séparateurs à flèche et les
  associations explicitement libellées sont désormais reconnus
  structurellement.

- Une seconde extension du laboratoire porte l'ensemble à 400 documents,
  dix formes de structure, 2 200 valeurs cibles et 1 480 ancrages de
  conservation. Les valeurs-clés de type JSON, les listes YAML et les
  champs de formulaire en majuscules atteignent, avec l'ensemble
  précédent, 100 pour cent sans faux positif. Les dates de naissance et
  numéros d'identification cités ainsi que les rôles explicitement
  libellés comme personnes assurées, candidates, redevables et habilitées
  à représenter sont désormais aussi reconnus dans ces formes d'export.

- Un mode OCR distinct du laboratoire de documents allemand produit en
  outre 200 scans purement image issus des 40 familles. Les pages
  propres, à faible contraste, à basse résolution, comportant des
  artefacts JPEG et pivotées de 90 degrés sont remesurées avec des cadres
  de pixels exacts, sans modifier l'état de base comparable de
  1 600 fichiers texte. Le manifeste sépare les caractéristiques
  activables de date, d'argent et médicales du profil de base et connaît
  les lectures OCR attestées sans les compter comme valeurs cibles
  supplémentaires. La mesure est détaillée par mutation et famille de
  documents. Des limites de champ étroites empêchent notamment que « Az »
  dans le nom de lieu « Graz » fasse caviarder une date suivante comme
  numéro de dossier ; la matrice de base actuelle s'exécute avec zéro faux
  positif et zéro interruption.

- Cinq familles de documents allemandes supplémentaires pour
  facture/bordereau de livraison, banque/crédit, loyer/gestion
  immobilière, école/université et logistique/douane élargissent le
  laboratoire à 600 fichiers avec 3 520 valeurs cibles et 2 360 ancrages de
  conservation. Une voie de tableau PDF étroite utilise l'en-tête explicite
  `Feld Angabe` lorsque la couche de texte perd ses séparateurs de
  cellule ; une nouvelle sélection `--familien` accélère les mesures
  partielles. Les 200 nouveaux fichiers atteignent 1 320/1 320 sans faux
  positif ni interruption.

- Assurance/sinistre, travail/salaire, médecine/laboratoire,
  véhicule/garage et technique/maintenance élargissent le laboratoire de
  documents allemand à 800 fichiers avec 4 960 valeurs cibles et
  3 200 ancrages de conservation. Les identifiants étroitement libellés de
  police, patient, contrôleur et véhicule ainsi que de nouveaux champs de
  rôle, d'adresse et d'organisation sont reconnus. La nouvelle matrice
  partielle et la matrice complète atteignent 100 pour cent sans faux
  positif ni interruption en TXT, HTML, PDF et DOCX.

- Construction/appel d'offres, énergie/environnement,
  association/société, communication/calendrier et hôtel/événement
  portent le laboratoire de documents allemand à 1 200 fichiers avec
  7 920 valeurs cibles et 4 800 ancrages de conservation. De nouveaux
  champs de rôle, d'entreprise, d'adresse, de registre, d'attribution, de
  réservation et de compte utilisateur sont également reconnus dans tous
  les formats d'export. Les numéros de compteur restent conservés comme
  identifiants factuels. La matrice partielle et complète atteint 100 pour
  cent sans faux positif ni interruption.

- Restauration/livraison, pharmacie/ordonnance, pompes
  funèbres/cimetière, sport/adhésion et immobilier/agence élargissent le
  laboratoire de documents allemand à 1 400 fichiers avec 9 360 valeurs
  cibles et 5 640 ancrages de conservation. De nouveaux rôles de personne,
  champs d'adresse et numéros de dossier de recherche sont reconnus. Les
  noms d'entreprise libellés avec forme juridique restent entièrement
  protégés même après un saut de ligne automatique ; les classes d'âge et
  les en-têtes spécialisés ne sont plus remplacés à tort. La matrice
  partielle et complète atteint 100 pour cent sans faux positif ni
  interruption.

- Soins dentaires, auto-école, pompiers/intervention, communauté
  énergétique et voyage forfaitaire élargissent le laboratoire de
  documents allemand à 1 600 fichiers avec 10 840 valeurs cibles et
  6 440 ancrages de conservation. De nouveaux rôles, champs d'adresse
  ainsi que des identifiants de traitement, de formation, d'intervention,
  d'énergie et de contrat de voyage sont reconnus structurellement. La
  nouvelle matrice partielle de 200 fichiers atteint 1 480/1 480 ; la
  matrice complète atteint 10 840/10 840. Les deux restent à zéro faux
  positif et zéro interruption.

- La mesure complète du laboratoire de documents a réduit, grâce à des
  formes factuelles officielles et des règles de structure étroites, les
  remplacements inutiles de 68 à 0, les atteintes mesurées explicitement à
  une valeur à conserver de 23 à 0 et les interruptions de 3 à 0. Le taux
  de détection est en même temps passé de 91,1 à 100,0 pour cent ; TXT,
  HTML, PDF et DOCX atteignent chacun 100 pour cent. Les en-têtes de
  tableau généraux comme `Feld` ne sont freinés que dans la séquence
  attestée `Feld`/`Angabe` ; un nom de famille identique reste protégé.
  Les numéros de dossier judiciaires avec lettre finale, les champs à
  signe d'égalité, `Geburtsdatum des Kindes` et plusieurs noms individuels
  libellés sur la même ligne sont entièrement reconnus. Les tableaux Word
  et les champs de ligne précédente utilisent leur en-tête de champ comme
  contexte de reconnaissance temporaire ; les adresses PDF libellées
  restent entièrement protégées même en cas de saut de ligne dû à la mise
  en phrase.

- Les champs allemands de caractéristique de personne, de profession et
  médicaux fonctionnent désormais aussi avec des sauts de ligne Windows.
  Les mentions de sexe à une lettre comme `Geschlecht`/`w` sont protégées
  dans la forme en ligne précédente. Les champs factuels `Artikel-PZN`,
  en revanche, ne déclenchent ni un résultat de code de médicament ni un
  résultat de personne ; les véritables données PZN, ICD et ATC restent
  reconnues.

- Les champs de formulaire et de numéro allemands sont plus précis :
  « DW. » fonctionne désormais aussi avant un saut de ligne souple, les
  noms explicitement libellés sont retirés même en minuscules et les
  numéros de dossier purement numériques sont attribués à leur véritable
  type d'identifiant. Inversement, un numéro de facture, de bordereau ou
  d'article aléatoirement valide selon Luhn n'est plus considéré comme
  carte de crédit. Des épreuves de sortie HTML et PDF synthétiques
  confirment le retrait et la conservation dans le document terminé.
  Les numéros d'identification et noms d'utilisateur sont en outre
  reconnus lorsque leur libellé se trouve dans la ligne de tableau ou de
  formulaire immédiatement précédente ; les numéros de pièce factuels
  restent visibles également sous cette forme.

- Les mots de passe sont désormais aussi reconnus derrière un en-tête de
  champ isolé sur la ligne précédente. Les caractères spéciaux finaux
  comme `!` ou `#` font alors pleinement partie de la valeur protégée. Les
  codes PIN de produit et d'article ne sont inversement plus masqués comme
  code PIN de carte ; les champs explicites `PIN` et `Karten-PIN` restent
  protégés.

- Les valeurs de formulaire en minuscules sont désormais affichées comme
  adresse, respectivement code postal avec localité, au lieu d'un simple
  lieu général, dans le cas de champs allemands univoques d'adresse et de
  `PLZ/Ort`. De même, les valeurs d'entreprise en minuscules comme
  « beispiel service » derrière un champ d'entreprise restent entièrement
  protégées, sans couper le dernier mot comme prétendu en-tête de champ
  suivant.

- L'aide, la FAQ, le texte de confidentialité et le site web expliquent
  désormais ensemble la preuve d'origine : identifiant Maskuro neutre dans
  le document, attribution facultative au véritable compte système
  uniquement dans le journal de contrôle local, changement d'utilisateur
  sous Windows/macOS/Linux ainsi que la portée de SHA-256 et de la
  signature.

- Les cahiers des charges techniques basés sur l'image sont nettoyés de
  manière plus mesurée. Des mots factuels univoques comme
  « Abbruchhämmern », « Deckungsrücklass », « Positionsnummern »,
  « Einbauplatine » ou « Terminsituation » ainsi que des formes OCR
  coupées en plein mot ne sont plus considérés comme personne ou lieu.
  Une véritable offre d'une administration communale est ainsi passée de
  140 à 90 remplacements univoques, sans produire de nouveaux résultats ;
  des noms comme Schneider, Lang, Bauer et Hahn restent explicitement
  protégés.

- D'autres faux positifs issus d'offres réelles sont corrigés :
  « Digital signiert » ne contient plus de prétendue personne, un BIC est
  désormais reconnu même sans deux-points après son libellé,
  `15000 Alternativ` n'est plus considéré comme code postal avec
  localité, et la citation UE « (VO (EG) 715/2007 » ne produit plus
  d'organisation. Une offre photovoltaïque est ainsi passée de 26 à 16
  occurrences de remplacement ; les véritables noms, lieux et données de
  compte ont été conservés.

- Dans les organigrammes de personnel, l'abréviation de suppléance
  « Stv. » et un titre de section « FACILITY » isolé ne sont plus
  remplacés comme nom de personne. La contre-vérification réelle de
  13 pages est passée de 878 à 875 remplacements ; les noms, numéros de
  poste et la raison sociale ont été conservés.

- Les fichiers PDF, OpenDocument et Office nettoyés reçoivent un
  identifiant neutre `MASKURO-…` dans leurs propriétés de document. Le
  rapport de contrôle et le journal de contrôle signé portent le même
  identifiant ainsi que les valeurs SHA-256 de la source et du résultat ;
  le certificat de rédaction reprend l'identifiant du fichier terminé. Un
  nom d'utilisateur n'est ajouté que si l'administration active
  explicitement le champ utilisateur existant.

- La fenêtre principale et les réglages sont organisés plus calmement :
  Enregistrer, Copier, Détails, Indicateurs et la suppression d'un profil
  de reconnaissance n'apparaissent que lorsque l'action correspondante est
  possible. Les sigles de langue OCR techniques et les longs exemples se
  trouvent en cas de besoin dans le texte d'aide au lieu de rester en
  permanence dans la zone de travail. La page de reconnaissance s'adapte
  mieux aux fenêtres plus étroites, sans explications coupées ni barre de
  défilement horizontale ; l'avertissement contre le texte en clair dans
  la liste de remplacement reste visible.

- La reconnaissance couvre davantage de cas de contact allemands et
  internationaux : les numéros de téléphone sont désormais vérifiés pour
  toutes les régions de pays sélectionnables, les rôles contractuels
  hongrois et croates saisissent désormais aussi entièrement les noms de
  famille identiques à un métier, et les listes numérotées de pièces
  détachées/matériaux ne déclenchent plus de faux positif de personne à
  cause de « Mutter / Flach ». Les champs de personne avec une valeur
  factuelle manifestement chiffrée ne sont plus repris comme nom ; la
  zone de lecture automatique du passeport (MRZ) peut en outre être
  activée et désactivée conjointement via le groupe « Identifiants ».

- Les entreprises sans forme juridique sont mieux distinguées des
  personnes derrière des champs d'employeur ambigus : des noms comme
  « Huber Handel », « Müller Logistik » ou « Kowalski Handel » sont
  entièrement saisis comme entreprise, tandis que « Arbeitgeber: Bauer
  Anna » reste un nom de personne. La sélection automatique de pays tient
  toujours compte, pour les documents français, de tout l'espace
  linguistique français, Luxembourg inclus.

- Les signatures reconnues et le texte à caractère personnel à l'intérieur
  d'une image étaient jusqu'ici toujours recouverts par un rectangle noir –
  même lorsqu'une autre couleur ou un motif comme « Arc-en-ciel » était
  configuré pour les caviardages. Ces zones d'image reprennent désormais
  aussi la représentation de caviardage choisie ; la surface opaque
  continue d'être écrite directement dans les pixels.

- La reconnaissance anglaise a été remesurée et améliorée de manière
  ciblée sur onze documents réels traduits manuellement : statut
  d'inventaire, champs d'offre technique et de boutique en ligne ainsi
  que les rôles dans les répertoires d'employés restent visibles, « CV »
  n'est plus lu comme forme juridique dans la phrase modèle, les polices
  citées sont conservées, et les noms dans les en-têtes de CV verticaux,
  les listes d'employés multipages, derrière « Account manager » ainsi
  que les noms d'entreprise commençant par un chiffre sont entièrement
  reconnus. Les numéros de registre du commerce autrichiens fonctionnent
  désormais aussi derrière un libellé anglais ; la forme abrégée
  « Customer: », les numéros d'enregistrement EAR et les numéros
  d'employeur portent leur valeur. Les cotes, types de câble, renvois
  juridiques UE, dates de validité d'offre, lieux d'exécution, tribunaux
  compétents, tribunaux du registre, l'abréviation fiscale « NoVA », les
  numéros techniques dans les étiquettes de pneus ainsi que les renvois
  normatifs comme « OVE R6-2 » et « AStV » ne produisent plus de faux
  positif. Un IBAN libellé valide se termine proprement avant le champ
  d'enregistrement ou le titre de la ligne suivante ; les adresses avec
  complément de zone commerciale sont désormais entièrement reconnues même
  à partir de flux de texte PDF avec sauts de ligne Windows. Les
  introductions d'entreprise anglaises et les noms de caisses d'épargne
  structurés sont entièrement délimités. Le pays du document source reste
  conservé dans les versions linguistiques pour les codes postaux et les
  identifiants spécifiques au pays.

- Dans les en-têtes de destinataire et de message, le modèle de langue
  pouvait fusionner les deux premiers noms d'une liste séparée par des
  virgules en un seul résultat (« Bcc: Huber, Mayer »). Les deux noms sont
  désormais reconnus, remplacés et consignés séparément dans le rapport –
  de même derrière « Sent: », « Reply: » et « Fwd: ».

- La zone de lecture automatique d'un passeport ou d'une carte d'identité
  (MRZ) manquait dans le contrôle de groupe « Ce qui est recherché ». Elle
  appartient désormais à « Identifiants » et peut être activée et
  désactivée avec ce groupe.

- Qui choisit le modèle « Arc-en-ciel » pour les textes de remplacement
  obtient désormais aussi les emplacements caviardés dans la même
  apparence ; jusqu'ici, ils restaient étonnamment en noir classique. Les
  zones de caviardage peuvent ensuite toujours être basculées
  indépendamment vers un autre modèle.

- Le panneau des pages de l'éditeur de reprise pouvait rester vide après
  la restauration d'une disposition de fenêtre enregistrée, jusqu'à ce que
  sa largeur soit modifiée manuellement. Les miniatures sont désormais
  réorganisées selon la construction de fenêtre visible et se trouvent
  aussitôt centrées dans le panneau.

- Les marques de contrôle colorées autour des textes de remplacement dans
  les PDF restaient à peine visibles selon la couleur de catégorie et de
  feu tricolore. Un contour clair sépare désormais le cadre de contrôle de
  manière fiable du placeholder coloré et du fond de page.

- Qui caviarde dans l'éditeur de reprise une ligne dont le document est
  composé avec un interligne serré (typique des offres et cahiers des
  charges) obtenait une barre qui empiétait sur les jambages ascendants de
  la ligne du dessous – celle-ci n'était plus que la moitié lisible. La
  barre s'arrête désormais à l'écriture réellement dessinée de la ligne
  voisine ; la ligne caviardée elle-même reste entièrement couverte, y
  compris ses jambages descendants.

- Le document d'exercice (« Aide → Ouvrir le document d'exercice », aussi
  dans la visite guidée) présente désormais chaque type de reconnaissance :
  à la lettre inventée s'ajoutent une photo avec un visage reconnaissable,
  une signature manuscrite, une profession et un service, un diagnostic et
  un médicament – à côté du nom d'entreprise, du montant et de la date déjà
  présents. Ce que le réglage par défaut laisse volontairement en place est
  expliqué par le document lui-même, avec l'interrupteur qui le retire ; le
  visage sur la photo est pixellisé d'usine.

- Les montants d'argent dans l'écriture allemande habituelle avec le
  symbole après le nombre (« 1.240,00 € ») n'étaient jamais trouvés par
  l'interrupteur « Retirer aussi les montants d'argent » – « 1.240,00
  EUR » et « € 1.240,00 » l'étaient toujours. Les trois écritures sont
  désormais reconnues.

- La recherche de signatures fonctionne désormais aussi sur des fichiers
  image isolés : qui nettoie un scan en JPG ou PNG obtient les signatures
  manuscrites qu'il contient caviardées – la même reconnaissance, le même
  message dans le rapport que pour un PDF. Les images intégrées dans des
  fichiers Office ne sont toujours pas explorées, car la reconnaissance y
  fonctionne de manière mesurée peu fiable ; la case s'appelle donc
  désormais « PDF et fichiers image : caviarder les signatures
  manuscrites ».

- Une barre de caviardage pouvait, avec un interligne serré, empiéter
  visiblement sur les jambages ascendants de la ligne du dessous et la
  rendre à moitié illisible – la hauteur de la barre provenait des
  métriques de police, pas de ce qui figure réellement sur le papier. La
  barre s'arrête désormais à l'encre réellement dessinée de la ligne
  voisine, dans l'éditeur de reprise comme dans le nettoyage automatique.
  Sa propre ligne, jambages descendants compris, reste toujours
  entièrement couverte ; si les lignes se chevauchent vraiment, la barre
  préfère rester sur la ligne voisine plutôt que de libérer quelque chose.

- Dans un répertoire d'employés avec un rôle sous le nom, une désignation
  de direction au féminin (« Anna Berger » avec « Montageleiterin »
  dessous) était entraînée dans le remplacement du nom – la forme
  masculine à côté restait correctement en place. Les formes féminines en
  « …leiterin » (Montage-, Team-, Projekt-, Bau-, Abteilungs-, Betriebs-,
  Gruppen-, Amtsleiterin) sont désormais traitées comme désignation de
  fonction au même titre que leurs pendants masculins ; Filial-, Personal-
  et Vertriebsleitung sont nouvellement incluses dans les deux formes.

- La reconnaissance de profession activable ne trouvait pas les rôles de
  direction féminins comme « Projektleiterin », « Teamleiterin » ou
  « Abteilungsleiterin », mais bien leurs formes masculines. Les deux
  formes comptent désormais de manière égale.

- Dans la fenêtre d'aperçu, sur Mac, l'indication de multiplicité collait
  directement au terme (« Anna Musterfrau2ק au lieu de « Anna Musterfrau
  2ק). L'espacement est de nouveau présent.

- La loupe de comparaison a un nouveau bouton à côté du curseur de zoom :
  il la place d'une pression en pleine largeur sur le résultat – chacun à
  moitié hauteur, et l'original à la même échelle que le document (le zoom
  de la loupe passe alors à 100 %). Une seconde pression la ramène en
  petit dans la colonne de gauche et restaure le zoom de loupe précédent.
  Le rond à côté ne fait plus que réinitialiser le zoom – son info-bulle
  affirmait jusqu'ici à tort qu'il rattachait aussi la fenêtre.

- Dans la barre d'outils de l'éditeur de reprise, on distingue de nouveau
  visuellement l'outil choisi : le bouton de l'outil actif porte une
  surface remplie avec un bord bleu – comme tout autre bouton bascule
  activé de la barre (par exemple loupe de comparaison ou mode
  apprentissage). Le marquage avait été perdu avec la nouvelle
  présentation des boutons du 29 août.

- Les numéros de position d'un cahier des charges (« 2.3.3.3, 2.3.3.4,
  2.3.3.5 » les uns sous les autres) étaient pris pour des adresses IP et
  retirés du résultat ; des numéros à trois niveaux avec un dernier
  élément ressemblant à une année (« 2.3.19, 2.3.20 ») tombaient comme
  dates de calendrier. Une séquence numérique croissante en début de
  ligne est désormais considérée comme ce qu'elle est – une liste de
  positions ; les véritables adresses (tableaux réseau avec environnement
  de mots techniques, nombres supérieurs à 99) et les véritables dates
  restent toujours reconnues.

- Des noms de famille comme « Müller », « Fischer », « Bauer », « Koch »,
  « Wagner », « Schneider », « Weber », « Jäger », « Schmied », « Becker »,
  « Schuster », « Schäfer » ou « Meister » restaient en clair dans des
  listes de la forme « Nachname, Vorname » (p. ex. « Teilnehmer: Müller,
  Peter; Nowak, Anna ») car ils sont en même temps des désignations
  professionnelles courantes. Ils sont désormais reconnus de manière
  fiable.

- Lors du caviardage d'un PDF, la barre pouvait, dans des cellules de
  tableau étroites, emporter toute la cellule : à partir du résultat
  « D-LINK » dans un cahier des charges, toute la description de produit
  à côté était retirée, bien que l'aperçu n'ait mentionné que le résultat.
  La barre continue de couvrir des lignes entières de bloc d'adresse et
  des libellés de champ, mais elle n'emporte au maximum que ce qui n'est
  pas concerné dans la même proportion que ce qu'elle couvre de digne de
  protection – la description à côté du résultat reste désormais en
  place.

- Après « Réinitialiser la vue » dans l'éditeur de reprise, le panneau des
  pages restait vide – les miniatures des pages n'étaient de nouveau
  visibles qu'après la fermeture et la réouverture de la fenêtre. Elles
  apparaissent désormais aussi directement après la réinitialisation,
  centrées comme avant.

- L'éditeur de reprise a un quatrième outil : **Retirer** enlève le texte
  sous le cadre sans remplacement – sans barre (caviarder) et sans
  placeholder (remplacer) ; l'espace reste visiblement vide. Il agit au
  mot près, si une image se trouve dessous, son fond est nettoyé en blanc,
  et « Récupérer l'original » annule aussi un retrait sans remplacement.
  Symbole de barre propre et badge de réticule (croix), raccourci mémo
  propre dans les 18 langues (allemand F comme entFernen).

- Dans la barre de recherche PDF, « Dossier … » se trouve désormais à
  droite des options de recherche. Depuis qu'il existe, en plus du
  caviardage, aussi le remplacement des résultats, cinq boutons ne
  tenaient plus côte à côte à la largeur de fenêtre habituelle – le
  premier était comprimé et son texte coupé.

- « Réinitialiser tous les réglages » réinitialise désormais aussi la case
  « Remplacer rouge/vert par d'autres couleurs » et la marque, comme
  toute autre, avec « modifié » si elle s'écarte de la livraison.

- Les textes de remplacement dans les PDF sont désormais plus réguliers :
  là où le placeholder complet devrait être nettement plus petit que sa
  ligne (par exemple « [BEG16] » comprimé dans un mot court comme « Das »),
  une forme abrégée à la taille de la ligne apparaît à la place
  (« [B16] ») – bien lisible plutôt que minuscule, et le numéro pour la
  récupération porte les deux écritures. Un placeholder ne devient
  minuscule que lorsque même la forme la plus courte ne trouve pas de
  place – ce qui reste mieux qu'une barre sans aucune information.

- Un texte de remplacement multicolore (dégradé ou arc-en-ciel) dans un
  PDF ne restait intact que jusqu'à l'intervention suivante : chaque
  nouveau remplacement ou caviardage sur la même page pouvait comprimer
  des placeholders déjà posés en un empilement de lettres illisible et
  tassé – qui remplaçait mot par mot dans l'éditeur voyait, au lieu de
  « [BEG17] », uniquement des caractères imprimés les uns sur les autres.
  Les placeholders une fois posés restent désormais tels qu'ils ont été
  posés.

- L'interrupteur des exceptions permanentes dans l'aperçu s'appelle
  désormais « Ne jamais retirer » – comme la liste dans laquelle il
  inscrit ; jusqu'ici, il était intitulé « plus jamais ». La ligne de
  résultat à côté est plus soignée : le symbole d'information « ⓘ » est
  plus grand et plus facile à atteindre, et la case, la marque de
  remplacement et le bouton ont une hauteur commune. La phrase autour
  d'un résultat utilise désormais réellement la largeur annoncée – la
  précédente indication de largeur avait été silencieusement rejetée par
  l'affichage, et l'extrait se poursuivait comme une bande étroite.

- Dans l'éditeur, le curseur de la souris indique désormais quel outil
  agit : un réticule pour viser, à côté un petit signe – barre pour
  caviarder, flèches d'échange pour remplacer, arc d'annulation pour
  restaurer, grille de pixels pour pixelliser. Les anciens symboles de
  main ont disparu ; une main signifie partout ailleurs « saisir et
  déplacer ». Elle a désormais une tâche adaptée : au-dessus d'un mot ou
  d'une barre mis en évidence en rouge, le curseur devient une main qui
  pointe – un clic y suffit.

- « Reconnaissance maximale (IA) » ne propose plus de modèle de langue
  local téléchargeable – le niveau calcule désormais exclusivement via
  une IA personnelle configurée sous « Connecter une IA personnelle ».
  Qui avait déjà connecté son propre serveur ne remarque aucune
  différence.

- La visite guidée de l'aperçu explique désormais aussi le symbole
  d'information « ⓘ » qui affiche la phrase autour d'un résultat. Et
  cette phrase elle-même est plus lisible : une taille de police plus
  grande, plus d'interligne, largeur fixe au lieu d'un saut de ligne
  étroit et serré.
- « Vérifier le fichier », « Règles de reconnaissance et termes
  personnels », « Nettoyer le texte » et « Nettoyer l'image » ont
  désormais aussi leur propre visite guidée – via un nouveau bouton
  « Visite guidée de la fenêtre », car ces quatre fenêtres n'ont pas de
  barre de menu propre.
- Les noms sous neuf libellés de rôle contractuel ukrainiens restaient
  incomplètement reconnus en cas de nom de famille homographe, lorsque le
  libellé se trouvait seul sur sa ligne : « Покупець »/« Продавець »
  (acheteur/vendeur), « Поручитель »/« Боржник » (garant/débiteur
  principal), « Свідок » (témoin), « Орендодавець »/« Орендар »
  (bailleur/locataire) et « Спадкодавець »/« Спадкоємець »
  (testateur/héritier). Les noms sont désormais entièrement reconnus.

- Le commentaire d'une plage nommée dans un classeur Excel (gestionnaire
  de noms, champ « Commentaire ») conservait sans modification un nom qui
  y était inscrit. Il est désormais nettoyé de la même manière que le
  reste du contenu du classeur.

- Les noms sous sept libellés de rôle contractuel hongrois restaient
  totalement inaperçus en cas de nom de famille homographe :
  « Bérbeadó »/« Bérlő » (bailleur/locataire), « Vevő »/« Eladó »
  (acheteur/vendeur), « Kezes »/« Főadós » (garant/débiteur principal) et
  « Tanú » (témoin). Les noms sont désormais entièrement reconnus.

- Les noms sous le libellé tchèque d'acheteur « Kupující » restaient
  totalement inaperçus en cas de nom de famille homographe. Le nom est
  désormais entièrement reconnu.

- Les noms sous le libellé russe de tuteur « Опекун » restaient totalement
  inaperçus en cas de nom de famille homographe. Le nom est désormais
  entièrement reconnu.

- Les noms sous six autres libellés croates restaient inaperçus : « Jamac »
  (garant), « Glavni dužnik »/« Dužnik » (débiteur principal/débiteur),
  « Ostavitelj » (testateur), « Nasljednik » (héritier/héritière) et
  « Vjerovnik » (créancier). Les noms sont désormais entièrement reconnus.

- Une page web enregistrée avec une sous-page intégrée dans l'attribut
  `src` d'un `<embed>` (au lieu de `data` pour `<object>`) conservait sans
  modification les données à caractère personnel qu'elle contenait. Elles
  sont désormais nettoyées comme pour `<object>`.

- Les noms sous cinq libellés de rôle contractuel danois restaient
  incomplètement reconnus en cas de nom de famille homographe, lorsque le
  libellé se trouvait avec deux-points devant le nom : « Arvelader »/
  « Arving » (testateur/héritier), « Befuldmægtiget »/« Fuldmagtsgiver »
  (mandataire/mandant) et « Værge » (tuteur). Les noms sont désormais
  entièrement reconnus ; les libellés norvégiens correspondants ont
  également été ajoutés par précaution.

- Les placeholders dans les fichiers Word et PowerPoint portent désormais
  la même couleur que dans l'apparence choisie (unie, dégradé, arc-en-ciel
  ou par catégorie) – jusqu'ici, ils restaient là dans la couleur de texte
  ordinaire, même lorsque les résultats PDF étaient depuis longtemps
  colorés.

- « Copier comme texte » et « Copier comme Markdown » déposent directement
  le texte en clair du résultat dans le presse-papiers – pour l'insérer
  dans un chat, un e-mail ou un autre programme, sans avoir à ouvrir
  d'abord le fichier.

- Les noms sous cinq autres libellés slovènes restaient inaperçus :
  « Toženec » (défendeur), « Tožnik » (demandeur), « Zastavitelj »
  (constituant du gage), « Zastavni upnik » (créancier gagiste) et
  « Darovalec » (donateur). Les noms sont désormais entièrement reconnus.

- Le nom de l'auteur d'une modification de cellule de tableau suivie
  (cellule insérée, supprimée ou fusionnée dans Word) restait dans le
  fichier, même lorsque le même nom en tant qu'auteur de commentaire avait
  depuis longtemps été retiré. Il est désormais également retiré.

- Les noms sous neuf autres libellés slovènes restaient inaperçus :
  « Najemodajalec »/« Najemnik » (bailleur/locataire), « Zapustnik »/
  « Dedič » (testateur/héritier), « Upnik »/« Dolžnik »
  (créancier/débiteur), « Glavni dolžnik » (débiteur principal) et
  « Skrbnik » (tuteur/curateur). Les noms sont désormais entièrement
  reconnus.

- Les noms sous cinq libellés slovènes restaient inaperçus : « Izvedenec »
  (expert), « Kupec » (acheteur), « Prodajalec » (vendeur), « Naročnik »
  (donneur d'ordre) et « Izvajalec » (prestataire). Les noms sont
  désormais entièrement reconnus.

- Les noms sous cinq autres libellés lituaniens restaient inaperçus :
  « Užsakovas » (donneur d'ordre), « Vykdytojas » (prestataire),
  « Vežėjas » (transporteur), « Siuntėjas » (expéditeur) et « Arbitras »
  (arbitre). Les noms sont désormais entièrement reconnus.

- Les noms sous six autres libellés lituaniens restaient inaperçus :
  « Įgaliotinis » (mandataire), « Įgaliotojas » (mandant), « Naudos
  gavėjas » (bénéficiaire, assurance), « Trečiasis asmuo » (intervenant
  volontaire/tiers dans une procédure civile), « Ankstesnis nuomininkas »
  (ancien locataire) et « Naujasis nuomininkas » (nouveau locataire). Les
  noms sont désormais entièrement reconnus.

- Un signet dans les documents ODT (`text:bookmark`) porte son nom
  librement attribué, souvent nommé d'après l'emplacement qu'il désigne
  (p. ex. « Herr_Mueller_Unterschrift ») – invisible pour le lecteur, mais
  littéralement dans le fichier. Le nom est désormais nettoyé également.

- Les noms sous huit autres libellés lituaniens restaient inaperçus :
  « Pareiškėjas » (demandeur), « Suinteresuotas asmuo » (défendeur dans
  une procédure non contentieuse), « Ekspertas » (expert), « Bankroto
  administratorius » (administrateur judiciaire), « Valdybos narys »
  (membre du conseil de surveillance), « Direktorius » (directeur
  général), « Palikėjas » (testateur) et « Įpėdinis » (héritier). Les noms
  sont désormais entièrement reconnus.

- Les noms sous sept autres libellés lituaniens restaient inaperçus :
  « Liudytojas » (témoin), « Vertėjas » (interprète/traducteur),
  « Notaras » (notaire), « Dovanotojas » (donateur), « Apdovanotasis »
  (donataire), « Pirkėjas » (acheteur) et « Pardavėjas » (vendeur). Les
  noms sont désormais entièrement reconnus.

- Les noms sous six autres libellés lituaniens restaient inaperçus :
  « Globėjas » (tuteur/curateur), « Palikimo administratorius »
  (administrateur de succession), « Laiduotojas » (garant), « Pagrindinis
  skolininkas » (débiteur principal), « Nuomotojas » (bailleur) et
  « Nuomininkas » (locataire). Les noms sont désormais entièrement
  reconnus.

- Un nom sous le libellé lituanien « Ieškovas »/« Atsakovas »
  (demandeur/défendeur en tant que partie au procès) restait inaperçu,
  que le nom de famille soit aussi un mot courant (p. ex. « Vilkas » =
  loup) ou non. Le nom est désormais entièrement reconnu.

- Une entrée de répertoire de personnes dans les documents ODT (marque de
  texte pour l'index) portait le nom une seconde fois dans sa propre clé
  de tri – invisible dans le texte courant, mais littéralement dans
  l'index généré plus tard. La clé est désormais nettoyée également.

- Le nom de diapositive et le nom de section d'une présentation
  PowerPoint (visibles dans le volet de sélection ou dans le trieur de
  diapositives) restaient non nettoyés, car les deux sont un attribut
  attaché à un élément qui n'est pas du texte de diapositive. Les deux
  sont désormais reconnus.

- Un nom composé lituanien à trait d'union comme « Petraitis-Kazlauskas »
  perdait sa seconde moitié dès qu'un texte courant quelconque le
  précédait (seul en début de texte, il restait complet) : le nom de
  famille est désormais entièrement reconnu même dans ce cas.

- Un nom sous le libellé « Cesionar » (croate, cessionnaire lors de la
  cession de créance) produisait un faux positif parce que le libellé de
  champ lui-même était lu à tort comme une personne. Un nom sous le
  libellé russe « Цессионарий » (également cessionnaire) restait quant à
  lui totalement inaperçu. Les deux cas sont désormais corrigés.

- Un nom sous le libellé « Zedent »/« Zessionar » (allemand, cession de
  créance) restait totalement inaperçu lorsque le nom de famille était en
  même temps un mot courant (p. ex. « Bauer »). Le nom est désormais
  entièrement reconnu.

- Un nom sous le libellé « Darczyńca »/« Obdarowany » (polonais,
  donateur/donataire dans le contrat de donation) restait inaperçu
  lorsque le nom de famille était en même temps un mot courant (p. ex.
  « Wilk » = loup). De même, le libellé roumain « Donatar » (donataire)
  restait accroché pour un nom de famille ordinaire comme un prétendu
  élément du nom. Les deux cas sont désormais corrigés.

- Un nom sous le libellé « Wierzyciel »/« Dłużnik » (polonais, créancier
  poursuivant/débiteur poursuivi, ou créancier/débiteur général) restait
  inaperçu lorsque le nom de famille était en même temps un mot courant
  (p. ex. « Wilk » = loup). Le nom est désormais entièrement reconnu.

- Un nom sous le libellé « Poręczyciel »/« Dłużnik główny » (polonais,
  garant/débiteur principal dans les contrats de cautionnement) restait
  inaperçu lorsque le nom de famille était en même temps un mot courant
  (p. ex. « Wilk » = loup). Le nom est désormais entièrement reconnu.

- Un nom sous le libellé « Ubezpieczony »/« Ubezpieczający » (polonais,
  assuré/preneur d'assurance dans les polices d'assurance) restait
  partiellement ou totalement inaperçu lorsque le nom de famille était en
  même temps un mot courant (p. ex. « Wilk » = loup). De même pour un nom
  sous « Osiguranik »/« Osiguravatelj » (croate, mêmes rôles), où il
  disparaissait entièrement avec le prénom (p. ex. « Golub » = pigeon).
  Les deux noms sont désormais entièrement reconnus.

- Un nom sous le libellé « Pełnomocnik »/« Mocodawca » (polonais,
  mandataire/mandant dans les procurations) restait inaperçu lorsque le
  nom de famille était en même temps un mot courant (p. ex. « Wilk » =
  loup). De même pour un nom sous « Opunomoćenik »/« Opunomoćitelj »
  (croate, mêmes rôles), où il disparaissait même entièrement avec le
  prénom. Les deux noms sont désormais entièrement reconnus.

- Un nom sous le libellé « Pozwany » (polonais, défendeur en tant que
  partie au procès) restait inaperçu lorsque le nom de famille était en
  même temps un mot courant (p. ex. « Wilk » = loup). Le nom est désormais
  entièrement reconnu.

- Un nom sous le libellé « Najmoprimac »/« Najmodavac » (croate,
  locataire/bailleur dans les contrats de location) restait inaperçu
  lorsque le nom de famille était en même temps un mot courant (p. ex.
  « Kovač » = forgeron). Le nom est désormais entièrement reconnu.

- Un nom sous le libellé « Pracodawca »/« Pracownik » (polonais,
  employeur/employé en tant que partie contractante dans les contrats de
  travail) restait partiellement inaperçu lorsque le nom de famille était
  en même temps un mot courant (p. ex. « Krawiec » = tailleur). Le nom
  est désormais entièrement reconnu.

- La Hongrie n'avait dans le catalogue de pays que les identifiants de
  personne et l'identifiant de TVA : le numéro de registre du commerce
  (Cégjegyzékszám) est désormais reconnu, à condition que le mot de champ
  « Cégjegyzékszám » ou l'abréviation « Cg. » le précède immédiatement –
  le numéro lui-même ne porte pas de chiffre de contrôle.

- L'Estonie n'avait dans le catalogue de pays que l'Isikukood : le
  Käibemaksukohustuslase number (identifiant de TVA sur chaque facture
  estonienne) est désormais reconnu avec chiffre de contrôle.

- La Lettonie n'avait dans le catalogue de pays que le Personas kods : le
  PVN reģistrācijas numurs des personnes morales (identifiant d'entreprise
  sur chaque facture lettone) est désormais reconnu avec chiffre de
  contrôle.

- Un e-mail au contenu chiffré (enveloppe S/MIME ou PGP/MIME,
  `multipart/encrypted`) était présenté sans aucun avertissement comme
  apparemment entièrement vérifié, alors que son contenu réel était
  chiffré et donc non vérifié. De tels e-mails signalent désormais cela,
  comme une pièce jointe non vérifiée.

- Malte manquait dans le catalogue de pays : l'identifiant de TVA maltais
  (VAT number) est désormais reconnu.

- Le Luxembourg manquait dans le catalogue de pays : l'identifiant de TVA
  luxembourgeois (n° TVA) est désormais reconnu.

- Un bulgare « Изчакайте » (« Attendez ! ») placé en début de phrase était
  signalé comme donnée de lieu – la même limite de modèle que
  précédemment pour les formes impératives hongroises, polonaises,
  tchèques et autres sans modèle de langue propre. Le faux positif
  n'apparaît plus désormais.

- Un nom sous le libellé « Zleceniodawca », « Zleceniobiorca » (polonais),
  « Prestator » (roumain), « Naručitelj » ou « Izvođač » (croate) restait
  partiellement ou totalement inaperçu lorsque le nom de famille était en
  même temps un mot courant (p. ex. « Wilk », « Vuk » = loup, « Vulpe » =
  renard, « Sokol » = faucon). Le nom est désormais entièrement reconnu.

- Un nom sous le libellé « Nadawca » (polonais), « Afsender » (danois) ou
  « Pošiljatelj » (slovène) restait partiellement ou totalement inaperçu
  lorsque le nom de famille était en même temps un mot courant (p. ex.
  « Sowa » = hibou, « Bager » = boulanger, « Volk » = loup). Le nom est
  désormais entièrement reconnu.

- Un nom sous le libellé « Gavėjas » (lituanien) ou « Prejemnik »
  (slovène) restait partiellement ou totalement inaperçu lorsque le nom de
  famille était en même temps un mot courant (p. ex. « Vilkas » = loup).
  Comme déjà pour « Primatelj » (croate) et « Modtager » (danois), le nom
  est désormais entièrement reconnu.

- Un en-tête de circulaire comme « To All Staff » ou « To All Employees »
  était reconnu à tort comme nom de personne et retiré. Cela ne se produit
  plus désormais.

- Un nom sous le libellé « Primatelj » (croate) ou « Modtager » (danois)
  restait partiellement inaperçu lorsque le nom de famille était en même
  temps un mot courant (p. ex. « Golub » = pigeon, « Bager » = boulanger).
  Comme déjà pour « Odbiorca » (polonais) et « Destinatar » (roumain), le
  nom est désormais entièrement reconnu.

- Un nom complet sur la ligne de signature d'un document danois,
  norvégien ou grec restait partiellement inaperçu lorsque le libellé
  « Underskrift » ou « Υπογραφή » se trouvait seul au-dessus du nom – dans
  le cas grec, le nom de famille était même reconnu comme donnée de lieu
  au lieu de nom. Comme déjà pour « Подпись » (russe), le nom est
  désormais entièrement reconnu.

- Le texte sur une photo de téléphone déposée latéralement (la prise
  verticale habituelle qui n'est affichée à l'endroit que via une marque
  de rotation d'image) pouvait être manqué par la reconnaissance de texte,
  car celle-ci lisait jusqu'ici les pixels bruts, couchés. De telles
  photos sont désormais correctement pivotées avant la lecture – comme
  précédemment déjà pour la reconnaissance faciale.

- Un nom complet sur la ligne de signature d'un document russe, ukrainien
  ou lituanien restait partiellement inaperçu lorsque le libellé
  « Подпись », « Підпис » ou « Parašas » se trouvait seul au-dessus du
  nom – le prénom ou le patronyme disparaissait. Comme déjà pour
  « Potpis » (croate), le nom est désormais entièrement reconnu.

- Un visage sur une photo de téléphone déposée latéralement (la prise
  verticale habituelle qui n'est affichée à l'endroit que via une marque
  de rotation d'image) pouvait être manqué par la reconnaissance faciale,
  car celle-ci vérifiait jusqu'ici les pixels bruts, couchés. De telles
  photos sont désormais correctement pivotées avant la recherche.

- Un nom complet sur la ligne de signature d'un document croate restait
  partiellement inaperçu lorsque le libellé « Potpis » se trouvait seul
  au-dessus du nom ou avec deux-points devant – le prénom disparaissait,
  que ce soit sur une ligne propre ou dans « Potpis: Vorname Zweitname
  Nachname ». Comme déjà pour « Unterschrift » et « Signature », le nom
  est désormais entièrement reconnu.

- Un nom d'épouse ou d'époux derrière les abréviations d'état civil
  « verh. » (mariée/marié) et « verw. » (veuve/veuf) restait jusqu'ici
  totalement inaperçu, que ce soit entre parenthèses, après une virgule ou
  collé sans espace (« Anna Meier (verh. Weber) », « Klaus Bauer
  (verw.Fischer) ») – comme déjà pour « geb. », il est désormais reconnu
  de manière fiable.

- Un nom derrière la mention de procuration « ppa. » (p. ex. dans la ligne
  de signature d'un e-mail professionnel ou d'une lettre commerciale)
  restait jusqu'ici partiellement ou totalement inaperçu en cas de nom de
  famille identique à un nom de métier comme « Bauer » ou « Koch » –
  comme déjà pour « gez. », il est désormais reconnu de manière fiable.

- Le numéro de la carte d'identité polonaise (dowód osobisty) n'était
  reconnu que sans espace entre la série et le numéro (« ABS123456 »).
  Or ce n'est pas ainsi que le document imprime la donnée – officiellement
  un espace s'y trouve (« ABS 123456 »), et sous cette écriture, le
  numéro restait jusqu'ici inaperçu.

- Un PNG animé (APNG, p. ex. un court enregistrement d'écran déposé en
  PNG au lieu de GIF) n'était jusqu'ici vérifié et nettoyé que par sa
  première image, sans que cela soit signalé – comme précédemment pour le
  WebP animé, Maskuro signale désormais que chaque image supplémentaire
  reste non vérifiée dans le résultat.

- Une image WebP animée (p. ex. issue d'un outil de capture d'écran ou
  d'une application de chat avec plusieurs images dans un fichier)
  n'était jusqu'ici vérifiée et nettoyée que par sa première image, sans
  que cela soit signalé – comme précédemment pour un TIFF multipage,
  Maskuro signale désormais que chaque image supplémentaire reste non
  vérifiée dans le résultat.

- Un prénom double slovène à trait d'union (« Ana-Marija Novak ») perdait
  sa première moitié dès qu'une phrase courante le précédait dans le
  texte – la même erreur que précédemment pour le polonais. « Ana- »
  restait en clair, non traité, tandis que le reste du nom était déjà
  remplacé.

- Un prénom double polonais à trait d'union (« Anna-Maria Kowalska »)
  perdait sa première moitié dès qu'une phrase courante ou une
  préposition comme « z »/« od » le précédait – le reste du nom était
  remplacé, « Anna- » restait en clair, non traité.

- Des formules de politesse kazakhes « Хабарласыңыз »/« Байланысыңыз »
  (contactez-nous) ainsi que des formes verbales serbes « Помоћи »,
  « Чекамо » et « Пишите » sans modèle de reconnaissance linguistique
  propre étaient reconnues à tort comme nom de personne ou lieu dans des
  phrases de contact téléphonique.

- Le mot de politesse azerbaïdjanais « Xahiş » (prière/demande) sans
  modèle de reconnaissance linguistique propre était reconnu à tort comme
  nom de personne dans des phrases de contact téléphonique.

- Des mots de politesse/d'incitation indonésiens et malais sans modèle de
  reconnaissance linguistique propre comme « Silakan », « Mohon »
  (indonésien), « Sila » et « Tolong » (malais) étaient reconnus à tort
  comme nom de personne ou lieu dans des phrases de contact téléphonique.

- La forme impérative ouzbèke « Kutamiz » (nous attendons) sans modèle de
  reconnaissance linguistique propre était reconnue à tort comme lieu dans
  des phrases de contact téléphonique.

- Des formes impératives turques sans modèle de reconnaissance
  linguistique propre comme « Arayınız » (appelez) et « Bekliyoruz »
  (nous attendons) étaient reconnues à tort comme nom de personne dans des
  phrases de contact téléphonique.

- Des formes impératives dans d'autres langues sans modèle de
  reconnaissance linguistique propre (tchèque, slovaque, grec) comme
  « Zavolejte » (appelez), « Prosíme » (nous prions) et « Περιμένουμε »
  (nous attendons) étaient reconnues à tort comme nom de personne ou lieu
  dans des phrases de contact téléphonique.

- Des formes impératives hongroises et polonaises comme « Hívjon »
  (appelez), « Kérjük » (nous prions), « Várjuk » (nous attendons),
  « Zadzwoń » (appelez) et « Czekamy » (nous attendons) étaient reconnues
  à tort comme nom de personne ou lieu dans des phrases de contact
  téléphonique.

- Dans une liste de noms numérotée sans forme de tableau (p. ex.
  « 1. Robert Brown », dessous « 2. Mary Johnson »), un nom avec certains
  noms de famille anglais (entre autres « Brown », « White », « Green »,
  « Black », « Young ») était complètement manqué – le modèle de langue
  avait attaché le numéro de la ligne suivante au nom, si bien que le
  résultat ne correspondait plus jamais exactement.

- Dans le modèle de langue polonais, l'initiale de prénom placée avant un
  nom de famille (p. ex. « J. Kowalski », « A. Nowak ») restait non
  reconnue et non nettoyée dans le texte – seul le nom de famille était
  remplacé. D'autres langues vérifiées (entre autres l'allemand,
  l'anglais, le roumain, le croate, le hongrois, le russe) prenaient déjà
  la même initiale auparavant.

- Un nom de personne derrière un titre en minuscules comme « dr. »,
  « ing. » ou « dipl. ing. » n'était pas du tout reconnu en hongrois,
  roumain et croate – non seulement le titre, mais tout le nom était
  perdu (p. ex. « dr. Kovács Béla », « ing. Andrei Popescu », « dipl. ing.
  Marko Horvat »).
- Dans les procès-verbaux de séance slovènes, une simple désignation de
  rôle avant les deux-points (p. ex. « Tajnik: », « Podpredsednik: »,
  « Poročevalec: », « Predsedujoči: ») était reconnue à tort comme nom de
  personne dès qu'un véritable nom d'orateur figurait déjà ailleurs dans
  le procès-verbal.
- Dans les procès-verbaux de séance russes, une simple désignation de
  rôle avant les deux-points (p. ex. « Секретарь: », « Докладчик: »,
  « Докладчица: ») était reconnue à tort comme nom de personne dès qu'un
  véritable nom d'orateur figurait déjà ailleurs dans le procès-verbal.
- Dans les procès-verbaux de séance roumains, une simple désignation de
  rôle avec article défini avant les deux-points (p. ex. « Secretarul: »,
  « Președintele: », « Vicepreședintele: », « Moderatorul: »,
  « Consilierul: ») était reconnue à tort comme nom de personne –
  « Președintele » déjà à lui seul, les autres en plus dès qu'un véritable
  nom d'orateur figurait déjà ailleurs dans le procès-verbal.
- Dans les procès-verbaux de séance croates, une simple désignation de
  rôle avant les deux-points (p. ex. « Izvjestiteljica: »,
  « Zapisničar: »/« Zapisnicar: », « Predsjedavajući: ») était reconnue à
  tort comme nom de personne.
- Une adresse de boîte postale polonaise « Skrytka pocztowa » derrière un
  libellé d'expéditeur ou de destinataire (p. ex. « Odbiorca: Skrytka
  pocztowa 45 ») était reconnue à tort comme nom de personne.
- Une adresse de boîte postale croate « Poštanski pretinac » derrière le
  libellé d'adresse « Adresa: » (p. ex. « Adresa: Poštanski pretinac 45 »,
  aussi avec « br. » accolé pour le numéro) était reconnue à tort comme
  nom de personne.
- Un lieu sans autre libellé dans un texte courant norvégien (p. ex.
  « Anna Hansen bor i Oslo ») n'était pas reconnu – le propre modèle de
  langue y désigne le plus souvent les lieux avec une étiquette propre,
  jusqu'ici non attribuée, au lieu du « LOC » habituel.
- Une date dans l'ordre ISO année-mois-jour avec trait d'union ou point
  (p. ex. « 2024-12-31 ») n'était pas du tout reconnue comme date dans
  certaines langues – le plus visiblement en lituanien, où les courriers
  officiels indiquent les dates majoritairement dans cet ordre.
- Un identifiant de TVA hongrois (közösségi adószám) sous sa forme à
  11 chiffres sans séparateur, tout aussi officiellement valide (p. ex.
  « 12345678123 » au lieu de « 12345678-1-23 »), n'était pas reconnu.
- Un numéro fiscal polonais NIP avec les séparateurs dans le groupement
  3-2-2-3 (p. ex. « 856-73-46-215 », comme il est habituel sur les
  factures d'entreprises et d'entrepreneurs individuels) n'était pas
  reconnu – seul le groupement 3-3-2-2 pour les personnes physiques
  était détecté.
- Un nom d'entreprise sous le libellé de champ slovaque
  « Zamestnávateľ: » ou « Názov zamestnávateľa: » (employeur/entreprise)
  n'était pas reconnu.
- Un nom d'entreprise sous le libellé de champ roumain « Angajator: » ou
  « Denumire angajator: » (employeur/entreprise) n'était pas reconnu.
- Un nom d'entreprise sous le libellé de champ hongrois « Cég: » ou
  « Munkáltató: » (entreprise/employeur) n'était pas reconnu.
- Un nom d'entreprise sous le libellé de champ polonais « Pracodawca: »
  ou « Nazwa firmy: » (employeur/entreprise) n'était pas reconnu.
- Un nom d'entreprise sous le libellé de champ slovène « Podjetje: » ou
  « Delodajalec: » (entreprise/employeur) n'était pas reconnu.
- Un nom d'entreprise sous le libellé de champ croate « Tvrtka: » ou
  « Poslodavac: » (entreprise/employeur) n'était pas reconnu.
- Un montant d'argent écrit en toutes lettres avec une devise en
  minuscules (p. ex. « 500 euro ») n'était pas reconnu, seule la
  majuscule (« Euro ») était détectée.
- Le nom de famille derrière « Schwager »/« Schwägerin » (p. ex. « Der
  Schwager Bauer erhält die Erbschaft. ») n'était pas reconnu.
- Pour une adresse turque sans signe de ponctuation séparateur entre code
  postal+localité et rue+numéro (p. ex. « 34000 İstanbul İstiklal Caddesi
  No: 45 »), le numéro restait non nettoyé.
- Pour une adresse slovaque sans signe de ponctuation séparateur entre
  code postal+localité et rue+numéro (p. ex. « 831 01 Bratislava Hlavná
  15 »), le numéro restait non nettoyé.
- Un pays de naissance sans autre libellé dans un champ de formulaire
  croate (p. ex. « Zemlja rođenja: Njemačka ») n'était pas reconnu.
- Un pays de naissance sans autre libellé dans un champ de formulaire
  lituanien (p. ex. « Gimimo valstybė: Vokietija ») n'était pas reconnu.
- Un pays de naissance ou de résidence sans autre libellé dans un champ de
  formulaire polonais (p. ex. « Kraj: Niemcy ») n'était pas reconnu.
- Une nationalité ou un lieu de résidence sans autre libellé dans un champ
  de formulaire slovène (p. ex. « Državljanstvo: Nemčija ») n'était pas
  reconnu.
- Un pays de résidence sans autre libellé dans un champ de formulaire
  norvégien (p. ex. « Bosted: Tyskland ») n'était pas reconnu.
- Nouvelle page de réglages « Notifications » (auparavant une section
  dans « Programme ») : les trois messages de la barre des tâches
  (aperçu prêt, traitement terminé, mise à jour téléchargée) se trouvent
  désormais à un endroit propre.
- Nouveau : le résultat peut en outre être déposé à côté comme simple
  fichier texte (.txt) ou avec l'extension .md – pour un traitement
  ultérieur dans une IA ou un autre programme.
- Pour une coordonnée de contact croate avec le libellé « Osoba za
  kontakt »/« Kontakt osoba » (p. ex. « Osoba za kontakt: Golub Marko »),
  le nom restait totalement inaperçu lorsque le nom de famille était en
  même temps un substantif courant (Golub = « pigeon »).

- Pour une coordonnée de contact roumaine avec le libellé « Persoana de
  contact »/« Persoană de contact » (p. ex. « Persoana de contact: Lup
  Ion »), le nom restait totalement inaperçu lorsque le nom de famille
  était en même temps un substantif courant (Lup = « loup ») et le
  prénom très court et générique.

- Pour une coordonnée de contact polonaise avec le libellé « Osoba
  kontaktowa »/« Osoba do kontaktu » (p. ex. « Osoba kontaktowa: Wilk
  Adam »), le nom de famille restait inaperçu lorsqu'il était en même
  temps un substantif courant (Wilk = « loup », Zielony = « vert »).

- Pour une adresse roumaine sans signe de ponctuation séparateur entre
  code postal+localité et rue+numéro (p. ex. « 010061 București Strada
  Victoriei 30 »), le numéro restait non nettoyé.
- Pour une adresse serbe sans signe de ponctuation séparateur entre code
  postal+localité et rue+numéro (p. ex. « 11000 Beograd Bulevar Kralja
  Aleksandra 73 »), le numéro restait non nettoyé.
- Pour une adresse grecque sans signe de ponctuation séparateur entre code
  postal+localité et rue+numéro (p. ex. « 104 32 Αθήνα Ερμού 15 »), le
  numéro restait non nettoyé.
- Pour une adresse slovène sans signe de ponctuation séparateur entre code
  postal+localité et rue+numéro (p. ex. « 1000 Ljubljana Slovenska cesta
  58 »), le code postal restait non nettoyé.
- Pour une adresse lituanienne sans signe de ponctuation séparateur entre
  code postal+localité et rue+numéro (p. ex. « LT-01100 Vilnius Gedimino
  pr. 9 »), le code postal restait entièrement non nettoyé.
- Pour une adresse hongroise sans signe de ponctuation séparateur entre
  code postal+localité et rue+numéro (p. ex. « 1052 Budapest Kossuth
  Lajos utca 12 »), le code postal restait non nettoyé.
- Un nom de famille derrière « Erben » (p. ex. « Die Erben Wagner
  erhielten die Mitteilung fristgerecht. ») restait pour ainsi dire
  toujours inaperçu dans un contexte de succession.
- Un nom de famille derrière « Geschwister » (p. ex. « Die Geschwister
  Bauer wohnen in Linz. ») restait jusqu'ici pour ainsi dire toujours
  inaperçu – contrairement à « Familie »/« Ehepaar », cela touchait non
  seulement les noms identiques à un métier (Koch, Bauer, Richter), mais
  tout nom de famille à cet endroit.
- Un nom de famille derrière « Ehepaar » ou « Eheleute » (p. ex. « Das
  Ehepaar Koch zieht um. ») restait inaperçu lorsqu'il était en même temps
  un substantif courant ou une désignation professionnelle (Koch, Bauer,
  Richter).
- Un numéro de commande, de dossier ou d'article ordinaire dans la grille
  de groupement typique d'un numéro fiscal ou de sécurité sociale (p. ex.
  « 030 4471 2298 ») était caviardé à tort comme tel sans aucun libellé
  associé.
- Un numéro de pièce/de dossier au format « année/numéro courant » (p. ex.
  dans « Rechnung Nr. 4/2024/778899 ») était caviardé à tort comme numéro
  de téléphone par la reconnaissance de numéro d'appel.
- Un nom derrière « Herr »/« Frau » avec une chaîne de titre académique à
  plusieurs mots devant (« Herr Dr. med. Weber », « Herr Prof. Dr.
  Krause ») restait jusqu'ici totalement non protégé – seul un mot de
  titre isolé entre la formule de politesse et le nom était jusqu'ici
  reconnu.
- Un numéro de dossier judiciaire au format classique avec sigle de
  chambre/de section (« 4 Ca 1523/24 », « Az.: 7 O 234/25 ») restait
  jusqu'ici totalement non protégé – même la forme abrégée habituelle
  « Az. »/« Gz. » n'était pas reconnue à côté du libellé écrit en toutes
  lettres.
- Un numéro de carte de crédit séparé au milieu de son groupement de
  quatre par un saut de ligne – par exemple dans une colonne de tableau
  étroite – restait jusqu'ici totalement non protégé.
- Un numéro d'identification fiscale séparé au milieu de son groupement
  par un saut de ligne – par exemple dans une colonne de tableau étroite
  ou un champ de formulaire – restait jusqu'ici totalement non protégé.
- Un numéro de sécurité sociale séparé au milieu de son groupement par un
  saut de ligne – par exemple dans une colonne de tableau étroite –
  restait jusqu'ici totalement non protégé, pas même partiellement
  remplacé.
- Un numéro de rue avec plage comme « 12a-14b » ou « 3-5 » n'était
  remplacé qu'à moitié – la seconde partie après le trait d'union restait
  ouverte dans le résultat.
- Un numéro d'identification de véhicule (FIN/VIN) séparé au milieu de
  ses 17 caractères par un saut de ligne, un espace ou un trait d'union –
  par exemple dans une colonne de tableau étroite ou un champ de carte
  grise – restait jusqu'ici totalement non protégé.
- Une formule d'appel de lettre/e-mail comme « Liebe Anna! » ou « Lieber
  Hans » – sans virgule après le nom, la forme la plus fréquente dans les
  e-mails informels – laissait le nom totalement non protégé, même dans
  le document complet avec texte courant et formule de salutation
  dessous.
- La même lacune touchait aussi les formules d'appel informelles de chat
  ou d'e-mail « Hallo Anna! », « Hi Anna! », « Hey Anna! » et « Servus
  Anna! » sans virgule – le nom restait également totalement non protégé.
- Un simple bloc de signature commençant directement par « MfG » ou
  « Herzlichst » – par exemple copié depuis le presse-papiers, sans phrase
  précédente – laissait le nom en dessous totalement non protégé.
- Un champ avec plusieurs personnes, par exemple « Angehörige: Kaczmarek,
  Piotr (Sohn), Kaczmarek, Anna (Ehefrau) », fusionnait les deux noms
  avec l'indication entre parenthèses en un seul résultat, beaucoup trop
  long – le second nom restait alors en partie non protégé dans le
  résultat.
- Une rue sans suffixe « -straße »/« -weg » – comme c'est habituel à la
  campagne, par exemple « Am Marktplatz 5 » ou « Im Grund 12 » – n'était
  pas reconnue lorsqu'une ligne code postal-localité la suivait, par
  exemple dans une attestation d'enregistrement : « Neue Anschrift: Am
  Weidengarten 17, 54295 Trier » perdait entièrement la rue, seul le
  code postal était retiré.
- Un nom derrière un libellé de champ composé avec barre oblique (par
  exemple « Name/Vorname: Bauer Klaus ») n'était en partie pas reconnu –
  un nom de famille ambigu comme « Bauer » restait inaperçu sans la
  preuve du champ. La même lacune touchait des champs combinés comme
  « PLZ/Ort: 04109 / Leipzig ». Il en allait de même pour des champs
  combinés avec connecteur écrit en toutes lettres au lieu d'une barre
  oblique, par exemple « Vor- und Nachname: Bauer Klaus » ou « Nachname
  bzw. Vorname: … ».
- Une date de naissance sous la forme « Datum der Geburt: … » et une date
  de décès sous la forme « Todesdatum: … » ou « Datum des Todes: … »
  n'étaient pas reconnues – seules « Geburtsdatum: … » et
  « Sterbedatum: … » étaient détectées.
- Une date de mariage sous la forme « Datum der Heirat: … » ou « Datum
  der Hochzeit: … » n'était pas reconnue – seules « Hochzeitsdatum: … »,
  « Heiratsdatum: … » et « Datum der Eheschließung: … » étaient
  détectées, bien que la date de divorce, de naturalisation et de
  partenariat civil connaissent depuis longtemps la même forme
  « Datum der X ».
- Une date de divorce sous la forme « Datum der Scheidung: … » n'était
  pas reconnue – seule « Scheidungsdatum: … » et la forme verbale
  postposée étaient détectées, bien que la date de naturalisation et de
  partenariat civil connaissent depuis le début la même forme
  « Datum der X ».
- Une date de partenariat civil n'était jusqu'ici pas du tout reconnue –
  ni avec libellé (« Verpartnerungsdatum: … », « Datum der
  Lebenspartnerschaft: … ») ni dans le texte courant (« … wurden am …
  verpartnert »). Elle est désormais remplacée, comme la date de
  naissance, de mariage, de divorce et de naturalisation, comme un type
  de donnée propre.
- Une date de naturalisation n'était jusqu'ici pas du tout reconnue – ni
  avec libellé (« Einbürgerungsdatum: … ») ni dans le texte courant
  (« … wurde am … eingebürgert »). Elle est désormais remplacée, comme la
  date de naissance, de mariage et de divorce, comme un type de donnée
  propre.
- Une date de divorce n'était jusqu'ici pas du tout reconnue – ni avec
  libellé (« Scheidungsdatum: … ») ni dans le texte courant (« Die Ehe
  wurde am … geschieden »). Elle est désormais remplacée, comme la date
  de naissance, de décès et de mariage, comme un type de donnée propre.
- Une date de mariage derrière le signe généalogique de mariage « ⚭ » sans
  libellé n'était pas reconnue, bien que la date de naissance et de décès
  sur la même ligne via l'étoile et la croix soient déjà reconnues –
  désormais la date de mariage est également reconnue.
- Une date de décès derrière la croix de faire-part sans libellé
  (« *03.06.1940 †21.11.2023 ») n'était pas reconnue, bien que la date de
  naissance devant, via l'étoile généalogique, soit déjà reconnue –
  désormais la date de décès est également reconnue.
- Le nom de famille avant le prénom en fin de ligne d'objet/de ticket avec
  texte factuel précédent et trait de séparation (« Betreff: Reklamation -
  Bauer, Anna ») n'était pas reconnu pour un nom de famille identique à
  un métier – il est désormais reconnu.
- Les numéros de candidat et de demandeur derrière leur libellé
  (« Bewerbernummer: 4471829 », « Antragstellernummer: 7654321»)
  échappaient entièrement à la reconnaissance – ils sont désormais
  reconnus.
- Remplacer ne caviarde plus lorsqu'il n'y a pas de place pour un
  placeholder lisible – un placeholder trop petit est désormais écrit en
  plus petit au lieu de devenir une barre vide, tant qu'il reste de la
  place du tout. Nouveau également : le fait qu'un résultat sur une image
  (en-tête de lettre, fond de scan) soit libellé ou seulement caviardé
  peut désormais être réglé indépendamment du reste du type de résultat.
  Et un résultat sur une image entièrement retirée était libellé comme si
  l'image restait en place – le placeholder se trouvait clair sur un fond
  jamais caviardé, et disparaissait ainsi invisiblement sur le papier
  désormais blanc.
- Un résultat sur une image **conservée** était toujours caviardé en
  noir et blanc lors du remplacement, indépendamment de l'apparence
  choisie (couleurs de catégorie, arc-en-ciel …) – visible comme une
  rupture entre des étiquettes colorées dans le texte courant et des
  barres noires sur l'en-tête de lettre. Le fond de l'image suit
  désormais la même couleur que le placeholder à côté.
- La reconnaissance du numéro d'identification de véhicule (FIN/VIN)
  marquait sans condition tout code alphanumérique à 17 caractères sans
  I/O/Q comme numéro de châssis – même les numéros de commande, de série
  et de clé de licence qui ont par hasard la même forme. Elle ne compte
  désormais qu'avec un mot de contexte à proximité (« FIN », « VIN »,
  « Fahrgestell », « Chassis » etc.).
- Dans les systèmes de tickets/calendrier, la reconnaissance de noms
  entraînait après « Assigned to »/« Closed by » etc. le mot de champ
  suivant lorsqu'il suivait directement sur la même ligne sans séparateur
  (« Assigned to Max Mustermann Priority High » devenait « Max Mustermann
  Priority »). Dans les en-têtes de commit Git, la reconnaissance de noms
  entraînait de même la clé de trailer **suivante** lorsque deux lignes
  s'enchaînaient avec un seul espace au lieu d'un saut de ligne
  (« Author: julia bergmann Reviewed-by: … » devenait « julia bergmann
  Reviewed-by »). Les deux freins ont été complétés.
- Le nom derrière « p.A. », « zH »/« zHd », « i.A. »/« i.V. » et « geb. »
  entraînait un mot de service directement suivant dans le même résultat
  lorsqu'il se trouvait sans séparateur sur la même ligne (« p.A. Max
  Mustermann Buchhaltung » devenait « Max Mustermann Buchhaltung »,
  « i.A.Max Mustermann Vertrieb » devenait « Max Mustermann Vertrieb »).
  Le même frein que pour « Assigned to »/les trailers Git a désormais
  été complété ici aussi.
- Un IBAN libellé directement au-dessus de la ligne BIC, BLZ ou SWIFT
  entraînait son libellé dans son propre résultat, car « BIC » et « BLZ »
  ressemblaient eux-mêmes à un bloc de numéro supplémentaire – de
  « IBAN: DE89 … 0130 00 » et la ligne dessous résultait un seul résultat
  trop étendu, et le libellé de la ligne suivante disparaissait avec lors
  du nettoyage. Presque chaque relevé bancaire avec IBAN et BIC les uns
  sous les autres était concerné.
- Le panneau de résultats indique désormais **où** se trouve un
  placeholder qu'il ne peut pas trouver sur la page. Deux cas ne
  signalaient jusqu'ici que « introuvable », alors que le remplacement
  avait bien eu lieu : si le placeholder se trouve dans un texte annexe
  non visible – par exemple l'adresse de renvoi d'un lien, une annotation
  ou un champ de formulaire –, la ligne porte désormais cette
  information propre (« dans le texte annexe »), et le clic l'explique.
  Et si le placeholder a été écrit sous forme abrégée faute de place
  (« [N382] » au lieu de « [NAM382] »), le clic sur la longue ligne saute
  désormais vers l'emplacement de la forme abrégée et nomme le
  renommage ; l'affectation relie explicitement les deux lignes entre
  elles pour cela.
- Si la même valeur de remplacement figure plusieurs fois dans le
  document, chaque clic supplémentaire sur la ligne du panneau saute en
  boucle vers le résultat suivant – même par-delà les limites de page ;
  la ligne d'état compte en même temps (« résultat 2 sur 4 »), et
  l'emplacement actuellement visé est encadré plus fortement que les
  autres. Et si un placeholder ne figure que dans la liste de résultats
  mais nulle part dans le document (parce que l'emplacement a été absorbé
  dans un remplacement qui se chevauche), la ligne d'état l'indique
  désormais, au lieu que le clic reste silencieusement sans effet.
- Un prénom abrégé derrière « an » ou « für » est désormais reconnu de
  manière fiable comme nom – « Überweisung an M. Wagner » et « Rechnung
  für M. Wagner » restaient jusqu'ici souvent non nettoyés, tandis que le
  même nom avec un autre libellé devant (par exemple
  « Zahlungsempfänger: ») était déjà trouvé. Étaient concernées surtout
  les lignes de relevé de compte et d'écriture comptable.
- « Angeklagter »/« Angeklagte »/« Beschuldigter »/« Beschuldigte »
  comptent désormais comme champ de nom : lorsqu'un nom se trouvait dans
  des documents de procédure pénale directement derrière l'un de ces
  libellés, il n'était jusqu'ici pas du tout reconnu pour environ la
  moitié des noms vérifiés – ni prénom ni nom de famille.
- L'emplacement cliqué depuis le panneau de résultats est désormais
  encadré en bleu au lieu d'être marqué en jaune – sur les surfaces
  colorées du feu tricolore de contrôle, le jaune du résultat de
  recherche n'était pas discernable. En outre, le clic trouve désormais
  aussi les valeurs de remplacement à plusieurs mots (noms inventés,
  numéros masqués) : jusqu'ici, il restait sans effet sur de telles
  lignes, car l'emplacement n'était recherché que mot par mot.
- Les parents adoptifs, nourriciers et beaux-parents (« Adoptivvater »,
  « Pflegemutter », « Stiefvater » et autres) sont désormais reconnus
  comme champ de nom, le nom échappait auparavant à la reconnaissance
  sans être nettoyé
- Les tableaux et listes riches en chiffres ne sont plus rejetés à tort :
  lorsqu'un nombre court (par exemple une partie de numéro de client lue
  comme numéro d'appel) était remplacé, le contrôle final signalait la
  même séquence de chiffres comme donnée résiduelle même lorsqu'elle se
  trouvait ailleurs par hasard dans un tout autre numéro – et ne
  fournissait alors aucun résultat du tout. Un nombre ne compte désormais
  comme reste que là où il figure comme nombre propre.
- Actes d'état civil : « Vater: »/« Mutter: » est désormais reconnu comme
  champ de nom, le nom du parent échappait auparavant à la reconnaissance
  sans être nettoyé
- D'autres rôles familiaux (« Pate », « Großvater/-mutter », « Ehepartner »,
  « Lebenspartner », « Onkel », « Tante ») sont désormais reconnus comme
  champ de nom, le nom échappait auparavant à la reconnaissance sans être
  nettoyé
- Le code guichet allemand (Bankleitzahl) est désormais aussi reconnu
  groupé de façon officielle (« 370 400 44 », « 370.400.44 »,
  « 370-400-44 », « 370/400/44 »), plus seulement comme huit chiffres
  consécutifs.
- Le numéro d'assurance retraite allemand est désormais aussi reconnu
  avec point, trait d'union ou barre oblique entre les cinq blocs
  (« 65-170839-J-08-8 », « 65.170839.J.08.8 »), plus seulement avec
  espaces.
- La fenêtre principale apparaît plus vite : les bibliothèques de
  reconnaissance (Presidio avec le socle de modèles de langue) étaient
  jusqu'ici déjà chargées lors de la construction de la fenêtre – environ
  quatre secondes sur Windows avant même qu'il y ait quoi que ce soit à
  voir. Elles se chargent désormais entièrement en arrière-plan ; le
  bouton « Nettoyer » ne devient libre, comme avant, que lorsque tout est
  prêt.
- Les documents Office comportant de nombreuses images ou vidéos sont
  écrits plus vite : les médias déjà compressés sont désormais enregistrés
  dans le paquet de résultat au lieu d'être inutilement compressés une
  seconde fois – cela n'économisait jusqu'ici pas un octet et rendait
  plutôt les JPEG plus volumineux.
- Les tableurs et autres documents composés de nombreuses petites unités
  de texte sont vérifiés plus vite : la reconnaissance linguistique
  traite désormais toutes les cellules et paragraphes d'un document en un
  seul passage au lieu d'un par un – pour des résultats identiques
  démontrés (400 cellules : d'environ 4,7 à 2,5–3,5 secondes).
- Les pages PDF de type liste (répertoires, listes de positions) sont
  nettement plus rapides lors de l'insertion des placeholders : la
  recherche de place par libellé parcourait jusqu'ici tous les mots de la
  page – désormais seulement l'environnement de la ligne, pour un résultat
  démontré identique (sur une page à 300 libellés, environ seize fois plus
  vite).
- Les documents riches en images économisent plusieurs étapes de travail
  inutiles par image : le comptage des visages et des codes sur les pages
  PDF ne décode plus l'image de page deux fois, le contrôle des métadonnées
  ne déchiffre plus du tout une image propre, les images pixellisées sont
  écrites avec la compression PNG normale au lieu de la plus lente (même
  taille, un tiers du temps), et sans filigrane configuré, la réécriture
  inutile de tout le PDF à la fin disparaît.
- Les PDF numérisés avec reconnaissance de texte activée sont nettement
  plus rapides : chaque page était jusqu'ici rendue deux fois en pleine
  résolution (une fois pour la lecture, une fois pour la rastérisation) –
  l'image est désormais réutilisée. Et sous Windows/Linux, la
  reconnaissance de texte lit les bandes d'un grand scan en un seul
  passage au lieu d'un démarrage de programme propre par bande.
- Les grands documents sont nettoyés nettement plus vite : la comparaison
  des valeurs déjà trouvées croissait jusqu'ici avec le nombre de
  résultats (un bloc de texte de 64 Ko coûtait à la fin d'un grand fichier
  environ une seconde rien que pour cela, désormais un soixantième), et la
  recherche des formes juridiques d'entreprise parcourait les ~280 formes
  du catalogue sur chaque emplacement de texte (désormais environ vingt
  fois plus rapide, pour des résultats identiques démontrés).
- Un nom directement après « Beste Grüße »/« Beste Wünsche » sans texte
  ni ponctuation précédents n'était pas du tout reconnu – un simple bloc
  de signature sans texte courant devant faisait disparaître le nom sans
  laisser de trace.
- Un champ d'adresse en début de document avec un nom de famille
  identique à un métier (« Bauer Anna », « Koch Stefan » comme première
  ligne au-dessus de la rue et de la localité) restait jusqu'ici en
  partie inaperçu ou était classé comme donnée de lieu au lieu de
  personne – sans phrase précédente, il manquait au modèle de langue la
  structure de phrase qui permet sinon de reconnaître « Bauer » comme
  nom et non comme métier.
- Un nom derrière la marque de signature « gez. » avec un nom de famille
  identique à un métier avant le prénom (« gez. Bauer Anna » à la fin
  d'une décision ou d'un jugement) restait jusqu'ici incomplètement
  reconnu – seul le prénom était trouvé, le nom de famille disparaissait
  sans laisser de trace.
- Un nom directement derrière un numéro de client, de contrat ou un
  numéro d'identification similaire sans ligne propre (« Vertragsnummer
  55219 Bauer Anna », « Kundennr. 4711 Bauer Anna ») restait jusqu'ici
  incomplètement ou pas du tout reconnu pour un nom de famille identique
  à un métier.
- Le symbole dans la barre de menu macOS est désormais un modèle qui
  s'adapte au mode clair et sombre comme les symboles voisins – avec les
  deux barres découpées, il reste reconnaissable comme Maskuro. Si le
  veilleur de presse-papiers fonctionne, un point détaché à la pointe du
  bouclier l'indique.
- Un clic dans le panneau de résultats mène désormais aussi en mode
  anonymisant vers l'emplacement du résultat : changement de page,
  défilement vers l'image, marquage en jaune. Jusqu'ici, le clic restait
  sans effet là, car il considérait encore les placeholders comme sans
  numéro – depuis que chaque résultat porte son propre numéro,
  l'emplacement est univoque. Seul le placeholder réellement sans numéro
  continue d'expliquer, dans la ligne d'état, pourquoi aucune destination
  de saut ne peut être déterminée.
- Le premier enregistrement dans l'éditeur de reprise (Ctrl+S ou le bouton
  disquette) demande désormais l'emplacement, comme « Enregistrer sous… »
  – prérempli avec le dossier de l'original et le nom de résultat.
  Jusqu'ici, le fichier atterrissait sans un mot à côté de l'original. Qui
  a déjà choisi l'emplacement de dépôt via la ligne d'état n'est pas
  redemandé ; chaque enregistrement suivant réécrit comme avant le même
  fichier.
- Si le contrôle de sécurité avant l'enregistrement signale un emplacement
  suspect, « Retour au contrôle » y mène désormais : le premier résultat
  défile vers l'image et est encadré en rouge, la ligne d'état le nomme.
  Jusqu'ici, on restait seul avec un numéro de page et des coordonnées de
  point. Depuis la fenêtre principale, l'éditeur s'ouvre alors à cet
  endroit. En cas d'indication de numéro de page divergent, le bouton mène
  désormais aussi vers la première page qui n'existe que dans l'un des
  deux documents.
- Qui bascule l'aperçu sur « Côte à côte en deux colonnes » obtient
  désormais de lui-même une fenêtre où les deux voies tiennent – jusqu'ici
  elles se comprimaient dans l'ancienne largeur, jusqu'à ce qu'on les tire
  soi-même. L'élargissement va au maximum jusqu'au bord de l'écran et
  n'est jamais réduit en retour ; une largeur tirée soi-même reste
  inchangée.
- Le nom de famille et le prénom dans des colonnes de tableau séparées
  (p. ex. « Nachname | Vorname » dans une confirmation d'inscription ou un
  export CSV) restaient ouverts – chaque cellule prise à part ressemblait,
  pour la reconnaissance, à un mot quelconque sans lien avec un nom. Sont
  désormais reconnus.
- Le nom et le prénom au verso d'un permis de conduire européen au format
  carte restaient ouverts – ils se trouvent là derrière les codes de champ
  officiels « 1. » et « 2. » au lieu d'un mot allemand, et c'est
  précisément cela qui les laissait inaperçus. Sont désormais reconnus
  lorsque le numéro de permis de conduire (code de champ « 5. ») se
  trouve à côté.
- Le prénom du titulaire du véhicule sur le certificat d'immatriculation
  restait ouvert – il se trouve derrière le code de champ officiel
  « C.1.2 » au lieu d'un mot allemand comme « Vorname », et c'est
  précisément cela qui le laissait inaperçu. Le nom de famille et le
  prénom sous les codes de champ C.1, C.1.1 et C.1.2 sont désormais
  reconnus.
- La première ligne de la zone de lecture automatique (MRZ) sur un
  passeport ou une carte d'identité restait ouverte – elle porte le nom
  au format « NACHNAME<<VORNAME » et passait entièrement au travers même
  avec le nouveau reconnaisseur MRZ pour la ligne de chiffre de contrôle.
  Un résultat ne compte désormais que si une seconde ligne MRZ valide en
  chiffre de contrôle se trouve directement à côté – la ligne de nom
  elle-même n'a pas de chiffre de contrôle propre.
- La seconde ligne de la zone de lecture automatique (MRZ) sur un
  passeport ou une carte d'identité restait entièrement inaperçue – elle
  contient le numéro de passeport, la date de naissance et d'expiration
  en clair, mais ne touchait aucun reconnaisseur existant. Un
  reconnaisseur propre vérifie désormais les quatre chiffres de contrôle
  ICAO.
- Une plaque d'immatriculation sans aucun espace par rapport au libellé
  restait ouverte – « KennzeichenM-AB1234 » ou « KFZ-KennzeichenM-AB1234 »
  n'étaient pas du tout reconnus, car la vérification de plaque sous-
  jacente exige un caractère non alphanumérique avant la plaque. Concernait
  les données de véhicule où aucun espace ne sépare le mot de champ de la
  plaque.
- Un numéro d'appel sans aucun espace par rapport au libellé restait
  ouvert – « Handynummer0171/2345678 » ou « Tel0171/2345678 » n'étaient
  pas du tout reconnus, car la vérification de numéro d'appel sous-jacente
  exige un espace ou un signe de ponctuation avant le numéro. Concernait
  les coordonnées où aucun espace ne sépare le mot de champ du numéro.
- Un nom de naissance derrière l'abréviation « geb. » n'était pas du tout
  reconnu – « Julia Bergmann (geb. Weber) » ne trouvait que « Julia
  Bergmann », le point dans « geb. » faisait complètement ignorer le nom
  suivant par le modèle de langue. Concernait les données de personne avec
  nom de naissance entre parenthèses ou après une virgule.
- Le prénom avant un surnom entre guillemets restait ouvert lorsque la
  formule de politesse et le titre se trouvaient ensemble devant –
  « Herr Dr. Klaus "KP" Peters » ne donnait que « Peters », « Klaus »
  restait lisible. Concernait les signatures et coordonnées avec titre et
  surnom.
- Un nom derrière la forme abrégée sans point « zH »/« zHd » (à
  l'attention de) n'était pas du tout reconnu – contrairement à
  « z.Hd. » avec point, la structure de phrase manquante entraînait le nom
  avec elle. Concernait les adresses sans point dans l'abréviation.
- Un nom derrière « p.A. » (chez, par adresse) n'était pas du tout reconnu
  – le point dans l'abréviation faisait complètement sauter la
  reconnaissance de nom par le modèle de langue. Concernait les factures
  et candidatures avec adresse collective.
- Un nom derrière « i.A. »/« i.V. » (par ordre/en représentation) collé
  sans point n'était pas du tout reconnu, par exemple « i.A.Robert Lang »
  sans espace – la même erreur de structure de phrase que pour « p.A. ».
  Concernait les lignes de signature et signatures d'e-mail de cas de
  représentation.
- Une simple liste de présence à puces sans aucune autre donnée
  (« - Max Mustermann », aussi avec point en fin de ligne) perdait tous
  les noms au même frein qui ne doit en réalité protéger que les
  énumérations factuelles comme « - Farbe: Blau ». De telles listes sont
  désormais reconnues.
- Les fichiers qui ne pouvaient plus être nettoyés peuvent de nouveau
  l'être. Une valeur déjà remplacée par la reconnaissance pouvait être
  retrouvée dans sa propre marque déjà remplacée comme « [SVNR1] » – le
  contrôle final rejetait alors un fichier impeccablement nettoyé. En
  outre, un renvoi téléphonique dans un tableau CSV est désormais retiré
  également, et qui limite la recherche à certains types l'obtient
  désormais partout dans le document de manière identique – y compris
  dans le texte alternatif d'une image, un en-tête Excel, une liste
  déroulante ou un attribut HTML.
- Un nom derrière l'en-tête d'e-mail « To: » (ou « To » sans deux-points)
  n'était pas reconnu, car un modèle de langue étranger lisait toute la
  ligne comme un seul résultat anodin et engloutissait complètement le nom
  qu'elle contenait – contrairement à « Cc: », « Bcc: » ou « From: » avant
  le même nom. Un nom derrière « To » est désormais trouvé de manière
  fiable.
- La date de mariage ne pouvait pas être traitée comme date dans des
  règles personnelles (« déplacer » était rejeté avec « n'existe que pour
  les dates »), manquait dans l'affectation de groupe des types de
  résultat – ce qui empêchait de la désactiver via les marques « Ce qui
  est recherché » – et recevait le libellé complet comme placeholder au
  lieu d'un sigle court comme pour la date de décès. Corrigé pour les six
  tables de sigles/libellés.
- Une valeur explicitement désélectionnée dans l'aperçu pouvait quand même
  être caviardée à un autre endroit : si l'on désélectionnait par exemple
  une adresse e-mail, l'adresse elle-même restait bien en place, mais sa
  partie locale sans domaine était remplacée dès qu'elle coïncidait avec
  le nom d'utilisateur dérivé d'une personne restée sélectionnée
  (« anna.musterfrau@beispiel.de » à côté de « Anna Musterfrau »). Un
  libellé désélectionné reste désormais tabou dans tout le document,
  indépendamment du type de résultat dont il provient.
- Une date de naissance restait inaperçue lorsqu'un livret de famille ou
  un extrait d'état civil la présentait sous un en-tête commun avec le
  lieu de naissance (« Geburtsdatum, Geburtsort: 19.11.1982, Steyr ») – le
  second mot de champ entre « Geburtsdatum » et la date faisait
  jusqu'ici entièrement échouer la reconnaissance.
- Un numéro d'appel déjà reconnu restait lisible sous sa forme de
  confirmation abrégée lorsqu'il n'était mentionné ailleurs dans le même
  document que par ses quatre derniers chiffres (« erreichbar unter der
  Nummer ...5678 », « Rückruf unter ...5678 ») – la même forme que pour
  l'IBAN et la carte de crédit.
- Un numéro de carte de crédit déjà reconnu restait lisible sous sa forme
  de confirmation abrégée lorsqu'il n'était mentionné ailleurs dans le
  même document que par ses quatre derniers chiffres (« Ihre Kreditkarte
  endet auf ...0366 ») – la même forme habituelle dans les confirmations
  de paiement que pour l'IBAN.
- Un IBAN déjà reconnu restait lisible sous sa forme de confirmation
  abrégée lorsqu'il n'était mentionné ailleurs dans le même document que
  par ses quatre derniers chiffres (« Die IBAN endet auf ...3201 ») – une
  forme habituelle dans les e-mails de confirmation.
- Un orateur dans un chat ou un procès-verbal de séance restait inaperçu
  lorsqu'une formule de politesse précédait son nom (« Herr Bauer: … »,
  « Frau Koch: … ») – et touchait ainsi souvent aussi la ligne d'orateur
  suivante dans le même procès-verbal, car trop peu de lignes reconnues
  restaient pour même considérer le document comme un procès-verbal.
- Une date de naissance restait inaperçue lorsque le mot de champ
  « geboren » se trouvait APRÈS la date au lieu d'avant (« Das Kind wurde
  am 14.01.2026 geboren ») – ainsi formule par exemple une attestation de
  congé parental ou de protection de la maternité la date de naissance de
  l'enfant. Les modèles précédents supposaient toujours le mot de champ
  avant la date.
- Un libellé de formulaire avec un signe de réaction ou une coche
  directement devant (« Ansprechpartner 😊: », « Kontaktperson ✓: ») n'était
  plus reconnu comme libellé, et le nom en dessous ou à côté restait de ce
  fait en partie seulement incomplètement trouvé (p. ex. seulement le nom
  de famille pour « Mayer Roman »).
- La même lacune touchait aussi les données particulièrement dignes de
  protection selon l'art. 9 du RGPD (religion, santé, syndicat) : un signe
  de réaction directement avant le séparateur ou le saut de ligne
  (« Konfession 😊: römisch-katholisch ») faisait entièrement échouer le
  libellé, et la donnée restait complètement inaperçue.
- Une adresse avec un nom de lieu double à trait d'union (p. ex.
  « 79761 Waldshut-Tiengen », « 78050 Villingen-Schwenningen ») perdait
  entièrement le code postal, bien que le lieu lui-même soit reconnu et
  caviardé – sur une carte grise ou une lettre, le code postal restait
  ainsi lisible.
- Une colonne de tableau sans espacement de colonne (véritable extrait de
  texte PDF) pouvait, sous une colonne de noms, caviarder à tort deux
  majuscules se trouvant côte à côte par hasard comme une personne, par
  exemple deux noms de lieu dans une ligne de données ; ce n'est désormais
  plus le cas que lorsqu'aucun autre résultat au même endroit ne reconnaît
  déjà autre chose.
- La même colonne de noms caviardait, dans la même forme de ligne, aussi
  deux mots factuels inconnus du modèle de langue (p. ex. « Frontend
  Backend », « Turbo Modul ») à tort comme une personne, car aucun autre
  résultat ne déclenchait le frein à cet endroit ; elle exige désormais en
  plus qu'au moins l'un des deux mots soit lu par le modèle de langue
  lui-même comme nom propre.
- Le numéro d'assurance retraite allemand n'était pas reconnu dans son
  groupement officiel complet (p. ex. « 65 170839 J 08 8 » – tel qu'il
  figure sur la carte d'assurance sociale et le bulletin de salaire) et
  restait dans l'original ; seules l'écriture compacte et la forme
  groupée seulement jusqu'à la lettre étaient reconnues.
- Le numéro d'identification fiscale n'était pas du tout reconnu dans son
  écriture officielle (groupement 2-3-3-3, p. ex. « 48 836 075 988 » –
  tel qu'il figure sur chaque avis fiscal réel et chaque courrier de
  l'Office fédéral central des impôts) et restait dans l'original ; seul
  le groupement plus rare 3-3-3-2 était couvert.
- Le numéro fiscal de Rhénanie-du-Nord-Westphalie (p. ex.
  « 221/5147/0815 », avec un second groupe à quatre chiffres au lieu de
  trois) n'était pas du tout reconnu dans les avis fiscaux et restait
  dans l'original – chaque autre Land était déjà couvert.
- Dans les contrats de travail, un nom derrière le libellé
  « Arbeitgeber: » était totalement manqué dès que le nom de famille était
  en même temps un mot ordinaire (p. ex. « Bauer Anna ») – « Arbeitgeber »
  figure dans la liste à la fois comme libellé de nom et comme libellé
  d'entreprise, et l'attribution d'entreprise écrasait l'attribution de
  nom.
- Dans un en-tête de contrat de bail avec les libellés « Vermieter: »/
  « Mieter: », un nom de famille qui est en même temps un mot ordinaire
  (p. ex. « Bauer ») était manqué – seul le prénom restait reconnu. Les
  parties locataires numérotées (« Mieter 1: », « Mieter 2: ») étaient en
  outre concernées, même pour des noms sans cette ambiguïté.
- Dans un procès-verbal judiciaire avec les libellés « Zeuge: »/
  « Kläger: »/« Beklagter: » (aussi avec numérotation, « Zeuge 1: »,
  « Zeuge 2: »), un nom de famille qui est en même temps un mot ordinaire
  (p. ex. « Bauer ») était de même manqué – seul le prénom restait
  reconnu.
- Pour un certificat d'héritier, une procuration, une procédure d'injonction
  de payer et un contrat de vente, un nom de famille qui est en même temps
  un mot ordinaire (p. ex. « Bauer ») était manqué derrière des libellés
  comme « Erblasser: », « Erbe: », « Vollmachtgeber: »,
  « Bevollmächtigte:r », « Antragsgegner: », « Schuldner: », « Gläubiger: »,
  « Käufer: », « Verkäufer: », « Vermächtnisnehmer: » ou
  « Testamentsvollstrecker: » – en partie seul le prénom restait reconnu,
  en partie tout le nom disparaissait.
- Dans une liste à plusieurs parties avant le séparateur d'intitulé
  « ./. » (p. ex. « Sand, Werner und Huber, Anna ./. Wechsler, Martina »),
  la première partie restait non masquée – seule la partie immédiatement
  adjacente à « ./. » était reconnue.
- Dans le séparateur d'intitulé « ./. » (p. ex. « Sand./.Wechsler »), le
  nom après le signe était totalement manqué lorsqu'il n'y avait pas
  d'espace – la reconnaissance ne fonctionnait qu'avec un espace avant et
  après.
- Le nom de famille « Wahr » était totalement manqué lorsqu'il était seul
  (p. ex. « Frau Wahr bearbeitet Ihren Vorgang. ») – le mot figure par
  hasard aussi dans la liste des mots allemands ordinaires qui filtre
  sinon les résultats de nom issus de phrases comme « Das ist wahr. ».
- Des noms de famille comme « Los », « Weit », « Rund » ou « Hoch »
  étaient totalement manqués lorsqu'ils étaient seuls (p. ex. « Herr Hoch
  übernahm die Leitung. ») – les quatre mots figurent par hasard aussi
  dans la liste des mots allemands ordinaires qui filtre sinon les
  résultats de nom issus de phrases comme « Rund einhundert Gäste kamen
  zur Feier. ».
- Des noms de famille comme « Ganz » ou « Recht » étaient totalement
  manqués lorsqu'ils étaient seuls (p. ex. « Herr Ganz unterschrieb den
  Vertrag. ») – les deux mots figurent par hasard aussi dans la liste des
  mots allemands ordinaires qui filtre sinon les résultats de nom issus
  de phrases comme « Ganz genau, das stimmt. ».
- Un champ de formulaire avec un astérisque ou un chiffre de note en
  exposant derrière le libellé (p. ex. « Konfession*: römisch-katholisch »
  ou « Religionszugehörigkeit¹: evangelisch ») n'était pas reconnu et
  restait en clair – seule la forme sans ce signe fonctionnait.
- Le même champ restait de même en clair lorsque deux signes de note se
  trouvaient derrière le libellé (p. ex. « Konfession**: römisch-
  katholisch » ou « Gewerkschaft¹²: ver.di »).
- Un numéro de version comme « Softwareversion 4.2.1.19 » ou « Firmware
  Build 2.0.4.11 » n'est plus caviardé à tort comme adresse IP. Il en va
  désormais de même pour des numéros de pièce et de dossier comme
  « Rechnungsnummer 10.20.30.40 » ou « Bestellnummer 7.8.9.10 ».
- Deux IBAN directement l'un sous l'autre (p. ex. le sien et celui d'un
  partenaire commercial étranger dans l'en-tête de facture) n'étaient plus
  tous deux reconnus – le second restait inaperçu.
- Un IBAN libellé entraînait parfois le mot suivant dans la phrase
  (« Bankverbindung AT61 … wird belastet » était caviardé jusqu'à « wird »
  inclus), dès que le mot suivant était en minuscules – le reste en clair
  à côté restait alors intact.
- Les adresses du Liechtenstein sont désormais reconnues (« FL-9490
  Vaduz »), comme déjà auparavant les allemandes, autrichiennes et
  suisses.
- Le numéro de passeport est désormais reconnu et retiré derrière son
  libellé (p. ex. « Reisepassnummer: C01X00T471 »).
- Le numéro de titre de séjour et d'attestation d'enregistrement sont
  désormais reconnus et retirés derrière leur libellé.
- Un numéro d'identification derrière son libellé est désormais aussi
  reconnu lorsqu'un tiret cadratin sépare au lieu de deux-points (p. ex.
  « Kundennummer – K903944 »).
- Une coordonnée bancaire libellée « IBAN » ou « Kontonummer » est
  désormais aussi reconnue lorsqu'un tiret cadratin sépare au lieu de
  deux-points.
- Un nom derrière un libellé comme « Kontaktperson (Vertrieb) » ou
  « Sachbearbeiter/in » est désormais aussi reconnu avec ajout entre
  parenthèses ou terminaison à barre oblique non genrée.
- La même forme genrée à astérisque (« Sachbearbeiter*in ») est désormais
  également reconnue.
- Un nom derrière un libellé est désormais aussi reconnu lorsqu'un signe
  égal sépare au lieu de deux-points (p. ex. « Ansprechpartner = Mayer
  Roman » ou « Kontaktperson=Mayer Roman »), comme c'est habituel dans les
  fichiers de configuration ou les en-têtes CSV. Si plusieurs paires
  libellé-valeur de ce type se trouvent séparées par un point-virgule sur
  une ligne, seule la première valeur est désormais reconnue au lieu de
  toute la ligne restante.
- Une paire de coordonnées GPS derrière le mot « Koordinaten » est
  désormais reconnue de manière fiable (p. ex. « Koordinaten: 48.2082,
  16.3738 ») – le mot portait la mauvaise forme de flexion dans le
  catalogue interne.
- Un numéro d'identification derrière son libellé (numéro de client, de
  contrat, dossier, numéro de carte d'identité et une centaine d'autres
  mots de champ) n'était plus reconnu dès que le libellé ne figurait pas
  exactement dans la casse enregistrée – « kundennummer: » dans un e-mail
  ou « KUNDENNUMMER: » dans un en-tête de formulaire restaient intacts.
### Nouveau

- **Des valeurs de remplacement réalistes sont désormais un exemple
  volontairement utilisé plutôt qu'un réglage par défaut.** Le tableau
  d'exceptions dans l'onglet « Placeholders » commence vide. Un nouveau
  bouton y inscrit sur demande des fausses valeurs plausibles pour nom,
  lieu, adresse, organisation, e-mail, téléphone, poste et IBAN. Il laisse
  explicitement les montants d'argent au placeholder numéroté ; la
  stratégie « inventer » reste par ailleurs sélectionnable à la main pour
  certains types.
- **Le niveau IA peut utiliser la carte graphique.** Sous Windows, un
  petit paquet complémentaire d'environ 17 Mo peut être rechargé pour
  cela ; ensuite, le niveau IA calcule nettement plus vite sur une carte
  graphique adaptée que sur le processeur. Qui n'en a pas ou ne recharge
  rien continue de travailler sans changement – simplement plus lentement.
  Sur macOS, l'accélération est de toute façon déjà intégrée.
- **Deux nouvelles notifications via l'icône de la barre des tâches** :
  lorsque l'aperçu avant le remplacement est prêt à être examiné et
  lorsqu'un traitement est terminé. Les deux sont activées par défaut et
  peuvent être désactivées individuellement sous *Réglages → Programme →
  Notifications*.

### Modifié

- **Le numéro de carte d'identité et de permis de conduire sont désormais
  reconnus** lorsque leur libellé les précède (« Personalausweisnummer: …»,
  « Führerscheinnummer: … ») – jusqu'ici, les deux échappaient à toute
  reconnaissance.
- **Maskuro suit désormais les thèmes de contraste de Windows.** Qui a
  activé l'un d'eux sous *Réglages → Accessibilité → Thèmes de contraste*
  l'obtenait jusqu'ici partout sauf ici : Maskuro appliquait ensuite ses
  propres couleurs. Désormais, le thème du système est conservé –
  fenêtre, listes, zone de dépôt, journal et couleurs d'état. Le feu
  tricolore de contrôle coloré dans l'aperçu et la fenêtre de reprise
  disparaît alors volontairement ; ce qu'il signifie figure de toute façon
  depuis longtemps comme signe et comme mot à côté.
- **Le besoin de contrôle ne repose plus seulement sur la couleur.** Rouge,
  orange et vert sont presque de la même luminosité – qui a une
  daltonie rouge-vert voyait dans l'aperçu et le panneau de résultats une
  liste sans différences, ce qui concerne environ un homme sur douze.
  Chaque ligne porte désormais en plus un signe qui se distingue par sa
  forme : ▲ à vérifier en premier, ● à vérifier, ○ bien étayé, ◆ sans
  évaluation. L'info-bulle le nomme en mots, et un lecteur d'écran le lit
  à voix haute.
- **Alt ouvre de nouveau les menus comme d'habitude.** La barre de menu
  n'avait pas de raccourcis clavier : qui n'utilise pas la souris devait
  naviguer dans chaque menu avec les flèches. Chaque entrée porte
  désormais une lettre soulignée – Alt+D pour « Datei », de là B pour
  « Beenden » –, et ce dans toutes les langues de l'interface.
- **Les éléments de commande indiquent de nouveau à un lecteur d'écran à
  quoi ils servent.** Dans la fenêtre de reprise, la fenêtre de règles, le
  journal, les listes de mots, l'aide, la recherche en lot et cinq autres
  fenêtres, les listes, champs de recherche, listes déroulantes et
  curseurs n'étaient jusqu'ici annoncés que comme « arbre » ou « champ
  combiné » – sans préciser de quoi. Environ quarante emplacements portent
  désormais un nom. (La fenêtre principale était en ordre depuis août ;
  les fenêtres ajoutées ensuite n'avaient jamais suivi ce pas.)
- **Qui utilise le clavier voit partout où il se trouve.** Sur les
  curseurs de besoin de contrôle, la case à cocher et le bouton « plus
  jamais » de l'aperçu, sur les titres de type qui s'y trouvent, sur le
  panneau des pages de la fenêtre de reprise et sur la barre latérale des
  réglages, il manquait le cadre que le système dessine sinon autour de
  l'élément de commande atteint.
- **Une plus grande police système ne coupe plus rien.** Qui règle plus de
  175 % sous *Accessibilité → Taille du texte* perdait jusqu'ici la fin des
  libellés dans la surveillance de dossier et les champs de raccourci
  clavier. La liste des chapitres de l'aide coupait déjà les longs noms de
  chapitre avec une police ordinaire ; elle les fait désormais passer à la
  ligne et nomme le nom complet dans l'info-bulle.

- **La reconnaissance est devenue nettement plus rapide.** Le
  reconnaisseur pour les numéros d'identification libellés
  (« Kundennummer: K903944 ») vérifiait jusqu'ici plus de 1200 motifs
  individuels l'un après l'autre par segment de texte – c'était le plus
  gros poste isolé du temps de reconnaissance, à chaque paragraphe et
  chaque cellule de tableau. C'est désormais un motif unique avec le même
  résultat : sur le corpus de mesure, pas un seul résultat ne change, le
  niveau de base par segment de texte devient environ trois à quatre fois
  plus rapide.
- **La fenêtre apparaît immédiatement au démarrage.** Jusqu'ici, la
  fenêtre principale chargeait les outils linguistiques complets avant
  même de s'afficher – environ quatre secondes de temps aveugle à chaque
  démarrage. Les modèles se chargent désormais comme prévu en
  arrière-plan, pendant que la fenêtre est déjà affichée ; le bouton
  Nettoyer ne devient libre, comme avant, que lorsque tout est prêt. Même
  les simples appels d'information de la ligne de commande (par exemple
  `--version`) répondent désormais immédiatement au lieu d'après plusieurs
  secondes.
- **Les images ne sont plus lues qu'une seule fois en reconnaissance
  automatique de langue.** Jusqu'ici, la reconnaissance de texte
  s'exécutait deux fois sur la même image avec le réglage par défaut
  « Langue : automatique » – une fois pour la détection de langue, une
  fois pour le contrôle proprement dit. Les fichiers image, les images du
  presse-papiers et la fenêtre de texte sont ainsi environ deux fois plus
  vite terminés ; avec la reconnaissance de texte désactivée, la lecture
  qui s'exécutait jusqu'ici quand même sans qu'on le remarque disparaît
  entièrement.
- **Les pages web enregistrées et les e-mails sont nettoyés plus vite.**
  Les valeurs dans les attributs HTML, les commentaires et les blocs de
  données intégrés étaient jusqu'ici reconnues individuellement – une page
  communale avec des centaines de libellés posait des centaines de
  questions individuelles à la reconnaissance. Elles sont désormais
  regroupées et reconnues une seule fois par valeur différente ; sur le
  corpus de mesure, aucun résultat ne change, .html et .eml sont environ
  un tiers plus rapides.
- **Les emplacements secondaires des tableaux et présentations sont
  également reconnus de manière groupée.** Textes alternatifs, chaînes de
  formule, libellés de graphique, commentaires, mémoires intermédiaires de
  tableau croisé dynamique et propriétés de document posaient chacun leur
  propre question de reconnaissance par valeur – un classeur avec des
  milliers de lignes de tableau croisé dynamique en conséquence des
  milliers. Un passage groupé s'exécute désormais sur les valeurs
  différentes, et le passage complet de reprise à la fin ne s'exécute plus
  que si de nouvelles valeurs se sont réellement ajoutées depuis le texte
  courant. Sur le corpus de mesure, aucun résultat ne change.
- **Les PDF riches en formulaires sont nettoyés plus vite.** Champs,
  notes, signets et renvois répètent les mêmes valeurs en masse (« Off »
  sur chaque case à cocher, le même auteur sur chaque annotation) –
  chacun posait jusqu'ici sa propre question de reconnaissance. Une
  valeur n'est désormais reconnue qu'une seule fois par passage ; le
  remplacement et le passage de cohérence continuent de s'exécuter sans
  changement par emplacement.
- **Les grands fichiers de tableau (.csv/.tsv) sont nettoyés nettement
  plus vite.** Les quatre passages de reprise sur les tableaux
  décomposaient jusqu'ici chacun eux-mêmes le même fichier caractère par
  caractère en cellules (pour 40 Mo, environ 30 s de travail
  supplémentaire) ; la décomposition s'exécute désormais une seule fois.
  La reconnaissance d'en-tête de colonne (colonnes de date de naissance et
  de numéro de personnel) pose une question groupée au lieu d'une par
  cellule – pour des résultats identiques, environ vingt fois plus vite.
  Et le regroupement de colonnes de noms de grandes listes de personnel
  n'est plus quadratique par rapport au nombre de lignes.
- **Le panneau d'indicateurs ne fait plus geler la fenêtre.** Le dépliage
  des indicateurs assemblait d'abord le texte de nombreux gros fichiers et
  faisait ainsi rester la fenêtre figée pendant des secondes. Le calcul
  s'exécute désormais en arrière-plan ; le panneau s'ouvre immédiatement
  et rattrape les chiffres après coup.
- **Le rapport de recherche en lot ne fait plus geler la fenêtre.** Après
  la recherche dans plusieurs milliers de fichiers, le dossier commun était
  recalculé pour chaque fichier concerné ; pour de grands lots, la fenêtre
  restait figée pendant des dizaines de secondes. Le rapport apparaît
  désormais immédiatement.
- **Les PDF avec reconnaissance de texte sont vérifiés plus vite.** Chaque
  page était inutilement convertie deux fois au format PNG lors du
  contre-lecture ; désormais, l'image déjà disponible est transmise. Le
  résultat est inchangé, seul le contrôle s'exécute plus rapidement.
- **Les annotations à dégradé sur de grandes images ne saccadent plus.**
  Lors du déplacement des poignées d'une annotation à dégradé, le dégradé
  était jusqu'ici recalculé point par point – sur une grande capture
  d'écran, un ralentissement visible. Le résultat est le même, simplement
  sans la pause.

### Corrigé

- **La croix pour retirer un fichier de la liste est de nouveau un simple
  X.** Le nouvel outil d'éditeur « Retirer » avait par mégarde utilisé le
  même identifiant de symbole et affichait ainsi aussi sa croix rouge
  avec ligne de texte en pointillé dans chaque ligne de fichier. Les deux
  actions possèdent désormais des noms de symbole distincts et conservent
  chacune leur représentation appropriée.
- **Les données à plusieurs parties sont désormais reconnues dans les PDF
  même par-delà un saut de ligne visible.** Maskuro lit désormais le texte
  de page généré géométriquement également comme une vue de texte courant
  à décalage identique. Cela vaut pour tous les reconnaisseurs de niveau
  de base et niveau élevé ainsi que pour les motifs de recherche
  personnels, pas seulement pour le cas initialement visible « Diabetes
  mellitus Typ 2 ». Les lignes vides et les limites de tableau ou de
  section reconnues restent des limites strictes ; les résultats
  continuent de s'ajuster exactement sur les mots à caviarder.
- **L'exemple de « Pseudonymiser » se contredisait lui-même.** La phrase
  promettait « même personne, même numéro » et montrait ensuite deux
  numéros différents – exactement l'image qui est correcte pour
  « Anonymiser ». Les deux exemples correspondent désormais à leur propre
  phrase.
- **Un placeholder fraîchement inséré pouvait, lors de « Récupérer
  l'original », rester sous forme de bouillie de caractères superposés au
  lieu de disparaître.** Un placeholder posé en une seule couleur écrivait
  jusqu'ici sa propre commande de sortie par caractère, dont seule la
  première portait une matrice de texte propre – lors de la modification
  suivante du même emplacement (par exemple « récupérer » juste après),
  les autres commandes de caractère se voyaient attribuer tour à tour les
  indices de caractère du premier, et le placeholder se décomposait en
  deux positions superposées. Un placeholder unicolore reçoit désormais
  une seule commande de sortie pour tout son texte.

- **Si la même valeur caviardée ou retirée figurait sous deux lignes dans
  la fenêtre de reprise et que les deux étaient marquées pour l'annulation,
  la seconde ligne comptait à tort comme « non univoque » – alors que la
  valeur avait déjà été récupérée depuis longtemps.** Les deux lignes
  comptent désormais comme accomplies.

- **Le nom après « Reply-To: » est désormais trouvé.** Dans un en-tête
  d'e-mail comme « Reply-To: Huber », le nom restait jusqu'ici totalement
  inaperçu – le modèle de langue lisait « Reply-To: » comme une personne
  propre, erronée, et manquait le véritable nom qui suivait.

- **Les mots d'en-tête d'e-mail « Reply » et « Fwd » ne sont plus
  eux-mêmes caviardés comme un nom.** Dans une ligne d'objet comme « Fwd:
  Angebot von Huber », le mot d'en-tête lui-même était jusqu'ici en plus
  du nom reconnu et caviardé comme une personne.

- **« Arbeitgeber: Siemens AG » est désormais reconnu comme entreprise, et
  non plus comme personne.** Si la valeur d'entreprise derrière le libellé
  « Arbeitgeber » portait une forme juridique comme GmbH, AG ou KG, elle
  restait un résultat de personne malgré la reconnaissance d'organisation
  activée – seul le cas plus étroit sans forme juridique (« Wollmuth und
  Partner ») était jusqu'ici reconnu comme entreprise.
- **Une adresse une fois reconnue ne reste plus en place à un autre
  endroit.** Si une adresse de rue était reconnue et remplacée à un
  endroit, la même adresse pouvait rester à un second endroit – par
  exemple dans un pied de page difficile à lire d'un document numérisé, où
  la reconnaissance de texte automatique la lisait de façon mutilée. Les
  adresses sont désormais, comme les noms et entreprises depuis plus
  longtemps déjà, retirées de manière cohérente dans tout le document.

- **Les e-mails avec plusieurs destinataires étaient silencieusement
  endommagés lors du nettoyage.** Un message `.msg` avec deux
  destinataires ou plus perdait à l'enregistrement des parties de sa
  structure interne, si bien que le résultat nettoyé était incomplet. La
  cause était une confusion entre des composants internes portant le même
  nom, qui apparaissent pour chaque destinataire. De tels messages sont
  désormais reconstruits intégralement.

- **Deux des documents de test fournis ne pouvaient pas être ouverts dans
  Word et PowerPoint.** Qui téléchargeait le corpus de mesure obtenait
  pour `format_dokument.docx` « Erreur à l'ouverture du fichier dans
  Word » et pour `format_praesentation.pptx` « Le fichier est
  endommagé ». Les deux fichiers étaient déjà défectueux avant que
  Maskuro ne les touche – la version nettoyée ne faisait que transmettre
  l'erreur. LibreOffice ouvrait les deux sans problème, c'est pourquoi
  personne ne l'avait remarqué.

- **Une IA personnelle sur Internet est désormais contactée de manière
  chiffrée.** Qui inscrit pour sa propre IA une adresse externe sans
  « https:// » (comme elle figure souvent sur le papier de l'informatique)
  l'atteignait jusqu'ici via une connexion non chiffrée – le texte non
  caviardé partait en clair. De telles adresses sont désormais contactées
  via « https:// » ; un serveur sur son propre réseau reste accessible
  sans changement. Si le serveur suit une redirection vers une autre
  machine, la clé d'accès ne voyage plus avec.

- **Même une image endommagée perd désormais ses métadonnées cachées.**
  Si une image intégrée ne pouvait plus s'ouvrir complètement (par exemple
  une photo tronquée), elle conservait jusqu'ici ses données EXIF et GPS –
  lieu de prise de vue et nom du photographe restaient invisibles dans le
  résultat. De telles images sont désormais libérées de ces données même
  lorsqu'elles ne peuvent plus du tout être affichées.

- **Un fichier intégré qui n'a pas pu être nettoyé est désormais signalé
  au lieu d'être transmis silencieusement.** Si une présentation ou un
  classeur contenait un objet intégré trop profondément imbriqué ou
  impossible à ouvrir, il restait jusqu'ici inchangé dans le résultat,
  sans indication – le fichier passait pour nettoyé. De tels cas figurent
  désormais dans l'avertissement « n'ont PAS pu être vérifiés », tout
  comme un ancien format intégré.

- **Les listes sombres sont de nouveau uniformément sombres et
  lisibles.** Sur macOS, les listes de fichiers alternaient entre lignes
  presque noires et gris clair ; dans la reprise, la même valeur de
  contrôle verte, orange ou rouge apparaissait ainsi différemment selon
  la ligne. Fenêtre, listes, police, placeholders et sélection proviennent
  désormais d'une palette claire/sombre commune. La liste de résultats
  codée par couleur ne pose en outre plus de rayures zébrées sous ses
  couleurs.

- **Les désignations de profession avec « als » étaient caviardées à tort
  comme un nom.** Une phrase comme « Als Koch ist er seit vier Jahren bei
  uns tätig. » perdait le métier, pas seulement un nom – « als » introduit
  une indication de rôle tout comme « der » ou « die ». Les véritables
  noms de famille au même endroit (p. ex. avec une formule de politesse
  devant) restent inchangés.

- **Un en-tête de tableau pouvait entraîner un numéro de position dans un
  montant d'argent** (uniquement avec l'option « Retirer aussi les
  montants d'argent » activée). Si une ligne se terminait par une devise
  (« … Einzelpreis EUR ») et que la suivante commençait par un nombre, cela
  devenait à tort un montant par-delà le saut de ligne. Le séparateur
  entre devise et nombre reste désormais sur la même ligne.

- **Une courte abréviation en majuscules pouvait engloutir toute une
  partie de phrase, ou s'accrocher devant un nom correctement reconnu.**
  Si une ligne contenait un mot en majuscules à deux lettres comme « DI »,
  « AG » ou « KG » – des abréviations courantes, pas des noms –, toute la
  ligne était parcourue à titre d'essai en minuscules, et l'abréviation
  entraînait parfois des mots voisins (même des verbes) dans un seul
  prétendu nom. Un mot en majuscules ne déclenche désormais cette seconde
  vérification qu'à partir de trois lettres. Pour des sigles un peu plus
  longs comme « CEO » ou « USB », une seconde erreur subsistait : le nom
  déjà correctement trouvé (« Schneider ») se voyait attribuer le sigle
  précédent comme préfixe dans le résultat (« CEO Schneider »). Le sigle
  reste désormais à l'écart.

- **Une date de naissance sans espace derrière restait en place.** Si
  aucun espace ne séparait « geb. » de la date – comme c'est habituel dans
  les formulaires composés de manière serrée (« geb.14.03.1988 ») –,
  Maskuro ne reconnaissait pas le champ et laissait la date intacte. Des
  formes abrégées courantes comme « Geburtsdat. » ou « Geb.-Dat. » sont
  désormais également reconnues.

- **Un IBAN avec des barres obliques comme séparateurs restait en place.**
  Comme pour les numéros de téléphone (« 0664/1234567 »), certains
  modèles écrivent aussi l'IBAN en blocs avec barre oblique
  (« AT48/3200/0000/1234/5864 ») au lieu d'espace ou de trait d'union.
  Cette écriture est désormais également reconnue.

- **Un numéro de sécurité sociale autrichien avec trait d'union, point ou
  barre oblique restait en place ou était mal libellé.** Seul un espace
  était jusqu'ici prévu entre les deux blocs de chiffres ; des écritures
  comme « 1237-010180 », « 1237.010180 » ou « 1237/010180 » n'étaient pas
  reconnues (ou, dans le cas de la barre oblique, sous le mauvais type).
  Le chiffre de contrôle confirme toujours chaque résultat, indépendamment
  du séparateur.

- **Un nom derrière « c/o » dans une adresse n'était pas du tout
  retiré.** « c/o Max Mustermann, Hauptstraße 5, 1010 Wien » caviardait la
  rue et la localité, mais laissait le nom derrière totalement en place.
  Le nom est désormais reconnu ; « c/o » lui-même reste visible comme
  indication d'adresse.

- **Un numéro de carte de crédit groupé avec des points restait en
  place.** Des écritures comme « 4111.1111.1111.1111 » n'étaient pas
  reconnues ; les numéros séparés par espace ou trait d'union n'étaient
  pas concernés. La somme de contrôle confirme toujours chaque résultat.

- **Un numéro d'identification fiscale groupé avec des traits d'union
  restait en place, de même qu'un numéro de TVA autrichien avec trait
  d'union ou point.** Espace, barre oblique et point étaient déjà prévus
  pour l'identifiant fiscal, le trait d'union manquait ; pour le numéro de
  TVA (« ATU12345678 »), trait d'union et point manquaient après le
  préfixe. Le chiffre de contrôle de l'identifiant fiscal confirme
  toujours chaque résultat.

- **Une valeur de champ entre guillemets restait en place, par exemple
  dans une ligne de type JSON comme « vorname »: « Max ».** La
  reconnaissance via un libellé de champ (« Vorname: … ») supposait
  jusqu'ici que ni le libellé ni la valeur elle-même ne soient entre
  guillemets. De telles lignes sont désormais également reconnues – de
  même que des libellés de champ avec un point de liste YAML devant
  (« - Vorname: Max ») ou une tabulation au lieu d'un espace avant les
  deux-points.

- **Le mot d'en-tête d'e-mail « Sent » était lui-même caviardé comme un
  nom.** Dans un en-tête comme « Sent: Huber », cela touchait jusqu'ici à
  la fois « Sent » et le véritable nom ; des mots d'en-tête apparentés
  comme « Subject » ou « Betreff » n'étaient jamais concernés. « Sent »
  reste désormais également en place.

- Un nom derrière les en-têtes « Errors-To: » ou « Resent-From: » restait
  inaperçu lorsqu'une telle ligne était copiée en clair (par exemple un
  message transféré ou un rapport d'incident) – contrairement à
  « Reply-To: » ou « Return-Path: », le nom disparaissait ici entièrement
  au lieu d'être seulement imprécisément délimité. Il est désormais
  trouvé.
- Un seul et même fichier donnait parfois un résultat différent lors de
  deux nettoyages : lorsque deux reconnaissances touchaient exactement le
  même emplacement avec la même longueur et la même confiance (p. ex.
  « Sozialversicherungsnummer 1237/010180 » comme AT_SVNR ou comme
  numéro d'identification général), c'était le hasard qui décidait
  laquelle l'emportait – la valeur était retirée dans les deux cas, seul
  le libellé du placeholder changeait. L'égalité est désormais toujours
  résolue de la même manière.
- Une désignation de fonction directement devant un substantif (p. ex.
  « Behandelnder Arzt: Dr. … » ou « Zuständiger Sachbearbeiter ist … »)
  était parfois caviardée à tort comme si elle était elle-même un nom.
  Les véritables noms de famille à côté restent inchangés.
- Un véritable nom de famille qui ressemble par hasard à un adjectif
  (p. ex. « Schöne », « Lange », « Junge ») et se trouve directement
  devant un autre substantif (par exemple « Kontaktperson: Schöne
  Assistentin ») restait, depuis la dernière correction, non caviardé
  dans le texte – une fuite de données. Seule une liste étroitement
  limitée de véritables désignations de fonction (p. ex. « Behandelnder »,
  « Zuständiger ») est désormais traitée comme non-nom dans cette forme.
- Un nom de famille isolé en fin de résultat de nom sur plusieurs lignes,
  qui ressemble par hasard à un adjectif (p. ex. « Schwarz », « Kurz »,
  « Alt », « Frisch », « Gut », « Reich »), restait inaperçu devant des
  deux-points immédiatement suivants – le nettoyage le confondait avec un
  libellé de champ comme « Telefon: ». Une liste fermée de noms de famille
  ambigus connus le protège désormais.
- Un nom de famille isolé qui est par hasard un mot allemand ordinaire
  (« Gross »/« Grosse », « Gut », « Kurz », « Lang »/« Lange ») était
  jusqu'ici **totalement** perdu – même dans des phrases simples comme
  « Herr Gross unterschrieb den Vertrag. » La raison résidait dans la
  liste de mots vides propre à spaCy, qui contient ces mots ; une liste
  fermée de noms de famille connus les protège désormais du rejet.
- Pour les contrats de travail, de prêt, de cautionnement, fiduciaires et
  d'insolvabilité ainsi que de tutelle/curatelle et les mandats
  d'expertise, un nom de famille qui est en même temps un mot ordinaire
  (p. ex. « Bauer ») était manqué derrière des libellés comme
  « Auftraggeber: », « Auftragnehmer: », « Arbeitnehmer: »,
  « Versicherter: », « Darlehensgeber: », « Darlehensnehmer: »,
  « Bürge: », « Sicherungsgeber: », « Treuhänder: », « Treugeber: »,
  « Insolvenzverwalter: », « Gutachter: », « Sachverständiger: »,
  « Vormund: » ou « Pfleger: » – en partie seul le prénom restait
  reconnu, en partie tout le nom disparaissait.
- Dans les mentions légales, un nom de famille qui est en même temps un
  mot ordinaire (p. ex. « Bauer ») était manqué derrière les libellés
  « Geschäftsführer: », « Geschäftsführerin: », « Vertretungsberechtigt: »,
  « Inhaber: » ou « Inhaberin: » – pour « Geschäftsführer: »/« Inhaber: »,
  tout le nom disparaissait, pour « Vertretungsberechtigt: » seul le
  prénom restait reconnu.
- Un bloc de contact dont le libellé se trouvait seul sur sa ligne et
  portait la forme genrée à deux-points (« Ansprechpartner:in », nom
  dessous) était **totalement** manqué – les deux-points étaient lus
  comme séparateur de champ, « in » comme valeur de champ (rejetée), et
  le véritable nom sur la ligne suivante n'était de ce fait jamais pris en
  compte. La forme à astérisque (« Ansprechpartner*in ») n'était pas
  concernée.
- Si le nom et le libellé avec la même forme genrée à deux-points se
  trouvaient sur **une** ligne (« Ansprechpartner:in Anna Berger »), le
  placeholder entraînait le mot « in » dans le remplacement au lieu de ne
  retirer que le nom – le nom lui-même continuait d'être entièrement
  saisi.
- Un nom dans une colonne de tableau sous un en-tête de colonne de
  personne (p. ex. « Name Vorname Geburtsdatum » au-dessus de « Bauer
  Anna 03.05.1985 », comme dans un bulletin de salaire) était totalement
  manqué dès qu'un seul espace séparait les colonnes et qu'aucune ligne
  ne commençait par un numéro de structure – exactement la forme dans
  laquelle un véritable extrait de texte PDF livre de telles lignes.
- Dans un chat ou un procès-verbal de séance avec noms d'orateur avant les
  deux-points (p. ex. « Bauer 🙂: Ich stimme dem Vorschlag zu. »), le nom
  restait totalement inaperçu dès qu'un signe de réaction se trouvait
  entre le nom et les deux-points et que le nom de famille était en même
  temps un mot ordinaire (« Bauer », « Koch », « Schneider » etc.) – un
  procès-verbal entier pouvait ainsi rester sans un seul orateur reconnu.
- La même lacune de ligne d'orateur existait aussi avec d'autres signes
  intermédiaires avant les deux-points : un complément de statut entre
  parenthèses (« Bauer (Vorsitz): … », « Bauer (abwesend): … »), une heure
  entre crochets (« Bauer [14:32]: … ») et un signe de note directement
  accolé au nom (« Bauer*: … »). Là aussi, l'orateur restait totalement
  inaperçu dès que le nom de famille était en même temps un mot ordinaire.
- Si une personne déjà reconnue figurait en plus, dans un extrait de
  procès-verbal ou de journal joint au même message (par exemple un
  ticket d'assistance), comme nom d'utilisateur sous la forme
  « vorname.nachname » – en minuscules, sans espace, reliée par un point
  –, ce nom en clair restait lisible, bien que le même nom soit déjà
  caviardé dans le courrier.
- La même lacune de nom d'utilisateur existait aussi avec un trait de
  soulignement au lieu d'un point (« vorname_nachname ») – un format tout
  aussi répandu dans les extraits de procès-verbal et de journal.
- Et même dans l'ordre inverse, le nom d'utilisateur restait lisible
  (« nachname.vorname », respectivement « nachname_vorname ») – certains
  systèmes placent le nom de famille en tête dans le nom d'utilisateur du
  journal au lieu de le mettre en fin.
- Une date de décès restait inaperçue lorsqu'aucune autre donnée ne se
  trouvait à côté (« Herr Bauer ist am 12.03.1985 verstorben ») – il
  n'existait jusqu'ici aucune reconnaissance propre pour cela, et la date
  générique ne s'applique pas à ce seuil standard.
- Une date de décès restait aussi inaperçue lorsque la phrase utilisait la
  forme verbale au lieu du participe (« Frau Meier verstarb am
  12.03.1985 », « Er starb am 12.03.1985 ») – seul « ist … verstorben »/
  « ist … gestorben » fonctionnait jusqu'ici.
- Une date de mariage restait inaperçue, quelle que soit la forme sous
  laquelle elle se présentait (« Eheschließung am 12.03.2010 »,
  « Hochzeitsdatum: 12.03.2010 », « Herr und Frau Bauer heirateten am
  12.03.2010 ») – il n'existait jusqu'ici aucune reconnaissance propre
  pour cela, et la date générique ne s'applique pas à ce seuil standard.

- **Dans l'éditeur de reprise, un second cadre au-dessus d'un placeholder
  tout juste posé pouvait laisser un reste de caractère rouge**, par
  exemple « [G » au lieu de « [BEG1] » – sans aucun avertissement, car le
  reste n'appartenait plus à la donnée confidentielle (déjà retirée au
  premier passage), mais seulement au placeholder lui-même. La raison
  résidait dans la coloration : un placeholder nouvellement posé était
  écrit caractère par caractère dans le fichier, même avec une couleur
  unie par défaut – un cadre ultérieur au même endroit ne trouvait alors
  plus de texte cohérent où se situer. Un placeholder unicolore se trouve
  désormais comme un seul bloc dans le flux, comme l'a toujours fait le
  nettoyage automatique ; seul un véritable dégradé ou texte arc-en-ciel a
  encore besoin de caractères individuels. La contre-vérification
  intégrée reconnaît en outre désormais un tel reste même lorsque la
  chaîne exacte du placeholder n'apparaît plus.
- Une liste de noms numérotée avec numérotation hiérarchique échelonnée
  (« 1.1 Max Mustermann », « 1.2 Huber Franz » …) perdait tous les noms au
  même frein qui ne doit en réalité protéger que les véritables structures
  et listes de positions – sans en-tête de colonne au-dessus de la liste,
  il n'y avait aucun témoin auquel un nom aurait pu se raccrocher.
- Un nom dans une ligne de connexion anglaise d'un journal système
  (« Accepted password for Max Mustermann from 10.0.0.5 port 51000 ssh2 »)
  n'était pas reconnu – le modèle de langue allemand ne le trouvait que si
  « invalid user » précédait, sinon il restait en place. De tels extraits
  de journal sont souvent joints sans modification à un rapport
  d'incident. Les noms derrière « for » avant une adresse IP sont
  désormais reconnus de manière fiable.
- Le nom du débiteur dans la référence de mandat SEPA d'un relevé de
  compte ou d'un journal comptable (p. ex. « MREF+Mustermann Klaus+SVWZ+
  Miete August ») restait ouvert – pas d'espace, pas de structure de
  phrase, seulement des champs en majuscules séparés par « + », et dans
  l'ordre habituel là-bas « Nachname Vorname », la reconnaissance ne le
  trouvait pas non plus par hasard. Est désormais reconnu.
- La rue avec le numéro dans la première ligne d'un tableau d'adresse
  (p. ex. « Nachname | Vorname | Straße | PLZ | Ort ») restait ouverte –
  le modèle de langue devinait à cet endroit un lieu erroné mais plus
  long, s'étendant sur plusieurs colonnes, qui supplantait le résultat
  d'adresse correct, plus court. Est désormais reconnue.
- La même fuite se produisait avec une tabulation au lieu de « | » ou
  « ; » comme séparateur de colonne – là, l'adresse disparaissait même
  entièrement au lieu de seulement se perdre en partie. Est désormais
  reconnue.
- Une rue avec numéro restait ouverte lorsqu'un code postal avec virgule
  suivait directement sans espace (p. ex. « Bahnhofstrasse 12,80331
  München », comme dans une colonne de tableau séparée par virgules) – la
  virgule ressemblait à une décimale d'une quantité, et la rue ne comptait
  donc pas du tout comme adresse pour le motif. Est désormais reconnue.
- Une rue avec numéro restait ouverte lorsque le préfixe de lieu « St. »
  (Sankt) suivait directement sans virgule (p. ex. « Hauptstraße 5 St.
  Pölten », un en-tête de lettre sans code postal devant) – « St. »
  ressemblait à l'unité de quantité « pièces », et la rue ne comptait donc
  pas du tout comme adresse pour le motif. Est désormais reconnue.
- Un complément de porte/d'escalier après un numéro de rue (p. ex.
  « Lerchenfelder Gürtel 43/12 ») restait visiblement ouvert lorsqu'une
  seule lettre suivait directement, coïncidant par hasard avec une unité
  de mesure (p. ex. « h » pour heure) – l'adresse n'était alors nettoyée
  que jusqu'au numéro de rue sans son complément, au lieu d'être saisie
  entièrement ou pas du tout.
- Une ligne d'objet avec un nom de famille identique à un métier avant le
  prénom (« Betreff: Bauer Anna », « Betreff: Bauer, Anna ») restait
  jusqu'ici totalement inaperçue – même en plein milieu du document avec
  une phrase complète précédente. Est désormais reconnue.
- Un numéro fiscal allemand avec espace, point ou trait d'union entre les
  blocs (p. ex. « Steuernummer: 30 815 08153 » ou « 30.815.08153 »)
  restait jusqu'ici inaperçu – seule l'écriture avec barre oblique était
  trouvée. Est désormais reconnu.
- Un nom derrière un libellé de champ médical (« Patient: », « Hausarzt: »,
  « Behandelnder Arzt: », « Überweisender Arzt: » et leurs formes
  féminines) restait jusqu'ici inaperçu lorsque le nom de famille était en
  même temps un mot allemand ordinaire (p. ex. « Patient: Bauer Thomas »).
  Est désormais reconnu.
- Un nom derrière le libellé de champ « Zahnarzt » sur sa propre ligne
  (p. ex. « Zahnarzt », dessous « Huber Franz ») restait jusqu'ici
  inaperçu – ni le prénom ni le nom de famille. « Zahnärztin » et la
  forme simple « Arzt » n'étaient pas concernées. Est désormais reconnu.
- Un nom de famille derrière « Herr »/« Frau », suivi d'une formule
  administrative comme « zur Kenntnisnahme », « zur Unterschrift » ou
  « zur Weiterleitung », était jusqu'ici saisi de manière trop large et
  entraînait la formule dans le résultat de nom – de « Frau Petra Klein
  zur Vertretung in allen Angelegenheiten » résultait le remplacement de
  « Petra Klein zur Vertretung », et le reste de la phrase restait
  grammaticalement mutilé. Les véritables particules nobiliaires comme
  « von der Leyen » ou « zu Guttenberg » restent inchangées.
- La même sur-rédaction par formule administrative se cachait aussi
  derrière le nom dans un en-tête d'e-mail « To: », un code
  d'immatriculation (C.1/C.1.1/C.1.2), un code de permis de conduire, un
  champ de formulaire entre crochets (« [Vorname]: … ») et une formule de
  salutation sans point – partout là, « zur »/« von » et consorts
  entraînaient une formule suivante comme « zur Unterschrift » ou « zur
  Vertretung » dans le résultat, parfois même le simple mot de particule
  lui-même restait accroché comme reste de nom dans le résultat. Là aussi,
  les véritables particules nobiliaires restent entièrement préservées.
- Le numéro matricule derrière son libellé n'était jusqu'ici pas du tout
  reconnu – « Matrikelnummer 7654321 » échappait entièrement à la
  reconnaissance, ni comme numéro d'identification ni via le modèle de
  langue, car le nombre seul ne porte aucune forme reconnaissable.
- Il en allait de même pour le numéro de participant – « Teilnehmernummer
  4471829 » échappait entièrement, ni comme numéro d'identification ni
  via le modèle de langue.
- Dans un CV, le nom sous le titre de section « Persönliche Daten »
  échappait souvent entièrement ou partiellement à la reconnaissance
  lorsqu'il se trouvait directement dessous sans formule de politesse,
  sous la forme « Nachname Vorname ».
- Il en allait de même pour le titre de section « Kontaktdaten » – là, le
  nom échappait même totalement, pas seulement partiellement.
- Dans une attestation d'enregistrement ou une liste de demande avec une
  colonne regroupée « Name, Vorname » (écriture des services de résidence,
  valeur p. ex. « Mustermann, Max » dans une cellule), le nom échappait
  entièrement à la reconnaissance lorsqu'une autre colonne comme la date
  de naissance suivait.
- Une date de naissance sous la forme habituelle sur la carte d'identité
  et l'attestation d'enregistrement « Geburtsdatum/-ort: 22.07.1978 /
  Rostock » n'était pas reconnue – seule la forme avec virgule
  « Geburtsdatum, Geburtsort: … » fonctionnait.
- « Bürgerservice » et « Bürgerbüro » étaient occasionnellement caviardés
  à tort comme lieu, surtout après un tiret cadratin comme séparateur
  d'énumération (par exemple « Wenden Sie sich an das Bürgerservice –
  Bürgerbüro … »).
- Un numéro d'appel libellé, coupé en son milieu par un saut de ligne
  (par exemple depuis une étroite colonne d'en-tête de lettre ou une
  extraction de texte PDF à la largeur de colonne : « Telefon: 0176
  12\n34567 »), n'était en partie caviardé qu'à moitié – le reste après
  le saut de ligne restait lisible.
- Un numéro d'identification libellé (numéro de client, de membre, de
  contrat et similaires), coupé en son milieu par un saut de ligne (par
  exemple « Kundennummer: K903\n944 » depuis une colonne étroite),
  n'était caviardé qu'à moitié – le reste après le saut de ligne restait
  lisible.
- Un nom avec titre académique devant une désignation professionnelle
  après une virgule (par exemple « Dipl.-Ing. Sabine Roth,
  Projektleiterin ») restait totalement non protégé – la ligne
  ressemblait à un en-tête de colonne tabulaire et était rejetée à tort
  comme contenu factuel.
- Le titre « Dr.-Ing. » (un grade d'ingénieur allemand courant) devant un
  nom n'était pas inclus dans la valeur de personne masquée et restait
  lisible – le même piège de trait d'union que pour « Dipl.-Ing. ».
- Les titres « Dipl.-Kfm. », « Dipl.-Kffr. » et « Dipl.-Psych. » (diplômé
  en commerce/commerciale/psychologie) devant un nom n'étaient pas inclus
  dans la valeur de personne masquée et restaient lisibles – le même piège
  de trait d'union que pour « Dipl.-Ing. » et « Dr.-Ing. ».
- Une adresse MAC dans l'écriture Cisco avec des points au lieu de
  deux-points (p. ex. « aabb.ccdd.eeff », comme l'affichent les journaux
  de commutateur et les tickets d'assistance) n'était pas du tout reconnue
  et restait lisible.
- Un nom de famille derrière « Familie » (p. ex. « Die Familie Gruber
  unterschreibt den Vertrag ») restait, selon la structure de la phrase,
  inaperçu et donc lisible – même avec une particule nobiliaire devant
  (« Familie von der Leyen »).

- Pour une adresse croate sans signe de ponctuation séparateur entre code
  postal+localité et rue+numéro (p. ex. « 10000 Zagreb Ulica Ivana
  Lučića 5 »), le numéro restait non nettoyé.

- Pour une coordonnée de contact lituanienne avec le libellé
  « Kontaktinis asmuo » (p. ex. « Kontaktinis asmuo: Vilkas Jonas »), le
  nom de famille restait inaperçu lorsqu'il était en même temps un
  substantif courant (Vilkas = « loup », Vanagas = « épervier »).

- Un pays de naissance ou de résidence sans autre libellé dans un champ de
  formulaire danois (p. ex. « Fødeland: Tyskland » ou « Bopæl: Tyskland »)
  n'était pas reconnu.

- Un pays de naissance ou de résidence sans autre libellé dans un champ de
  formulaire roumain (p. ex. « Țara: Germania » ou « Țara de reședință:
  Franța ») n'était pas reconnu.

- Un nom d'entreprise sous le libellé de champ lituanien « Darbdavys: »
  ou « Įmonės pavadinimas: » (employeur/entreprise) n'était pas reconnu.

- Un nom d'entreprise sous le libellé de champ russe « Работодатель: » ou
  « Наименование организации: » (employeur/entreprise) n'était pas
  reconnu.

- Une date écrite en toutes lettres avec nom de mois en roumain (p. ex.
  « 31 decembrie 2024 ») n'était pas reconnue.

- Un nom de naissance hongrois derrière l'abréviation « szül. » (p. ex.
  « Nagy Éva (szül. Kovács) ») n'était pas reconnu et restait ouvertement
  lisible.

- Une page de profil HTML enregistrée (ou un e-mail avec une page web
  jointe) pouvait laisser le nom civil non nettoyé lorsqu'il ne figurait
  que dans les champs de profil Open Graph `profile:first_name`/
  `profile:last_name`/`profile:username` – ceux-ci portent le nom
  décomposé au lieu de manière descriptive comme `og:title`, et sont
  désormais également nettoyés.

- Un avis de non-remise (bounce/NDR) portait souvent les en-têtes de
  l'e-mail initialement non distribué (expéditeur, destinataire, objet)
  dans une troisième partie de pièce jointe propre – celle-ci restait
  entièrement intacte dans la version nettoyée. Cette partie est désormais
  nettoyée comme le reste du rapport de livraison.

- L'éditeur individuellement désigné d'une zone protégée dans Word
  (Restreindre la modification → Exceptions, `w:permStart`) restait en
  clair, même lorsque le même nom était depuis longtemps nettoyé dans le
  texte courant. Il est désormais également retiré.

## 0.10.42-alpha.20260827 – 27 août 2026

### Nouveau

- **Des profils de reconnaissance nommés rendent différents cas d'usage
  accessibles en un geste.** Sous *Réglages → Reconnaissance → Ce qui est
  retiré*, la sélection actuelle de catégories et de types peut être
  enregistrée et réappliquée aussitôt via un menu déroulant. Le profil fixe
  *Standard* correspond à l'état de livraison précédent et ne peut pas être
  supprimé. Un profil modifie exclusivement ce qui est retiré ; la langue,
  le type de résultat, le niveau de reconnaissance ainsi que les termes et
  motifs de recherche personnels restent inchangés.

- **Le type de résultat se choisit désormais directement avant le
  nettoyage.** Un champ de sélection commun dans la fenêtre principale
  définit pour tout le lot si Maskuro insère des placeholders lisibles,
  caviarde ou retire sans remplacement. Les deux champs séparés pour PDF et
  Office dans la fenêtre de réglages ont disparu ; cette décision
  importante est ainsi visible et ne peut plus diverger involontairement
  pour des lots mixtes. La visite guidée explique la nouvelle sélection
  avant le premier nettoyage.

- **Les thèmes et filigranes marquent clairement les PDF terminés sur
  demande.** Douze looks d'ensemble harmonisent les textes de remplacement
  et les zones de caviardage ; sont nouveaux notamment Pride ainsi que
  printemps, été, automne et hiver. *Dossier secret* apporte directement un
  `TOP SECRET` diagonal. Indépendamment de cela, un texte de marquage libre
  ou une image, icône ou SVG personnalisée peut être choisi avec couleur et
  opacité. Les graphiques importés sont intégrés sans leurs métadonnées et
  restent disponibles si le fichier source est déplacé. Lors d'une reprise,
  Maskuro remplace son filigrane précédent au lieu de le superposer
  plusieurs fois.
  Les filigranes texte sont dessinés comme dernière couche PDF avec un
  contour clair, afin de rester visibles aussi sur des images sombres et un
  texte dense. L'éditeur de reprise ignore entièrement le filigrane de
  Maskuro et ne propose plus son texte comme candidat au caviardage.

- **Des thèmes de sortie personnalisés peuvent être enregistrés et
  partagés.** Le mélange actuel de texte de remplacement, de caviardage et
  de filigrane reçoit un nom, reste dans les réglages et peut être exporté
  ou importé comme JSON sans texte en clair. L'aperçu d'impression en noir
  et blanc avertit des contrastes faibles ; les confettis de succès
  optionnels restent purement dans l'interface.

- **Une dernière épreuve d'export et une charge de contrôle explicative
  clôturent le cycle de mise en forme.** Avant l'enregistrement définitif,
  Maskuro compare une nouvelle fois chaque emplacement PDF connu avec
  précision de valeur dans la couche de texte et les pixels rendus ; les
  avertissements ne mentionnent que la page et les coordonnées. Dans
  l'éditeur, *Pourquoi est-ce masqué ?* affiche la catégorie, la voie de
  reconnaissance et la marge de sécurité, jamais le texte en clair retiré,
  ni dans le document final.

- **Les barres de caviardage ont désormais le droit d'être jolies.** Sous
  *Réglages → Apparence* se trouvent des couleurs prédéfinies, des
  sélecteurs de couleur libres, des dégradés, un arc-en-ciel, des rayures,
  des points, des fleurs, des étoiles, des cœurs, des pattes, des nuages,
  des éclairs, des grains de café, des canards, des soleils, des feuilles,
  des flocons de neige, du papier, des motifs surligneur, ruban adhésif et
  des motifs aléatoires reproductibles, avec aperçu immédiat. Les textes de
  remplacement reçoivent au choix une couleur, un dégradé, un arc-en-ciel,
  une pilule ou une étiquette. Les couleurs de catégorie distinguent noms,
  adresses, contacts et données médicales. PDF reprend toute la mise en
  forme ; Word, PowerPoint, OpenDocument et HTML utilisent la couleur de
  base opaque choisie. La protection ne change rien à cela : Maskuro retire
  d'abord le contenu confidentiel et ne dessine la couleur ou le motif
  qu'ensuite sur l'emplacement vide.

- **Maskuro existe de nouveau pour Linux – sous forme d'AppImage, DEB, RPM
  et archive portable.** DEB et RPM inscrivent l'entrée de programme, les
  associations de fichiers, la commande de terminal et l'icône dans le
  système ; l'AppImage fonctionne sans installation. Les mises à jour
  restent dans le même format de paquet pour une installation DEB ou RPM
  existante et privilégient sinon l'AppImage.

- **Le contrôle visuel ne présente plus le texte PDF ordinaire une
  seconde fois comme nouveau résultat.** Le regard OCR final et la
  reconstruction sûre des pages visibles restent entièrement actifs ; mais
  ne comptent par défaut comme nouvelle source de résultat que les zones
  que le texte de page et le contrôle d'image individuelle n'ont pas
  encore lues. Ainsi, les lignes de produit ne deviennent plus de nouveaux
  noms ou entreprises pour la seule raison d'une seconde lecture OCR
  divergente. Qui souhaite malgré tout deux jugements indépendants sur
  tout le texte visible active dans les réglages *Vérifier de nouveau
  toute la page PDF visible pour des données*.

- **Les PDF peuvent désormais être consultés en continu, page par page ou
  en double page.** Trois icônes de vue compactes se trouvent en bas
  directement à côté de « Largeur » et « Page ». Continu fait défiler au
  bord de la feuille vers la page suivante ; page unique maintient la
  molette de la souris sur la feuille actuelle ; double page affiche un
  feuillet, rend la feuille cliquée modifiable et déplace Précédent/Suivant
  d'un feuillet entier. Les miniatures de page et la loupe de comparaison
  s'ouvrent en outre dans une colonne de base gauche nettement plus étroite
  et laissent plus de place à la page de travail.

- **Vous voyez désormais ce que le niveau IA a fait.** Après chaque
  passage, une ligne à ce sujet figure sous « Détails » par fichier – « Niveau
  IA : 12 cas limites vérifiés, 3 rejetés » –, et lorsqu'il n'a rien trouvé
  à modifier, cela est également indiqué. Jusqu'ici, le niveau le plus
  coûteux restait entièrement muet : impossible de savoir de l'extérieur
  s'il avait même été sollicité.

  Qui a besoin de plus de précision active sous « Réglages → IA »
  *Consigner chaque question IA dans le journal*. Le fichier journal
  conserve alors par question la taille, la durée et le nombre de
  résultats, ainsi que le temps d'attente dû à une limite de volume de
  l'interlocuteur distant. Le bouton « Afficher le fichier journal » à
  côté ouvre le dossier – il se trouve dans le répertoire de données de
  l'application, qui est caché sous Windows et que personne ne trouve de
  lui-même. Le fichier ne contient que des tailles, jamais de texte issu
  de vos documents.

- **Maskuro détecte lorsque votre service IA plafonne le nombre de
  requêtes.** Les services hébergés n'autorisent souvent que peu de
  requêtes par minute – quatre n'est pas rare. Les requêtes excédentaires
  ne sont pas rejetées, mais doivent attendre, et deux secondes par
  réponse deviennent quarante. Cela ressemblait jusqu'ici à un modèle
  lent. Maskuro lit désormais la limite dans la réponse du service, n'envoie
  plus simultanément plus de questions que ce qui est accepté, indique la
  limite sous « Vérifier la connexion » et l'intègre dans l'estimation de
  durée.

- **L'aperçu de page utilise votre Word, Excel et PowerPoint – et est de
  ce fait environ six fois plus rapide.** Jusqu'ici, elle avait besoin de
  LibreOffice, présent sur peu d'ordinateurs de bureau ; qui n'en avait
  aucun voyait un bouton demandant une installation tierce. Désormais :
  si Microsoft Office est installé, il est utilisé automatiquement – sans
  configuration, sans téléchargement, sans qu'il faille cocher quoi que ce
  soit. LibreOffice reste la seconde voie et, pour les fichiers
  OpenDocument, même la première ; si l'un échoue, l'autre est tenté.

  La différence se remarque surtout pendant le travail : après chaque
  remplacement, la page est recomposée, ce qui coûte environ une
  demi-seconde via Office au lieu de trois. Le premier affichage d'un
  document prend toujours quelques secondes, ensuite il suit vos gestes
  sans temps d'attente.

  Votre propre Word ouvert n'est pas touché : Maskuro démarre sa propre
  session invisible, ouvre le fichier uniquement en lecture, désactive les
  macros et met fin à tout dès que la fenêtre de reprise se ferme. Les
  fichiers protégés par mot de passe sont rejetés au lieu de rester bloqués
  dans une boîte de dialogue invisible.

- **La configuration initiale demande désormais aussi les visages, codes et
  signatures – et charge tout ce qui manque en une seule fois.** À côté de
  la reconnaissance étendue se trouvent sur la première page les trois
  interrupteurs d'image : rendre méconnaissables les zones de visage,
  rendre méconnaissables les codes-barres et QR, caviarder les signatures
  manuscrites sur les pages PDF. La limitation aux PDF est indiquée
  visiblement sous la case ; les fichiers Office ne sont pas recherchés
  automatiquement pour des signatures. Sous les cases figure le nombre de
  mégaoctets que coûte le clic sur « Suivant ». Le chargement se fait
  ensuite dans **une seule** fenêtre avec **une seule** barre de progression
  pour l'ensemble, au lieu de plusieurs boîtes de dialogue successives ;
  une annulation met fin à toute l'opération et ne laisse rien à moitié
  fait. Qui n'en veut rien retire les cases – alors rien n'est chargé non
  plus.

- **L'aperçu peut être allégé selon le besoin de contrôle et replié par
  type.** Au-dessus de la liste se trouve un curseur *Masquer les bien
  étayés* : plus il est déplacé vers la droite, plus il masque du vert vers
  le rouge ; tout à droite ne subsiste que ce que le programme a deviné
  seul. Un clic sur le titre d'un type le replie. Les deux sont une aide à
  la lecture, pas une sélection – ce qui est masqué ou replié reste coché et
  sera remplacé ; le nombre de valeurs concernées à ce moment figure sous
  le curseur. Pour les listes courtes, le curseur n'apparaît pas. Le
  passage à deux colonnes conserve désormais aussi les interrupteurs *plus
  jamais*.

- **La liste d'images peut s'ouvrir d'elle-même avant chaque passage.** Qui
  veut décider individuellement pour chaque image coche sous « Images » la
  nouvelle case *Définir individuellement avant chaque passage*. La liste
  avec aperçu apparaît alors d'elle-même lors du nettoyage, au lieu que
  vous deviez cliquer chaque fois vous-même sur « Définir individuellement… » ;
  si vous l'annulez, le nettoyage n'a pas lieu non plus. Si aucun des
  fichiers choisis ne contient d'image, rien n'apparaît. La case est
  décochée par défaut.
- **Maskuro trouve des signatures manuscrites sur les pages PDF et les
  retire des pixels.** Jusqu'ici, la signature restait visible sous un
  document nettoyé – la reconnaissance de texte lit l'écriture imprimée, et
  ce qu'elle ne lit pas n'est pas remplacé. La recherche est un interrupteur
  propre et nécessite un modèle de reconnaissance qui se recharge une seule
  fois.

  Elle trouve, mesuré, environ 84 signatures sur 100 et en couvre environ
  quatre cinquièmes. C'est une aide, pas une garantie : après chaque
  passage, le rapport indique combien ont été trouvées – y compris
  lorsqu'il n'y en avait aucune, car cela peut signifier qu'il n'y en a
  aucune ou qu'une a été manquée. Sur 72 pages professionnelles réelles
  sans signature, elle n'en a inventé aucune.

  Une signature **dessinée** est trouvée mais pas retirée : elle se
  compose de lignes, pas de pixels, et une barre par-dessus ne serait
  qu'un recouvrement sous lequel les lignes resteraient visibles. Ces
  emplacements sont comptés et signalés, afin de pouvoir les caviarder
  soi-même dans la fenêtre de reprise.

  Les fichiers Word, Excel, PowerPoint et OpenDocument ne sont pas
  recherchés automatiquement pour des signatures. L'interface, la
  configuration initiale, le téléchargement de modèle, la ligne de
  commande et le manuel mentionnent désormais explicitement cette limite.

- **La visite guidée traverse désormais aussi l'aperçu – la fenêtre où
  vous décidez.** Avec le document d'exercice, elle s'ouvre d'elle-même,
  même si vous avez sinon désactivé l'aperçu (votre réglage reste tel
  quel). Il est expliqué ce que signifient les couleurs, pourquoi chaque
  ligne ne pose qu'une seule question – y a-t-il seulement une personne
  ici ? – et à quoi sert « plus jamais ». Pour les couleurs, l'attention se
  porte sur une ligne bien étayée, le plus souvent l'IBAN – l'exemple vert
  que la phrase cite ; ensuite sur la moins bien étayée, où vous pouvez
  cliquer vous-même en pleine explication : la case disparaît, la valeur
  reste dans le document. Pour une longue liste, la fenêtre de visite
  s'ouvre plus grande, afin que l'explication ne recouvre pas les lignes.
  Si la fenêtre s'ouvre une seconde fois, la visite guidée explique
  aussi pourquoi – la page terminée est relue une fois de plus comme
  image, ce qui produit des fragments ressemblant à un nom.

- **L'éditeur s'ouvre en grand dès la première fois.** Original, résultat,
  barre d'outils et liste de résultats se trouvent côte à côte et
  manquaient de place dans la taille de base précédente. Qui rétrécit la
  fenêtre retrouve sa taille la prochaine fois – personne n'est contredit.

- **Un double clic sur un placeholder le récupère** – dans Word, Excel,
  PowerPoint, OpenDocument, texte, e-mail et HTML. Et qui fait glisser sur
  plusieurs placeholders et choisit « Récupérer la sélection » récupère
  tous ceux qui s'y trouvent d'un coup. Il n'est donc plus nécessaire de
  viser précisément le crochet. Les placeholders qui, lors de
  l'anonymisation, représentent plusieurs valeurs différentes en sont
  exclus – ils sont comptés et signalés, pas devinés.

- **Le manuel possède un chapitre « Aperçu avant le remplacement ».** La
  fenêtre est activée par défaut et c'est la seule où vous décidez – dans
  le manuel, cela ne figurait jusqu'ici qu'en incise. Il y est désormais
  écrit ce que signifie une case (elle vaut pour **chaque** occurrence, pas
  seulement celle listée), pourquoi une seule question est à répondre par
  ligne, ce que « plus jamais » entraîne durablement, et pourquoi la
  fenêtre peut s'ouvrir une seconde fois pour un PDF. Dans les dix-huit
  langues, et dans la liste des réglages, l'interrupteur figure désormais
  également.

### Modifié

- **Le panneau « Valeurs remplacées » possède un curseur sur les couleurs,
  et le mode apprentissage n'y figure plus.** Au-delà de huit valeurs, le
  même curseur que dans la fenêtre d'aperçu se trouve au-dessus de la
  liste : *Masquer les bien étayés* allège l'affichage à ce qui mérite
  vraiment d'être revérifié. Cela ne change rien au document, et le nombre
  de lignes visibles sur combien figure en dessous – champ de recherche et
  curseur comptent ensemble. La case *Mode apprentissage* a disparu du
  panneau ; elle reste dans le menu *Outils* et dans la barre d'outils.

- **Le panneau « Valeurs remplacées » affiche désormais les mêmes couleurs
  que le document.** Chaque ligne y est colorée comme l'emplacement dans
  le document et comme la valeur dans l'aperçu : rouge signifie « deviné
  seul, ici le second regard vaut la peine en premier », vert « reconnu par
  un motif nommé ». Au sein de chaque type, le plus incertain figure en
  haut – vous traitez donc la liste de haut en bas et voyez l'essentiel en
  premier. Jusqu'ici, tout y était affiché de manière identique et trié par
  ordre alphabétique.

- **Le mode apprentissage est désactivé d'usine.** Après une correction
  dans la fenêtre de reprise, le programme demandait jusqu'ici de lui-même
  s'il fallait en faire une règle propre. Cette question survient en
  pleine activité ; qui ne l'a pas demandée la ressent comme une
  interruption. Qui veut les règles active le bouton *Mode apprentissage*
  dans la barre d'outils – le choix vaut alors durablement, dans les deux
  sens.

### Corrigé

- **Les fichiers de règles exportés sont désormais explicitement marqués
  comme dignes de protection.** Des termes et exceptions personnels
  peuvent y figurer en clair ; en outre, le fichier peut contenir le sel de
  hachage permettant de confirmer des valeurs présumées. L'export réussi
  affiche donc un avertissement et invite à protéger le fichier et à ne le
  transmettre sciemment qu'à des destinataires autorisés.

- **Le contrôle de sécurité final ne retient plus des fichiers bureautiques
  nettoyés à cause de leurs propres placeholders.** Un sigle de type comme
  « SVNR » figure aussi dans `[SVNR1]` ; auparavant cela était considéré
  comme un prétendu reste de texte en clair et le fichier terminé était
  rejeté. En même temps, les numéros d'appel et les IBAN sont désormais
  aussi repris là où Office dépose la même donnée sans espace visible dans
  un lien ou un fichier intégré.

- **Word, Excel, PowerPoint et OpenDocument ne laissent plus subsister de
  copie de champ découverte tardivement.** Lorsqu'une valeur est détectée
  pour la première fois dans un emplacement secondaire ou un fichier
  bureautique intégré, un passage de reprise étroit nettoie aussi les
  copies visibles et cachées lues précédemment. Les placeholders de lien
  déjà créés ne sont pas remplacés une seconde fois.

- **Lors de la récupération individuelle d'une liste déroulante Word,
  aucune sélection voisine ne revient plus sans y avoir été invitée.** Le
  paragraphe original complet n'est repris que lorsque ses attributs ne
  contiennent plus non plus de placeholders ouverts.

- **Les scans mal lisibles perdent moins de données liées entre elles.**
  Une lecture OCR alternative avec formule de politesse et nom en deux
  parties est conservée ; fragment de rue, numéro et code postal-localité
  protègent ensemble toute la ligne d'adresse, même lorsqu'elle se
  décompose en blocs OCR voisins. Les champs de facture et d'article ainsi
  que les lignes d'événement à côté ne sont pas emportés avec. Une date
  valide décomposée après « né(e) » en plusieurs mots OCR et signes de
  ponctuation est également entièrement rendue méconnaissable.

- **Les confettis de succès sont désormais visibles lors de l'ouverture
  automatique de l'éditeur.** Les confettis jaillissent directement du
  bouton *Nettoyer* au lieu de pleuvoir depuis le bord supérieur de la
  fenêtre. L'éditeur n'attend que le premier jet, court de 850
  millisecondes, et s'ouvre ensuite automatiquement ; sans les confettis
  activés, il n'y a toujours aucun délai.

- **Le compteur de pages et la barre de zoom ne sautent plus dans tous les
  sens au survol des icônes de vue.** Qt redistribuait l'espace libre de la
  ligne d'état dès qu'y apparaissait l'indication d'une icône. Les deux
  groupes de commande conservent désormais leur largeur naturelle et leur
  position fixe au survol.

- **La mesure de vitesse d'un serveur IA connecté échouait toujours** – sur
  chaque serveur, depuis que l'IA propre existe. Elle interrogeait avec une
  limite de réponse étroite puis tentait de lire la réponse ainsi tronquée ;
  cela devait échouer, et « non mesuré » était enregistré. Les conséquences
  se voyaient partout : l'estimation de durée calculait votre serveur avec
  la vitesse du modèle fourni sur un ordinateur de bureau, et dans les
  réglages figurait durablement que la vitesse n'était pas encore mesurée.
  La mesure porte désormais sur la quantité produite par le serveur, et non
  sur le contenu de sa réponse.

- **« Reconnaissance maximale (IA) – lente » figurait aussi lorsque ce
  n'était pas vrai.** Le libellé et l'indication décrivaient le modèle
  fourni sur un ordinateur de bureau – « un modèle de langue sur cette
  machine », « jusqu'à une heure pour les grands documents ». Qui a
  connecté son propre serveur IA y lisait deux choses fausses : le calcul
  ne se fait pas sur sa machine, et la réponse arrive en secondes au lieu
  d'heures. Les deux proviennent désormais de la mesure. En l'absence de
  mesure, l'application n'affirme plus rien, mais indique que ce n'est pas
  encore mesuré.

- **La récupération agit désormais aussi sur une sélection glissée.** Qui
  faisait glisser sur plusieurs placeholders et voulait cliquer sur
  *Récupérer la sélection* trouvait le bouton grisé : il ne s'activait que
  lorsque la sélection était **exactement** un placeholder – glissée sur un
  paragraphe, elle ne l'est jamais. Le chemin en question existait déjà,
  seulement personne n'y accédait. Il suffit désormais de marquer la zone ;
  tous les placeholders qu'elle contient reviennent en un coup.

- **La récupération plantait lorsque la loupe de comparaison était
  ouverte.** La loupe mémorise l'emplacement sous le curseur de la souris,
  pour suivre le même point dans l'original. Lors du rechargement après une
  reprise, elle renvoyait cet emplacement dans une forme que la vue texte
  ne pouvait pas traiter – et comme une telle erreur en pleine interface
  met fin au programme, la reprise était devenue un plantage. La loupe est
  ouverte par défaut, cela touchait donc le chemin ordinaire.

- **Après une récupération, la vue ne saute plus au début du document.**
  Dans un document long, l'emplacement où l'on travaillait disparaissait
  après chaque geste. Désormais, le paragraphe qui était en haut avant y
  reste.

- **Sans LibreOffice, l'aperçu de page indique d'où cela vient au lieu de
  simplement manquer.** Les deux boutons *Aperçu de page* et *Caviarder en
  PDF* étaient verrouillés et ne mentionnaient dans l'info-bulle que le fait
  qu'aucun LibreOffice n'avait été trouvé ; aucun chemin vers celui-ci
  n'existait nulle part dans l'application. Un clic ouvre désormais une
  indication avec le chemin vers LibreOffice, gratuit et open source. Le
  manuel et la FAQ étaient erronés sur ce point – ils annonçaient un
  composant à recharger que l'application ne propose pas.

- **Avant la livraison, le fichier terminé est fouillé une dernière fois
  entièrement – désormais aussi pour Word, Excel, PowerPoint, LibreOffice,
  e-mail, HTML et texte.** Jusqu'ici, seul le PDF bénéficiait de ce dernier
  regard. Tous les contrôles précédents vérifient un emplacement que
  quelqu'un a désigné auparavant ; un emplacement auquel personne n'a
  pensé n'est donc vérifié par personne non plus. À la fin, Maskuro
  recherche désormais bêtement tout ce qui a été remplacé – dans chaque
  partie du paquet. Si quelque chose y subsiste, **aucun** résultat n'est
  produit, et le message nomme la valeur. Un fichier considéré comme
  nettoyé est pire qu'aucun fichier.

- **Les noms figurant dans `<script>` et `<style>` sont désormais
  signalés.** Les deux restent inchangés – il s'agit là de code de
  programme, et un remplacement en plein milieu d'un identifiant transforme
  une page web en page web cassée. Cela n'était toutefois pas signalé
  jusqu'ici, et c'était l'erreur : une règle de style
  `content: "Anna Musterfrau"` s'affiche **visiblement** à l'écran du
  destinataire, et dans le résultat elle restait affichée, tandis que le
  programme signalait la page comme nettoyée.

- **Dans les réglages, les modèles supplémentaires peuvent de nouveau être
  chargés et supprimés.** Le bouton à côté de « Reconnaissance étendue » et
  « Reconnaissance maximale (IA) » aboutissait au clic dans la fenêtre de
  rapport d'erreur au lieu de récupérer le modèle. Le second chemin – la
  case dans la reconnaissance qui demande le modèle d'elle-même – n'était
  jamais concerné.

- **Les noms figurant dans les noms de feuille et de plage d'un tableur
  sont désormais signalés.** Le nom d'une feuille figure sur l'onglet en
  bas, le nom d'une plage nommée dans le champ de nom et dans chaque
  formule qui l'utilise. Les deux ne sont toujours pas remplacés – les
  formules y font référence, et un classeur avec des erreurs de référence
  n'aide personne –, mais cela figure désormais quelque part. Jusqu'ici, le
  signalement n'existait que pour le nom de feuille d'un classeur Excel :
  une plage nommée « Bezuege_Brunnthaler » sortait silencieusement avec le
  fichier, et pour un tableur LibreOffice, le programme se taisait
  entièrement. Une feuille « Notizen Ortner » était ainsi considérée comme
  nettoyée, et le premier regard du destinataire tombait sur le nom.

  Seul est signalé ce qui mène réellement à une personne : un mot déjà
  remplacé ailleurs dans le même classeur, ou un résultat qui sélectionne
  parmi plusieurs mots. Un mot isolé comme « Zustaendig » ou
  « Bezug_Umsatz » ne déclenche plus d'avertissement – auparavant, c'était
  le cas, et un avertissement qui apparaît un classeur sur deux, plus
  personne ne le lit à la troisième fois.

- **« Récupérer l'original » récupère désormais vraiment tout.** Dans
  certains documents, des caractères isolés manquaient ensuite – de
  « Seestraße 14 » on obtenait « Seestraße 4 », de « An : » un « An », de
  « nordlicht-planung » un « nordlicht planung » –, et des lignes entières
  ne revenaient pas du tout. À cet endroit précisément, plus rien ne
  pouvait ensuite être sélectionné à la souris ni caviardé : le texte
  figurait bien sur le papier, mais le programme ne le connaissait plus.
  Étaient concernés les caractères étroits – le un, les deux-points, le
  trait d'union – dans des documents qui posent chaque caractère
  individuellement ; le document d'exercice en fait partie.

- **Et ces mêmes documents ne sont plus transformés en image lors du
  nettoyage.** Parce qu'un tel caractère subsistait, le contrôle final
  signalait un reste et la page était rastérisée par précaution. Le texte
  qui s'y trouvait n'était plus alors qu'une image : plus consultable, plus
  sélectionnable, plus volumineux dans le fichier. Le document d'exercice
  reste désormais du texte réel sur les deux pages.

- **Les marques colorées ne restent plus au-dessus du texte récupéré.**
  Qui annulait un remplacement voyait toujours le rectangle coloré au-dessus
  du mot restauré – il affirmait « quelque chose a été retiré ici », alors
  que l'original s'y trouvait de nouveau.

- **Une barre ne trahit plus la longueur du mot dessous.** Lors du
  caviardage, la barre couvre désormais **toute** la ligne dans les lignes
  courtes – bloc d'adresse, données d'en-tête, cellule de tableau étroite.
  Si toute la ligne ne tient pas (la ligne de tableau ordinaire à trois
  colonnes), on en reste au champ ; dans une ligne de texte courant, cela
  reste au mot près, sinon un nom en plein milieu de phrase noircissait
  toute la phrase. Et les barres alignées les unes sous les autres
  deviennent **de longueur identique** : dans le bloc d'adresse, une valeur
  figure sur chaque ligne, et trois barres de longueurs différentes
  trahissaient toujours la longueur des lignes. Elles ne s'étendent que
  tant que le papier est libre – devant une colonne voisine, la barre
  s'arrête.

- **« Ligne entière » caviarde désormais vraiment la ligne entière.**
  Jusqu'ici, la barre s'arrêtait à l'espace plus grand suivant – donc à la
  fin du champ. En texte courant, cela ne se remarquait pas, le champ y est
  la ligne ; dans les données d'en-tête et les tableaux si : de
  « Nom : Anna Musterfrau   Service : Ventes » résultait une barre qui
  s'arrêtait exactement à la dernière lettre du nom – et sa longueur restait
  ainsi lisible sur la feuille. La barre va désormais du premier au dernier
  mot de la ligne et emporte les colonnes voisines. Qui ne veut atteindre
  que la valeur choisit « Mots » ; l'automatisme caviarde toujours par
  champ.

- **Avant la livraison, le fichier terminé est fouillé une dernière fois.**
  Tous les contrôles précédents vérifient un emplacement que quelqu'un a
  désigné auparavant – texte de page, rectangle de résultat, zone d'image.
  Mais un PDF possède plus d'emplacements qu'une énumération ne peut en
  couvrir : annotations, valeurs de formulaire, signets, informations de
  document, pièces jointes, JavaScript. À la fin, Maskuro fouille donc
  bêtement le fichier écrit à la recherche de tout ce qui a été remplacé –
  partout sauf dans le texte de page, où le même libellé peut aussi
  légitimement subsister. S'il y subsiste quelque chose, **aucun** résultat
  n'est produit, et le message nomme la valeur. Un document considéré comme
  nettoyé est pire qu'aucun document.

- **Ce qui n'a pas pu être vérifié ne compte plus comme vérifié.** Sur
  trois voies, un échec du contrôle final ressemblait jusqu'ici à un
  résultat propre. Une page dont la couche de texte ne pouvait pas être lue
  passait pour particulièrement propre – il n'y avait rien à y trouver ;
  elle est désormais rastérisée. Si une page comportant un résultat
  résiduel ne pouvait pas être rastérisée en remplacement, elle était
  livrée silencieusement ; désormais, le nettoyage s'interrompt plutôt. Et
  la contre-vérification dans la fenêtre de reprise signalait après une
  erreur propre « rien ne reste » – impossible à distinguer dans la fenêtre
  du fait que tout avait été retiré ; désormais l'avertissement apparaît
  avec le bouton « Rastériser la page ».

- **« Réinitialiser aux valeurs par défaut » ne réinitialisait en fait pas
  la plupart des réglages.** Neuf cases sur vingt-deux restaient inchangées
  après le geste – parmi elles l'aperçu, « Ouvrir les fichiers nettoyés
  ensuite », la fenêtre de reprise, le dépôt immédiat et les deux cases de
  mise à jour. Le fichier enregistré était bien vidé, mais la fenêtre
  conservait les anciennes valeurs et les réécrivait au clic suivant.
  Chaque case revient désormais, et la mention « modifié » disparaît avec
  elle.
- **« Déposer automatiquement un rapport de contrôle par nettoyage »
  s'affichait activé, mais était désactivé.** Après la réinitialisation,
  la case restait cochée alors que la valeur était supprimée – aucun
  rapport n'était plus produit, sans que rien ne le signale. Il en allait
  de même pour le journal de contrôle et l'enregistrement d'écran
  personnel ; leur raccourci clavier est désormais aussi correctement
  activé ou désactivé lors de la réinitialisation.

- **Les barres d'une même ligne ont désormais le même aspect.** Jusqu'ici,
  chaque résultat apportait sa propre barre, dont la hauteur provenait de
  la police du mot atteint. Dans une ligne comportant un libellé et une
  valeur de tailles différentes, un trait épais et un fin se trouvaient
  donc côte à côte avec des bords décalés, et là où deux résultats
  n'étaient séparés que par un espace, un interstice clair subsistait
  au-dessus. Les barres d'une même ligne ont désormais le même bord
  supérieur et inférieur, et ce qui n'est séparé que par un espace devient
  une seule barre. Ce qui doit rester entre deux résultats – la virgule
  après le nom, un libellé, un montant – continue de les séparer.
  Valable aussi bien pour les pages composées que pour les scans.

- **Les onglets sous « À propos de ce programme » recommencent en haut.**
  Confidentialité, conditions de licence et mentions de licence
  s'ouvraient en plein milieu du texte – qui les lisait devait d'abord
  remonter tout en haut pour voir la première ligne.

- **Le stylo n'ouvre plus une seconde fenêtre d'éditeur, mais ramène celle
  existante au premier plan.** Jusqu'ici, chaque clic en créait une
  nouvelle. La fenêtre n'a pas d'entrée propre dans la barre des tâches –
  qui la réduisait n'y accédait plus et cliquait de nouveau ; en
  restaurant la fenêtre principale, toutes les fenêtres accumulées
  arrivaient alors d'un coup au premier plan. Désormais, d'autres documents
  atterrissent dans la barre d'onglets de la fenêtre ouverte, et un
  document déjà présent n'obtient pas de second onglet.

- **« Reconnaissance étendue » ne porte plus la mention « modifié » tant
  que son modèle manque.** Elle est livrée activée, mais sans le modèle
  rechargeable elle ne peut pas du tout l'être – dans les réglages, la
  ligne apparaissait donc comme modifiée sur chaque machine fraîchement
  configurée, bien que personne n'y ait touché. Pourquoi la case est
  désactivée, seul son libellé le dit désormais : « Modèle pas encore
  chargé ».

- **Le bandeau d'introduction expliquait la surface PDF dans les fichiers
  Office et texte.** Il y était écrit « cliquer sur un mot le caviarde » –
  dans un fichier Word, un clic ne caviarde pourtant rien, on y sélectionne
  puis on appuie sur un bouton. Il indique désormais ce qui vaut dans la
  vue concernée.
- **La barre d'outils était encombrée de libellés dans la vue texte.**
  « Remplacer la sélection », « Caviarder la sélection », « Récupérer la
  sélection », « Aperçu de page » et « Caviarder en PDF » apparaissent
  désormais sous forme de symbole – comme leurs équivalents dans un PDF.
  Leurs noms restent dans l'aide rapide et le menu.
- **Ctrl+molette dans la loupe de comparaison ne déplaçait pas son curseur
  de zoom en même temps.** L'écriture s'agrandissait, le curseur et le
  pourcentage à côté affichaient toujours l'ancien état.
- **Le programme d'installation d'une mise à jour ne passait pas au
  premier plan** – il fallait d'abord cliquer dessus dans la barre des
  tâches (Windows uniquement).
- **Une année en début de ligne était considérée comme code postal
  autrichien.** Dans un CV, « 2020 Stratégies de vente » devenait un
  placeholder – toute la ligne disparaissait. Un nombre à quatre chiffres
  entre 1900 et 2099 nécessite désormais un second signal d'adresse : la
  rue au-dessus, un mot de champ avant, un indicatif de pays ou un nom de
  lieu connu. Les blocs d'adresse en disposent ; les colonnes d'années non.
- **Une paire mois-année était considérée comme numéro de téléphone.** De
  « Depuis 08.2010 123-Verkauft GmbH » résultait un « numéro d'appel » – le
  mois, l'année et les premiers chiffres du nom d'entreprise qui suivait.
- **Le rapport indiquait « vérifié par reconnaissance de texte » et taisait
  ce qu'elle ne lit pas.** Si des images sont conservées, il est désormais
  précisé que le contenu manuscrit n'y est pas trouvé – une signature ou un
  nom inscrit à la main y reste visible. Jusqu'ici, cette phrase ne
  figurait que pour les pages numérisées ; un PDF ordinaire avec une
  signature intégrée n'en disait pas un mot.
- **Un placeholder sur fond d'image caviardé se trouvait au bord gauche de
  sa barre.** Lorsqu'une valeur est trouvée dans une image – par exemple un
  nom tapé à côté d'une signature scannée –, la zone d'image doit être
  entièrement caviardée sur toute sa largeur. Le placeholder plus court
  laissait à côté du noir nu, ce qui ressemblait à deux opérations. Il se
  trouve désormais centré sur la barre.

## 0.10.41-alpha.20260826 – 26 août 2026

### Nouveau

- **Après la période d'essai, une fenêtre rappelle la licence une fois par
  démarrage.** Elle apparaît cinq minutes après le démarrage – pas
  immédiatement, afin de ne gêner personne avant le premier geste – et
  attend qu'un nettoyage en cours se termine. De là, un chemin mène à
  l'achat et un autre à la saisie d'une clé déjà achetée ; « Plus tard » la
  ferme dès que les cinq secondes du bouton sont écoulées. Rien n'est
  bloqué : le niveau gratuit continue de fonctionner comme avant.

- **Le temps d'attente avant un passage au niveau gratuit dure désormais
  dix secondes au lieu de trente.** Il doit rappeler la licence, pas
  arrêter le travail.

- **Les trois indications relatives à la licence ont désormais le même
  aspect.** Temps d'attente, rappel dans les derniers jours d'essai et
  indication après la période d'essai portent le même bandeau, la même
  structure et les mêmes boutons ; le temps restant figure dans le bouton
  au lieu d'un grand chiffre à côté.

- **La liste de résultats dans l'aperçu se présente de nouveau les uns
  sous les autres.** Elle était sur deux colonnes à partir de neuf valeurs ;
  en la parcourant, l'œil saute alors entre deux voies, alors que la
  décision se prend ici ligne par ligne. Qui préfère les deux voies les
  réactive en bas à gauche de la fenêtre – le choix reste enregistré, et au
  changement, les valeurs déjà décochées restent décochées.

- **Le niveau IA est désormais ouvert à quiconque connecte son propre
  serveur IA.** « Réglages → IA » réunit tout à ce sujet : la connexion, ce
  que l'IA a le droit de faire, ce qu'elle doit faire – et au-dessus,
  l'interrupteur du niveau ainsi que la contre-vérification, dès qu'un
  serveur est enregistré. Un modèle de langue qui calcule sur le poste de
  travail lui-même reste réservé : il lui faut plusieurs minutes pour dix
  pages, ce qui n'est pas adapté au quotidien.

- **Une IA propre peut être connectée.** Au lieu du modèle de langue
  fourni, un modèle plus grand sur une autre machine peut répondre – sur un
  serveur interne ou une station de travail dotée d'une carte graphique
  puissante. Un service doté d'une interface compatible OpenAI est requis
  (Ollama, LM Studio, llama.cpp-server, vLLM, LocalAI) ; il se configure
  sous « Réglages → IA personnelle » avec une vérification de connexion qui
  interroge réellement le modèle, mesure la vitesse et détermine le format
  de réponse possible. Plusieurs segments de texte s'exécutent alors
  simultanément au lieu de l'un après l'autre.

- **Ce que l'IA a le droit de faire et ce qu'elle doit faire est désormais
  réglable.** Trois interrupteurs décident de la vérification des cas
  limites, de la recherche autonome et de la recherche dans le texte
  courant ; l'instruction donnée au modèle figure mot pour mot, peut être
  complétée par des termes maison et remise sur la valeur par défaut d'un
  clic.

- **Si le texte quitte alors le réseau propre, un avertissement s'affiche
  avant chaque passage.** Maskuro reconnaît à l'adresse si le serveur IA se
  trouve dans les locaux et nomme un fournisseur connu. L'avertissement
  peut être désactivé, mais seulement contre la confirmation explicite
  d'être autorisé à cette transmission, et seulement pour exactement cette
  adresse. Cela ne change rien au processus : la transmission figure
  toujours dans le journal et dans le rapport de contrôle de chaque
  fichier. En ligne de commande, il n'est pas demandé mais interrompu –
  `--ki-auswaerts-erlauben` est requis à cet endroit.

- **L'aperçu avant le remplacement est désormais actif par défaut pour les
  nouveaux réglages et s'applique aussi désormais au contenu du
  presse-papiers explicitement nettoyé ainsi qu'au texte et aux images
  insérés dans le programme.** Pour les lots de documents, exactement un
  aperçu par document avec toutes les pages continue d'apparaître ; le
  nettoyage immédiat et silencieux de copies courtes n'ouvre volontairement
  aucune fenêtre.

- **Les résultats peuvent être activés et désactivés dans l'aperçu sur
  toute la ligne colorée.** La case est désormais grande et contrastée ; en
  outre, un champ d'état affiche « Remplacer » ou, barré, « Remplacer », de
  sorte que les valeurs sélectionnées et désélectionnées se distinguent
  immédiatement même sur des couleurs de confiance sombres.

- **Même les PDF avec un contre-regard de sécurité visible n'ouvrent
  désormais l'aperçu qu'une seule fois par document.** Les termes
  désélectionnés restent désélectionnés pour le témoin de page ultérieur ;
  sa vérification continue de s'exécuter sans interrompre le même passage
  avec une seconde boîte de dialogue.

- **Les mots de remplacement se présentent de manière identique dans
  l'éditeur de reprise, même sur des pages rastérisées.** Si le
  placeholder rouge se trouve dans les pixels plutôt que dans la couche de
  texte PDF, il reçoit désormais malgré tout la même surface de fond
  colorée selon la confiance qu'un placeholder de texte PDF ordinaire.

- **Dès l'aperçu avant le remplacement, le besoin de contrôle des termes
  trouvés est affiché.** Chaque ligne porte la même couleur rouge-orange-
  vert que le remplacement plus tard dans l'éditeur. Au sein d'une
  catégorie, la faible confiance et les candidats rouges à faux positif
  sont en haut, les preuves vertes solides en bas ; les égalités restent
  alphabétiques. Si la même valeur provient de plusieurs résultats, c'est
  par précaution la plus douteuse de leurs évaluations qui compte. Les cas
  particuliers non évalués figurent en jaune neutre entre le rouge et
  l'orange.

- **Le résultat peut désormais être copié directement depuis l'éditeur de
  reprise comme fichier.** « Copier le résultat » dépose la version nettoyée
  actuelle dans le presse-papiers, sans fermer l'éditeur ni devoir
  rechercher le fichier dans la liste principale. Pour une modification
  manuelle pas encore enregistrée, le chemin d'enregistrement sûr complet
  s'exécute automatiquement avant ; « Copier l'image » reste une fonction
  distincte pour les pixels purs.

- **Les mots remplacés montrent d'un coup d'œil dans l'éditeur ce qui doit
  être vérifié en premier.** Une pure supposition du modèle de langue est
  rouge, même si spaCy annonce forfaitairement 85 pour cent pour cela.
  D'autres jugements de modèle non étayés restent au maximum orange ; des
  preuves nommées solides peuvent devenir vertes. Le travail manuel et les
  anciennes attributions sans évaluation exploitable restent en jaune
  neutre. Les barres de caviardage automatiques portent également ces
  couleurs dans l'aperçu de l'éditeur – désormais aussi lorsque la barre
  fait partie d'une page PDF rastérisée. Pour cela, l'attribution doit
  correspondre et l'ancien cadre de mot doit être prouvé entièrement
  opaque en noir ; le simple gras n'est pas coloré. Dans le PDF enregistré,
  toutes les barres restent inchangées, opaques en noir.

- **Ce qui est désélectionné dans l'aperçu peut être mémorisé
  durablement.** Là où vous retirez la case, vous dites : ici, la
  reconnaissance s'est trompée. Jusqu'ici, cela ne valait que pour ce
  document précis. Un interrupteur « plus jamais » apparaît désormais sur
  la ligne ; une fois activé, la valeur entre durablement dans la liste
  « Ne jamais retirer » et vaut désormais comme inoffensive dans chaque
  document. Sous la liste figure ce qui devient durable, avant que vous
  n'appuyiez sur « Remplacer ». Le sens inverse n'existe volontairement
  pas : ce qui a été trouvé une fois, la reconnaissance le retrouve.

- **Un bouton remet tous les réglages à l'état de livraison.** Il se trouve
  en bas à gauche de la fenêtre de réglages et demande confirmation au
  préalable. Vos fichiers, votre licence, vos règles de reconnaissance
  personnelles et le démarrage automatique restent inchangés ; ce que
  votre administration impose reste en vigueur. Chaque réglage qui s'écarte
  de l'état de livraison porte en outre la mention « modifié » – on voit
  ainsi d'un coup d'œil ce qu'on a changé.

### Modifié

- **Un résultat n'est plus déposé automatiquement de lui-même – seulement à
  l'enregistrement.** Un passage depuis la fenêtre écrit d'abord sa version
  nettoyée à un emplacement provisoire ; le fichier « …_bereinigt » à côté
  de l'original n'apparaît que lorsque vous appuyez sur « Enregistrer ».
  Jusque-là, le résultat peut être consulté, repris et copié. Chaque ligne
  terminée dispose pour cela d'un bouton d'enregistrement, sous la liste
  figure « Tout enregistrer », et dans l'éditeur, Ctrl+S s'applique. Qui
  vide la liste ou ferme le programme est interrogé ; ce que personne ne
  dépose ne reste nulle part non plus. « Afficher dans le dossier » est
  verrouillé avant l'enregistrement – l'emplacement provisoire n'est pas
  une destination vers laquelle on renvoie quelqu'un. Le fichier
  d'affectation part avec lors de l'enregistrement.

  Dans les réglages sous « Programme », « Déposer immédiatement les
  résultats à côté de l'original » restaure le comportement précédent. La
  ligne de commande, la surveillance de dossier et le veilleur de
  presse-papiers déposent toujours immédiatement, sans changement –
  personne n'y est présent pour enregistrer.

- **La barre d'outils de l'éditeur de reprise est réorganisée.** Le mode
  apprentissage se trouve désormais à l'extrémité droite avec la loupe de
  comparaison et « Valeurs remplacées » – les trois interrupteurs qui
  activent et désactivent un mode de fonctionnement se trouvent ainsi
  regroupés. « Appliquer à toutes les pages » a été rapproché des trois
  formes de caviardage, car il n'agit que là. « Copier le résultat »,
  « Fichier – Réinitialiser » et « Appliquer à toutes les pages » n'ont
  plus de libellé ; leur nom reste dans l'info-bulle et le menu. Entre
  « Remplacer » et « Récupérer l'original » se trouve un trait de
  séparation : les deux sont des sens opposés et ressemblaient côte à côte
  à deux variantes du même outil.

- **Le symbole de « Copier le résultat » affiche désormais un document.**
  Deux feuilles avec un coin plié et des lignes de texte au lieu de deux
  feuilles identiques avec une petite flèche de coin. « Copier l'image »
  porte en contrepartie le symbole d'image, afin que les deux se
  distinguent sans libellé. Le bouton « Copier » dans la liste de résultats
  affiche le même symbole de document – il dépose le même fichier.

- **Les réglages sont triés et pourvus de titres.** « Reconnaissance »
  comporte désormais quatre sections : *Ce qui est retiré*, *Comment c'est
  remplacé*, *Avec quelle minutie la recherche s'effectue* et *Avant et
  après le passage*. La reconnaissance de visage et les codes-barres/QR se
  trouvent avec les images, là où on les cherche ; « Programme » est
  divisé en *Fichiers de résultat*, *Au démarrage*, *Mise à jour*,
  *Affichage* et *Retour vers nous*, et le complément de nom du fichier de
  résultat se trouve avec les fichiers de résultat au lieu d'entre langue
  et apparence.

- **La reconnaissance étendue est activée d'usine**, même avant que son
  modèle de langue soit chargé. Auparavant, la valeur par défaut dépendait
  du stock de modèles, et une machine fraîchement configurée fonctionnait
  durablement au niveau le plus faible. La fenêtre de configuration propose
  le modèle à charger sur la première page et indique le prix à côté. S'il
  manque, la case le dit toujours, plutôt que de feindre un niveau qui ne
  fonctionne pas.

- **Les deux listes de termes portent désormais ce qu'elles font :**
  « Toujours retirer » au lieu de « Termes personnels » et « Ne jamais
  retirer » au lieu de « Exceptions ».

- **La fenêtre d'aperçu est plus claire.** À partir de neuf valeurs, elles
  se présentent sur deux colonnes, les lignes sont plus plates, et le
  nombre de résultats figure directement derrière le terme au lieu du bord
  droit.

- **Moins de boutons doublons dans l'éditeur.** « Enregistrer sous … » et
  « Copier l'image » ne se trouvent plus que dans le menu Fichier, avec
  leurs raccourcis clavier habituels. Dans la barre, il n'en reste plus
  qu'un chacun : Enregistrer et « Copier le résultat » – où est enregistré
  figure de toute façon dans la ligne d'état et peut y être changé d'un
  clic.

- **Le veilleur de presse-papiers n'est plus proposé au premier
  démarrage.** Il intervient dans chaque opération de copie du système ;
  qui découvre le programme pour la première fois ne peut pas évaluer
  cela. Dans les réglages, il figure toujours, avec à côté la clause qui
  lui appartient.

- **L'apparence claire éblouit moins.** Le fond de fenêtre provenait
  jusqu'ici du style système respectif et était ainsi la seule grande
  surface que personne n'avait décidée – presque blanc sous Windows.
  Désormais, c'est un blanc cassé, identique sur chaque système.

- **La visite guidée et le manuel expliquent les couleurs.** Ce que
  signifient le rouge, l'orange, le vert et le jaune derrière un mot
  remplacé figure désormais comme étape propre dans la visite guidée et
  comme paragraphe dans le manuel – dans toutes les versions linguistiques.

- **Dans l'éditeur de reprise, Remplacer précède Caviarder** – dans la
  barre d'outils, dans le menu « Outils » et dans le clic droit sur la
  page. Remplacer est le cas normal : un placeholder peut être cliqué et
  récupéré, une barre non.

### Corrigé

- **Le manuel et la FAQ affichaient des placeholders qui n'existent plus.**
  Depuis le passage à la forme courte, Maskuro écrit `[NAM1]` ; dans l'aide,
  `[NAME1]` figurait toujours, et la phrase « Par défaut, c'est `[NAME1]` »
  était donc tout simplement fausse. Dans les dix-sept versions traduites,
  la marque **allemande** figurait en outre à la place de la marque propre
  – un lecteur espagnol voyait `[NAME1]`, alors que son programme écrit
  `[NOMB1]`. De même pour l'extension du fichier de résultat : toutes les
  versions y promettaient `_bereinigt`, alors que le programme crée
  `_limpiado`, `_nettoyé` ou `_除去済み`. Étaient également concernées la
  forme sans numéro (lors de l'anonymisation, tout s'appelle `[NAM]`, pas
  `[NAME]`) et l'identifiant dérivé de la valeur lors du hachage.

- **La fenêtre d'aperçu n'interrompt plus qu'une seule fois par document –
  et une seconde fois seulement si quelque chose de vraiment nouveau
  s'ajoute.** Un PDF est lu depuis deux côtés : une fois depuis le flux de
  contenu, et enfin depuis la page rendue et visible. Jusqu'ici, chacun des
  deux interrogeait pour son compte. Désormais : ce que vous avez décidé
  dans la première fenêtre continue de s'appliquer, et les valeurs qui y
  figuraient déjà ne reviennent pas. Si en revanche le contrôle visuel des
  pages terminées trouve quelque chose qui ne figurait nulle part
  auparavant, cela vous est présenté une nouvelle fois – seul, sans les
  valeurs déjà décidées.

- **La fenêtre d'aperçu indique désormais selon quoi décider.** Au lieu de
  « Retirer la case = la valeur reste » – ce que fait la case, mais pas
  quand la retirer –, il est désormais écrit : retirez la case partout où
  ne figure aucune valeur personnelle ; c'est là que la reconnaissance
  s'est trompée. En outre, chaque fenêtre nomme le passage de contrôle dont
  proviennent ses valeurs.

- **Les placeholders se présentent de manière identique dans tout le
  document.** Sur les pages reconstruites comme pages image dans le
  chemin OCR, les placeholders visibles étaient jusqu'ici composés en
  police à chasse fixe – « [PLZ4] » apparaissait alors large et avec
  empattements à côté d'un « [NAM1] » étroit de la même page. Ils portent
  désormais la même police sans empattement que partout ailleurs, et ne
  sont plus non plus composés plus larges que prévu lors de l'ajustement.
  La couche de recherche invisible conserve sa propre police – elle a
  besoin de dimensions fiables, pas d'apparence.

- **Dans la barre d'outils de l'éditeur, il n'y a plus de doubles traits de
  séparation.** Là où tout un groupe d'outils disparaît pour le type de
  fichier ouvert – dans un PDF, par exemple, aperçu de page et rendu –, les
  deux traits autour de l'espace restaient jusqu'ici tous les deux.

- **Lors de la récupération, il ne reste plus occasionnellement qu'un
  emplacement blanc.** Un texte original déjà exactement restauré n'est
  plus repeint en blanc par le cadre large et regroupé de son placeholder
  retiré. Pour les récupérations mixtes de texte et d'image, le texte n'est
  en outre inséré de manière invisible que lorsque l'image de page porte
  déjà visiblement exactement cet état original. Cela vaut pour les cadres,
  le panneau de résultats et les pièces jointes PDF.

- **« Récupérer l'original » ne propose plus inutilement de rastériser la
  page.** Le contrôle strict de reste de texte reste actif pour le
  caviardage et le remplacement. Lors de la récupération, il est omis : là,
  du contenu original revient volontairement, et des mots voisins
  inchangés dans le cadre de récupération élargi n'étaient pas une erreur
  de nettoyage, mais un faux positif.

- **La visite guidée de l'éditeur explique désormais « Remplacer » et
  « Récupérer l'original » comme des étapes propres.** Les deux outils sont
  directement mis en évidence dans la barre et décrivent qu'un cadre glissé
  insère un placeholder, respectivement récupère le contenu original de cet
  emplacement depuis le fichier source.

- **Les placeholders spécifiques à un pays restent désormais aussi limités
  à quatre lettres au maximum.** Ces types manquaient jusqu'ici dans le
  catalogue de sigles central et pouvaient donc encore apparaître en toutes
  lettres, par exemple `[UMSATZSTEUER_ID1]`. Les nouveaux passages écrivent
  désormais `[UID1]` ; tous les types allemands et anglais reconnus
  automatiquement restent ainsi univoques. Les sigles calculés eux-mêmes
  d'autres langues d'interface ne dépassent plus quatre caractères en cas
  d'homonymie. Les libellés de règles personnels restent nommés inchangés,
  tels que saisis.

- **Remplacer utilise désormais tout l'espace de ligne réellement libre
  avant de caviarder.** La limite rigide précédente au triple de la
  largeur de mot d'origine produisait des barres même dans des champs de
  formulaire largement vides. Les résultats du contre-regard OCR visible
  reçoivent désormais aussi un placeholder lisible lorsque du texte PDF est
  présent ; restent noirs les contenus purement image, annotation et
  vectoriel, le mode de caviardage choisi ainsi que les véritables goulots
  d'étranglement dans lesquels même une forme abrégée univoque ne tient
  pas.

- **Un placeholder déjà visible n'est plus réécrit en rouge une seconde
  fois lors de la rastérisation de sécurité.** La rastérisation reprend
  désormais le remplacement existant depuis l'image de page et ne crée
  qu'une copie de recherche invisible. Si une barre de sécurité doit
  couvrir exactement cet emplacement, tout le cadre de placeholder réel est
  renouvelé au lieu de seulement son ancrage plus court d'origine.

- **« Récupérer l'original » ne marque plus que des cibles sûres dans le
  cadre glissé.** Tous les termes remplacés qu'il contient s'illuminent
  individuellement et précisément ; le texte courant inchangé reste
  intact. Les vraies barres de caviardage vectorielles sont également
  marquées individuellement lorsque du texte original se trouve sous leur
  surface PDF noire. Sur les pages rastérisées, l'aperçu renonce
  volontairement à une prétendue surface de barre : la recherche de pixels
  précédente y reliait lettres, soulignements et lignes de tableau en de
  grandes surfaces rouges à de mauvais endroits. La restauration elle-même
  n'en est pas affectée.

- **Lors de la restauration sur des pages rastérisées, le texte revient.**
  Auparavant, il restait un emplacement vide avec des rectangles colorés
  par-dessus. Le texte récupéré figurait dans le document, mais était
  repeint par le fond blanc d'un placeholder dessiné plus loin dans la
  construction de la page.

- **Les couleurs de contrôle ne se superposent plus.** Le même emplacement
  était coloré pour chaque entrée de l'affectation – sur une page, cinq
  vrais résultats, chacun repeint cinq fois, jusqu'à ce que la marque pâle
  devienne un bloc saturé. Et elles n'apparaissent plus sur des mots qui
  n'ont pas du tout été remplacés : si la valeur originale figure toujours
  sur la page, il n'y a plus non plus de marque à cet endroit.

## 0.10.40-beta.1 – 24 août 2026

### Corrigé

- **Les barres de caviardage dans l'éditeur disposent désormais d'une
  marge de sécurité.** Les cadres de mot, de ligne et libres couvrent
  aussi les glyphes débordants et les pixels de bord lissés ; une
  vérification de rendu garantit en outre qu'il ne reste ni trace
  visible ni texte original consultable.

- **Les textes de remplacement restent lisibles et uniformément
  courts.** Les nouveaux noms, adresses et termes libres apparaissent par
  exemple comme `[NAM1]`, `[ADR2]` et `[BEG3]`. La limite basse fixe est
  de 4,5 points ; en cas de manque de place, la réduction intervient
  d'abord et l'espace utilisable est élargi. Les anciennes affectations
  avec des espaces réservés longs restent lisibles et récupérables.

- **Les remplacements à plusieurs mots depuis le panneau de résultats
  sont protégés contre les marques en double et les restes
  d'original.** La régression est vérifiée avec et sans espaces réservés
  numérotés ; exactement une affectation commune est conservée par
  emplacement trouvé.

- **Les contenus du presse-papiers récupérés ne sont pas immédiatement
  renettoyés sur macOS.** Même si la signature système ne change qu'avec
  retard après l'écriture, Maskuro reconnaît de manière fiable son
  propre contenu.

### Nouveau

- **L'éditeur peut réinitialiser entièrement un fichier à la version de
  base fraîchement nettoyée.** « Fichier – Réinitialiser » annule, après
  confirmation, toutes les retouches de l'onglet actuel, y compris la
  liste des remplacements et les compteurs. La commande est verrouillée
  sans modifications et peut elle-même être annulée avec « Annuler ».

- **Les dates décalées conservent désormais leur chronologie de manière
  fiable sur plusieurs fichiers.** Le décalage commun est ancré de
  façon durable dans les règles dès l'activation de la stratégie ; de
  plus, le décalage ne peut plus être de zéro jour et donc laisser
  passer la vraie date sans que cela se remarque.

- **Le travail manuel PDF couvre désormais l'ensemble du processus de
  caviardage professionnel.** Termes isolés, listes et modèles réguliers
  peuvent être recherchés et caviardés en toute sécurité dans le PDF
  ouvert ou dans tous les PDF d'un dossier ; des pages entières et des
  plages de pages sont directement sélectionnables. Couleur, zone
  blanche neutre, texte de superposition, police, alignement et
  répétition disposent d'un aperçu, les codes réutilisables peuvent être
  gérés ainsi qu'importés et exportés. Le nettoyage PDF supprime au
  choix tous les contenus cachés par reconstruction complète ou des
  classes de données sélectionnées. Le choix le plus sûr est clairement
  recommandé, les modèles de recherche invalides sont expliqués et les
  passages sur dossier n'écrivent que des copies de résultat.

- **La statistique d'utilisation volontaire montre désormais les
  installations et changements de version.** Maskuro génère pour cela un
  identifiant d'installation aléatoire, stocké localement. Il ne
  contient aucune indication sur l'appareil, l'utilisateur ou la
  licence ; le serveur ne stocke que sa valeur SHA-256. La statistique
  reste entièrement désactivable dans les paramètres.

- **La visite guidée est désormais un exercice mené à travers les deux
  fenêtres.** Elle dépose elle-même le document d'exercice fictif dans
  la liste, explique le chemin jusqu'au nettoyage et se poursuit
  automatiquement dans l'éditeur après le passage. Qui interrompt la
  visite met aussi fin à cette suite.

- **Les entreprises de quinze juridictions supplémentaires sont
  reconnues.** Qui nettoie des documents des pays baltes, de Belgique,
  de Scandinavie, de Tchéquie, de Pologne, d'Europe du Sud-Est, de
  Singapour, du Brésil ou du Mexique ne perd plus de raisons sociales
  parce que leur forme juridique était inconnue – s'y ajoutent
  notamment OÜ, MTÜ, SIA, VZW, ASBL, P/S, Sh.p.k., EIRELI, z.s., o.p.s.,
  S.K.A., Pte. Ltd. ainsi que S.A. de C.V. et S. de R.L.

### Modifié

- **Les barres d'outils de l'éditeur exploitent désormais leur espace de
  façon plus ciblée.** Des icônes standard univoques et des formes
  d'outils directement reconnaissables figurent dans la barre sans texte
  répétitif ; les actions ambiguës conservent leur nom. Sous
  « Affichage », « Afficher les libellés d'outils » peut être désactivé
  pour réduire entièrement les deux barres à des icônes. Les infobulles
  et les menus restent alors entièrement libellés, le choix est
  mémorisé.

- **Le mode apprentissage est désormais visible en permanence dans la
  barre d'outils.** Il peut y être activé et désactivé directement,
  même quand le volet des valeurs remplacées est fermé. Barre d'outils,
  menu Outils et l'ancienne case dans le volet affichent toujours le
  même état.

- **« Réinitialiser » sur la loupe de comparaison ne réinitialise plus
  que son zoom.** Le bouton restaure le réglage par défaut de 125 %,
  sans ancrer la loupe, la déplacer ni modifier sa taille de fenêtre.
  Pour l'agencement complet, « Réinitialiser l'affichage » reste
  compétent.

- **Les erreurs et souhaits peuvent désormais aussi être signalés via le
  bouton d'aide.** « Signaler une erreur … » et « Exprimer un souhait … »
  s'y trouvent désormais tout comme dans le menu Aide classique ; les
  deux voies ouvrent le rapport d'erreur sécurisé déjà existant,
  respectivement la liste de souhaits publique.

- **Le menu de la barre des tâches est plus court et mieux ordonné.** Les
  deux commandes avec raccourci clavier global – nettoyage du
  presse-papiers et capture d'écran – figurent désormais immédiatement
  l'une sous l'autre avec une colonne de raccourcis commune à droite.
  « Restaurer le dernier contenu original » y disparaît ; le bouton de
  restauration plus compréhensible reste disponible dans la fenêtre
  principale.

- **Les pages légales sont directement accessibles sous « Aide →
  Mentions légales ».** Le sous-menu mène aux conditions de licence, à la
  déclaration de confidentialité, aux mentions légales et aux CGV sur
  maskuro.com. Les indications sur le droit de rétractation restent lors
  de l'achat sur le site.

- **Les PDF caviardés à la main sont entièrement reconstruits à
  l'enregistrement.** Restent visibles les pages et leur couche de
  recherche relue ; les métadonnées, pièces jointes, signets,
  commentaires, valeurs de formulaire, calques cachés, index de
  recherche, scripts, contenus tronqués et contenus cachés dans d'autres
  objets ne sont pas repris dans le fichier de sortie. Texte et
  graphiques vectoriels se composent ensuite de pixels – c'est le prix
  de la limite démontrable avec l'arbre d'objets PDF étranger.

- **Ctrl+Maj+B prend désormais par défaut une capture d'écran avec
  Maskuro sur tous les systèmes.** La touche Impr écran et ses
  combinaisons restent possibles comme affectation propre. Dans le menu
  de l'icône de la barre des tâches, les raccourcis clavier globaux
  figurent désormais à droite des commandes correspondantes. Les
  affectations propres enregistrées sont conservées.

- **L'éditeur démarre avec les pages et la loupe de comparaison à
  gauche.** Le volet des pages se trouve en haut, la loupe d'original
  ouverte juste en dessous ; les valeurs remplacées restent à droite. Un
  agencement propre délibérément enregistré reste prioritaire.

- **Le document d'exercice ne se trouve plus en permanence dans la
  fenêtre principale.** Il fait partie de la visite guidée et reste
  accessible en plus sous « Aide ».

- **Le premier démarrage mène directement à l'exercice pratique.** Le
  guide rapide illustré n'est plus proposé comme deuxième voie d'entrée
  au contenu redondant ; il reste accessible à tout moment sous
  « Aide → Guide rapide ».

- **L'icône de la barre des tâches au repos reste en couleurs
  pleines.** Elle affiche désormais le même bouclier Maskuro vif que le
  mode presse-papiers actif ; seul le point lumineux vert s'ajoute en
  cas de surveillance active.

- **Le document d'exercice reste dans Maskuro.** Le bouton d'entrée génère
  le PDF fictif et l'insère directement dans la liste de fichiers, mais
  ne démarre plus de visionneuse PDF supplémentaire.

- **La recherche dans la fenêtre de retouche reste fluide pendant la
  frappe.** La place pour le compteur de résultats est déjà réservée à
  l'ouverture ; son premier texte ne modifie plus la zone d'affichage et
  ne déclenche plus de nouveau passage de rastérisation PDF.

- **Les noms de fabricants dans les indications de marque restent
  visibles.** Une entrée comme « Fabricat : TRILUX ou équivalent »
  décrit la marchandise nécessaire et n'est plus caviardée comme
  entreprise pour ce seul libellé. Les champs fournisseur, entreprise et
  fabricant n'en sont pas affectés.

- **Les mesures de corpus comptent désormais les résultats trop
  largement caviardés comme faux positifs.** Quand Maskuro supprime le
  nom attendu mais emporte en même temps une partie de phrase, le nombre
  de faux positifs augmente désormais. Le rapport indique en outre les
  débordements séparément ; les anciens nombres de faux positifs ne sont
  donc pas directement comparables.

### Corrigé

- **Les termes techniques et administratifs issus de documents originaux
  allemands sont moins souvent caviardés comme noms ou lieux.**
  Équipements de véhicule, lignes de position et de total, termes
  d'attribution de marché et de protection des données, références
  légales ainsi que noms de fichiers de documents publics ne sont
  freinés qu'avec leur contexte factuel attesté. Un tréma perdu lors de
  la reconnaissance de texte dans « Marz 2026 » reste protégé en tant que
  mois ; « Marz » sans lien avec une date peut toujours être un vrai nom
  ou lieu.

- **« Récupérer l'original » prend immédiatement toute la largeur
  nécessaire.** Si le cadre ne touche qu'un mot d'une valeur associée,
  Maskuro l'étend automatiquement, à partir de l'affectation et de la
  ligne d'origine, à toute l'indication – par exemple de « Planungs » à
  « Nordlicht Planungs GmbH ». Le cadre ensuite manipulable affiche
  également la largeur totale réellement récupérée.

- **« Récupérer l'original » affiche désormais les barres noires comme
  cible univoque.** Au survol ou au tracé, toute la barre détectée
  s'allume en rouge avec un contour de contraste clair, au lieu d'un
  simple cadre de texte à peine identifiable à côté. Cela vaut aussi
  pour les pages rastérisées, où la barre ne se compose plus que de
  pixels.

- **La visite guidée de l'éditeur n'omet plus d'étapes quand des volets
  étaient fermés.** Pour la visite, Maskuro ouvre et organise
  temporairement lui-même le volet des pages, la loupe de comparaison et
  les valeurs remplacées. Après « Terminé » ou une interruption,
  l'agencement personnel revient. Si un outil n'est fondamentalement pas
  disponible pour un type de document, son explication reste comme
  point d'arrêt textuel, au lieu de disparaître sans se faire remarquer.

- **« Remplacer » reste visible même lors du repli de sécurité PDF.** Si
  Maskuro devait reconstruire une page en image à cause d'un caractère
  restant ou d'un flux de texte endommagé, les remplacements corrects ne
  figuraient plus que de façon invisible dans la couche de recherche, et
  des barres noires se trouvaient sur la page. Les valeurs de
  remplacement réellement posées restent désormais visibles en rouge et
  consultables par recherche à travers toutes les reconstructions par
  rastérisation et OCR.

- **Les indications au-dessus de la version nettoyée restent lisibles
  dans l'apparence sombre.** Le titre de version, la ligne de commande
  et l'introduction reprennent désormais directement leur couleur de
  police depuis la fenêtre Qt réellement affichée.

- **Les cadres de caviardage se trouvent de nouveau au-dessus du texte
  sur les pages PDF rastérisées.** Les cadres de mot invisibles étaient,
  selon la police d'origine, plus étroits que les lettres visibles.
  Cela créait des lacunes dans la barre ou laissait la dernière lettre
  lisible. Les cadres conservent désormais la largeur, la hauteur et le
  sens d'écriture du mot visible.

- **« Quoi de neuf » commence de nouveau tout en haut.** La boîte de
  dialogue du journal des modifications place désormais explicitement le
  curseur de texte et la barre de défilement au début après la
  construction complète de la fenêtre, au lieu de démarrer au milieu des
  nouveautés selon l'état de Qt.

- **La fermeture pendant la reconnaissance de mots du scan reste
  silencieuse.** Un passage OCR en arrière-plan qui se termine juste à ce
  moment n'envoie plus de données à une fenêtre de retouche déjà fermée.

- **Les indications de temps relatives ne sont plus prises pour des
  noms.** Des expressions fixes comme « heute », « gestern », « morgen »
  et « nächste Woche » sont désormais connues de Maskuro à partir des
  données calendaires officielles de la langue du document concernée.

- **Quitter pendant le premier chargement du modèle nettoie
  proprement.** Qui ferme Maskuro ou la fenêtre de retouche immédiatement
  après l'ouverture ne laisse plus de fil encore actif dans la
  détection linguistique native lors de l'arrêt du processus. Cela
  empêche le rapport de plantage sporadique à la fermeture ; un
  chargement déjà en cours est terminé de façon ordonnée.

- **Les boîtes de dialogue de démarrage différées n'apparaissent plus
  après la fermeture.** Qui ferme la fenêtre principale peu après le
  démarrage ne voit plus ensuite, invisible ou en retard, la question
  sur la meilleure détection, les nouveautés ou l'introduction s'afficher.

- **HTML et e-mail conservent leurs fins de ligne.** Sous Windows, la
  sérialisation HTML mélangeait LF et CRLF après nettoyage et
  récupération. Le contenu et le formatage étaient corrects, mais le
  fichier n'était plus identique octet pour octet. Les fichiers HTML et
  les messages MIME reprennent désormais de nouveau l'écriture de leur
  source.

- **Les raisons sociales avec un mot relationnel restent complètes.**
  Après une préposition, Maskuro tronquait des noms comme « Gesellschaft
  für Systemtechnik mbH » ou « Bank für Arbeit und Wirtschaft AG » au
  mot « für ». Le nom d'entreprise complet est désormais reconnu ; les
  véritables débuts de phrase comme « Wir sind bei Alpha GmbH versichert »
  restent visibles.

- **Les raisons sociales chinoises restent complètes devant leur forme
  juridique.** Un élément de marque interprétable comme verbe pouvait,
  malgré le suffixe univoque « 有限公司 », faire rejeter le nom entier.
  Dans les écritures sans majuscules ni minuscules, l'ancre officielle de
  forme juridique a désormais priorité sur cette frontière de nature de
  mot incertaine.

- **Des pages PDF devenaient des images sans nécessité.** Pour les PDF de
  plusieurs pages dont les pages partagent une liste de polices – ce que
  font les générateurs courants –, toutes les pages suivant la première
  perdaient la référence à leurs polices. La conséquence était double :
  les trémas n'étaient plus consultables par recherche dans le résultat
  (« Auftragsbestätigung » ne pouvait plus être trouvé), et la
  revérification prenait alors pour oubliées des lettres qui ne se
  trouvaient jamais sur la page – elle rastérisait des pages de texte
  intactes en images, les rendant ainsi non consultables par recherche,
  non copiables et nettement plus grandes. Dans le corpus de
  vérification, cela touchait quatre pages sur dix-sept.
- **Une simple virgule ne déclenche plus de rastérisation.** Si une zone
  de résultat se termine au mot, le signe de ponctuation juste à côté en
  fait tout juste encore partie. Mais une virgule ou un point n'est pas
  une donnée oubliée, et la rastérisation coûte la page entière. Les
  lettres et chiffres restent sans changement un motif de correction.

## 0.10.38-alpha.20260824 – 24 août 2026

### Nouveau

- **Les raisons sociales sans forme juridique sont désormais reconnues
  quand leur libellé les nomme.** « Lieferant: Kranzbichler Handels
  GmbH » était toujours déjà supprimé – la forme juridique trahit
  l'entreprise. « Lieferant: Dehner Märkte » restait en place, et dans
  les offres, appels d'offres et commandes, le fournisseur se présente
  le plus souvent exactement ainsi. Il en va de même pour « Firma: »,
  « Hersteller: », « Fabrikat: », « Arbeitgeber: » et leurs équivalents
  dans huit autres langues, y compris quand le libellé se trouve seul
  sur sa ligne et le nom en dessous.

  Ce qui, derrière le libellé, n'est *pas* une entreprise reste
  intact : « Lieferant: siehe Anlage » n'est pas caviardé – sinon on
  aurait « Lieferant: [ORGA1] », ce qui affirmerait un nom qui n'a
  jamais existé. Les libellés derrière lesquels se trouve tout aussi
  souvent une personne (« Kunde: », « Auftraggeber: ») en sont
  délibérément exclus.

- **Une image insérée peut désormais aussi être retravaillée.** Dans la
  fenêtre « Nettoyer une image », un bouton *Modifier dans l'éditeur*
  apparaît à côté de « Copier le résultat » : l'image est nettoyée puis
  ouverte pour retoucher, annoter et surligner – le même chemin que
  suit une capture d'écran.

- **Les numéros après leur libellé sont désormais trouvés même quand ils
  désignent un partenaire commercial.** Jusqu'ici tombaient les numéros
  de client, de contrat et de personnel ; désormais aussi le numéro de
  débiteur, de créditeur et de fournisseur, le numéro d'employeur
  autrichien, l'enregistrement ANKÖ et le numéro DEEE, EAR et REP d'un
  fabricant – en allemand comme en anglais. Maskuro comprend en outre
  désormais l'écriture des en-têtes d'offre composés avec espace avant
  le deux-points (« Kunden-Nr : K903944 »). Les numéros d'article, de
  commande, de mission, d'offre et de facture restent inchangés
  intacts : ils désignent le processus ou la marchandise, pas la
  personne. Qui veut quand même les supprimer les dépose comme modèle de
  recherche propre.

- **Vous voyez désormais combien de temps un fichier a pris.** Sur la
  ligne terminée figure la durée à côté de la langue détectée
  (« terminé · allemand · 2,4 s »), dans le résumé celle du passage
  entier, dans le volet des indicateurs le total – et dans le rapport
  de vérification elle figure comme champ propre. Avec plusieurs
  fichiers, la ligne révèle lequel a coûté le temps.

- **Les écritures non prises en charge par l'OCR système peuvent
  désormais être lues en substitution si le fichier de langue est
  présent.** Jusqu'ici : si la reconnaissance de texte du système ne
  maîtrisait pas une écriture (sur le Mac par exemple le devanagari), le
  résultat indiquait « Image(s) NON vérifiée(s) », et les indications
  dans l'image restaient en place. La reconnaissance de texte fournie
  prend désormais le relais si le fichier de langue adapté est
  présent. Comme une image ainsi lue est moins sûre qu'une image
  vérifiée normalement, cela figure dans le résultat : « lue avec le
  procédé de substitution – merci de vérifier ». Mesuré sur un état
  intermédiaire historique de l'essai hindi : **dix données de plus
  trouvées et quatre faux positifs de moins** (64 % → 73 %). La valeur
  finale actuelle figure plus haut et ne doit pas être confondue avec
  celle-ci.

- **La reconnaissance de texte demande la bonne langue.** Pour toutes
  les langues de document sauf l'allemand et l'anglais, le modèle de
  détection anglais était utilisé jusqu'ici, même quand le fichier de
  langue adapté était présent. Sous Windows, cela touchait chaque
  langue – le grec, le japonais ou le hindi y étaient lus avec le
  modèle anglais.

- **Un assistant de configuration au tout premier démarrage.** (Qui a
  déjà utilisé Maskuro ne l'obtient pas – « premier démarrage » signifie
  premier démarrage, pas premier démarrage après cette mise à jour.)
  Trois questions au lieu de six images : la langue de vos documents, si
  le texte dans les images est également lu, et comment vous voulez
  accéder à Maskuro au quotidien. À la fin, les trois voies restent
  proposées – document d'exercice, visite guidée ou le guide rapide
  illustré. Tout peut être passé, et « Aide → Refaire la
  configuration » le ramène.

- **F1 ouvre le manuel au chapitre correspondant.** Dans la fenêtre
  principale, dans les paramètres (selon la page), dans la fenêtre de
  consultation et dans la gestion des langues ; dans la fenêtre de
  retouche via Maj+F1, car F1 y affiche depuis toujours les raccourcis
  clavier. Jusqu'ici, l'aide commençait toujours en haut, à 25
  chapitres.

- **Nouveau premier chapitre du manuel : « Démarrer en trois
  minutes ».** Quatre étapes, il n'en faut pas plus pour un document –
  dans les 18 versions linguistiques.

- **Une visite guidée à travers la fenêtre.** « Aide → Visite guidée de
  la fenêtre » met en lumière un élément de commande après l'autre et
  écrit une phrase à côté – huit étapes dans la fenêtre principale, sept
  dans la fenêtre de retouche. Contrairement au guide rapide illustré,
  elle explique la fenêtre devant laquelle vous êtes assis à ce
  moment. Interruption possible à tout moment avec Échap.

- **Un document d'exercice pour essayer sans risque.** Sous la zone de
  dépôt figure désormais « Ouvrir le document d'exercice » (aussi dans
  le menu Aide). Il crée une feuille fictive – nom, adresse, numéro de
  téléphone, IBAN, numéro de sécurité sociale – et sur la feuille figure
  en même temps ce que vous pouvez en faire et ce que vous verrez
  ensuite. Aucun mot n'appartient à une personne réelle ; le premier
  document que vous envoyez à travers Maskuro n'a donc pas besoin
  d'être un vrai document.

- **« Juste vérifier … » figure désormais à côté de « Nettoyer ».** Il
  montre où se trouvent des données personnelles – fichier, type et
  nombre – sans rien modifier ni écrire. Qui a déposé un document
  vérifie ainsi avant de nettoyer. Jusqu'ici, ce chemin ne se trouvait
  que dans le menu Fichier sous « Parcourir un dossier … » et passait
  par un dossier entier au lieu des fichiers déposés.

- **Quand rien n'a été trouvé, la raison possible est désormais
  indiquée.** Par exemple : le fichier contient des images, mais
  « Vérifier aussi le texte dans les images » est désactivé. Ou : la
  langue réglée ne correspond pas à celle du document. Et si rien de
  tel n'est le cas, Maskuro le dit aussi.

- **La fenêtre de retouche vous accueille la première fois avec trois
  phrases :** cliquer caviarde un mot, tracer une zone, les valeurs
  remplacées figurent à droite. « Compris » retire l'indication de
  façon durable ; « Aide → Réafficher l'introduction » la ramène.

- **Cliquer sur des mots fonctionne désormais aussi sur des pages
  scannées.** Jusqu'ici, on ne pouvait cliquer sur des mots que là où le
  PDF apporte une couche de texte – pour un scan, ce n'était pas
  possible, et dans le même document cela pouvait changer de page en
  page. De telles pages sont désormais lues une fois par la
  reconnaissance de texte ; ensuite, on clique sur les mots comme
  partout ailleurs. La barre d'état indique ce qui se passe.

- **Le volet des pages est de nouveau une surface entière.** Il
  s'arrêtait au milieu de sa colonne : barre de titre coupée, à côté une
  bande d'une autre couleur, et la page actuelle n'était reconnaissable
  qu'à un cadre coloré derrière son numéro. Il remplit désormais sa
  colonne, peut être élargi, et la page actuelle est mise en évidence
  comme une tuile entière – avec un aperçu de page fidèle à l'intérieur.

- **Les emplacements remplacés s'illuminent en jaune pâle.** Dans
  l'aperçu des pages, on voit ainsi d'un coup d'œil où quelque chose a
  été remplacé – la même couleur qu'utilise la loupe de comparaison
  au-dessus de l'original. Le cadre rouge au survol de la souris reste
  inchangé.

- **« Réinitialiser l'affichage » dans la fenêtre de retouche** (menu
  « Affichage »). Qui a déplacé, détaché ou fermé le volet des pages ou
  la liste de résultats remet ainsi tout là où c'était au premier
  démarrage.

### Modifié

- **Les espaces réservés sont plus courts.** De `[SOZIALVERSICHERUNGSNR_1]`
  on obtient `[SVNR1]`, de `[ORGANISATION_1]` un `[ORGA1]`, de
  `[EMAIL_1]` un `[MAIL1]`. La raison n'est pas esthétique : un espace
  réservé plus long que la valeur qu'il remplace élargit la ligne et ne
  trouve parfois plus du tout de place dans une colonne de tableau
  étroite – il restait jusqu'ici une barre noire, qui ne dit plus à
  personne qu'il y avait quelque chose à cet endroit. Là où il existe
  une abréviation usuelle, elle est utilisée (`[BLZ1]`, `[KFZ1]`,
  `[IBAN1]`). Les résultats de passages antérieurs restent utilisables :
  l'ancienne écriture continue d'être reconnue, et les fichiers
  d'affectation d'hier fonctionnent sans changement.

- **L'icône du programme se présente désormais de façon identique
  partout.** Dans la barre de menu du Mac apparaissait jusqu'ici un
  bouclier unicolore que le système lui-même colorait en noir ou blanc,
  dans la barre des tâches Windows un vert ou un gris. Chaque barre
  porte désormais le même bouclier Maskuro bleu. Ce qui indique si le
  presse-papiers est surveillé reste tout aussi clair : si la
  surveillance fonctionne, un point vert se trouve sur le bouclier ; si
  elle est au repos, le même bouclier est pâle. Même dans les plus
  petites tailles, les deux barres de caviardage figurent désormais
  dans le bouclier – jusqu'ici, la barre des tâches n'en montrait qu'une.

- **Les visages sont reconnus avec un modèle dont les images
  d'entraînement ont été obtenues avec consentement.** Est désormais
  livré MediaPipe BlazeFace (Apache-2.0) ; l'ancien détecteur reste
  intégré et sélectionnable, mais n'est plus fourni, car la provenance
  de son entraînement n'est pas définitivement établie. Pour la
  détection, rien ne change : sur 324 portraits et 143 images sans
  visage, la nouvelle version trouve autant avec tout aussi peu
  d'erreurs et prend un tiers du temps.

- **L'OCR est l'ancre de sécurité pour la garantie PDF la plus
  forte.** Le passage PDF normal l'utilise et génère la construction
  minimale complète. Qui désactive l'OCR explicitement obtient le
  chemin objet plus compatible ; l'interface, le message de fin et le
  manuel indiquent désormais explicitement que ce chemin n'offre pas la
  même architecture contre les canaux PDF cachés inconnus.

- **Le verrou de vente bloque désormais aussi le modèle YuNet joint
  jusqu'ici.** La licence MIT du poids exact reste documentée, mais ne
  suffit pas comme homologation produit prudente pour la chaîne
  d'entraînement publiquement visible via WIDER FACE. Avant la vente,
  une clarification écrite ou l'échange contre un modèle avec une chaîne
  de données et de poids commerciale solide est nécessaire.

- **Les raisons sociales et noms d'organisation sont désormais
  supprimés d'eux-mêmes.** Jusqu'ici, ils restaient en place tant qu'on
  ne les demandait pas explicitement. C'était le mauvais réglage par
  défaut pour une lettre commerciale : qui transmet une offre ne veut
  pas que le donneur d'ordre y soit lisible. « Kranzbichler Handels
  GmbH », « Institut für Bauphysik » et similaires sont donc traités
  comme un nom. Qui en a besoin autrement le désactive dans la
  fenêtre ; en ligne de commande, l'interrupteur s'appelle désormais
  `--ohne-organisationen`. L'ancien `--mit-organisationen` continue
  d'être accepté et ne fait plus rien, afin que les scripts et
  raccourcis existants ne cassent pas. Les dates et montants restent
  exclus sans changement.

- **Le caviardage a désormais trois formes au lieu de deux cases.**
  « Mots », « Ligne entière » et « Cadre libre » figurent comme un choix
  côte à côte – exactement un seul s'applique toujours. Jusqu'ici,
  « Lignes de texte » et « Ligne entière » étaient deux interrupteurs
  indépendants qui pouvaient tous deux être actifs, et le cadre libre
  n'était pas du tout un bouton, mais l'état désactivé du premier. Les
  trois se trouvent visiblement à leur outil et sont grisés tant qu'un
  autre outil est sélectionné.

### Amélioré

- **Le premier document est terminé environ une seconde plus vite.**
  Avant que le nettoyage ne commence, Maskuro détermine la langue du
  document – et récupérait jusqu'ici pour cela les listes de mots des 48
  langues par un chemin qui chargeait bien plus que les mots. C'était
  environ la moitié du temps d'attente jusqu'au premier résultat. La
  détection elle-même est inchangée : elle voit les mêmes mots
  qu'avant, seulement plus vite. Chaque document suivant n'était de
  toute façon pas concerné.

- **Les documents avec de très longs paragraphes sont vérifiés plus
  vite.** Pour un paragraphe sans saut de ligne, Maskuro le relisait
  entièrement pour chaque emplacement trouvé ; une seule fois suffit
  désormais. Plus le paragraphe est long, plus la différence est
  grande – mesuré, environ un septième de temps de calcul en moins. Le
  résultat ne change pas.

### Corrigé

- **Avec une entreprise disparaissait souvent la moitié de la phrase.**
  Si une raison sociale figurait dans le texte continu – « Information
  über die Gottwald GmbH & Co KG », « … (AGB) der Musterbetriebe GmbH » –,
  non seulement le nom était caviardé, mais tout ce qui précédait
  jusqu'au début de la phrase. Le texte en devenait illisible, et cela
  avait l'air d'un caviardage aléatoire. Les raisons sociales qui
  portent elles-mêmes un « für » ou « und » (« Bank für Arbeit und
  Wirtschaft AG ») restent désormais entièrement intactes.

- **Des raisons sociales restaient dans les en-têtes de lettre, bien
  qu'elles aient été supprimées dans le texte.** Dans une offre, le
  siège de l'entreprise restait lisible dans l'image d'en-tête – le même
  lieu que Maskuro avait caviardé dans le texte continu ; dans le texte
  consultable par recherche du résultat, il figurait même encore
  invisible. Ce qui a été supprimé une fois est désormais aussi
  supprimé là où cela ne figure que comme image. Cela vaut aussi pour
  les logos et symboles verbaux dessinés comme graphique.

- **macOS demandait à chaque démarrage l'autorisation de capture
  d'écran**, même quand elle avait été accordée depuis longtemps.
  L'indication au démarrage testait une capture, et c'est exactement
  cela qui fait apparaître la boîte de dialogue système. Seul Maskuro
  demande désormais au démarrage, et une seule fois ; le système ne
  demande que quand vous prenez vraiment une capture d'écran.

- **Des termes techniques étaient pris pour des lieux et des
  entreprises.** « Einspeisepunkt », « Flachdach », « Verteileranlage »,
  « Meldersockel » et des dizaines de mots similaires disparaissaient
  des offres et cahiers des charges. Maskuro les reconnaît désormais à
  leur mot de base : ce qui se termine par « -anlage », « -punkt » ou
  « -kanal » est une chose. Les noms de lieu comme Berlin, Melk ou
  Wieselburg n'ont pas un tel mot de base et restent non affectés – de
  même que les adresses comme « Der Graben » ou « Alter Markt ».

- **Les documents japonais, coréens, chinois, thaïlandais et gujarati
  pouvaient faire planter le programme.** Si un document dans l'une de
  ces cinq langues contenait une adresse internet sans « https:// »
  devant, le nettoyage échouait avec une erreur interne – fenêtre
  ouverte, le reste du travail se perdait aussi. Les quarante-huit
  langues de document sélectionnables fonctionnent désormais toutes ;
  si le dictionnaire de fréquence manque pour une langue, la donnée
  reste en cas de doute plutôt que de disparaître.

- **Les libellés de champ ne protégeaient qu'en allemand et en
  anglais.** « Reference » restait en place, l'italien « Riferimento »
  et le portugais « Referência » étaient supprimés comme indication de
  lieu – même nom de champ, même ligne, résultat différent. Qui ne
  travaille pas en anglais était ainsi désavantagé. Maskuro connaît
  désormais les mêmes noms de champ dans les onze langues entretenues.

- **« Récupérer l'original » récupérait trop sur des pages scannées.**
  Un cadre sur une ligne caviardée d'un bloc d'adresse rouvrait
  **tout le bloc** – et la page restait déchirée : des restes de barre
  subsistaient, d'où dépassaient des fins de mot isolées. La cause était
  que des barres superposées sur une page rastérisée se touchent et
  comptaient donc comme une seule surface. Est désormais récupérée
  exactement la ligne visée par le cadre ; les lignes voisines restent
  caviardées, et la barre de la ligne touchée disparaît entièrement.

- **Des indications de quantité dans des listes de position étaient
  prises pour des adresses.** Dans une ligne comme
  « 1.4  Kabelgraben  100,00  m », « Kabelgraben 100 » était remplacé
  comme rue avec numéro de maison. De telles lignes restent désormais
  en place ; les vraies adresses – aussi « Hauptplatz 1, 3250
  Wieselburg » – continuent d'être reconnues sans changement.

- **Devant une raison sociale disparaissait la moitié de la phrase.**
  De « Vertrag zwischen der Firma Gottwald GmbH & Co KG und dem
  Auftraggeber. » on obtenait « [ORGANISATION_1] und dem Auftraggeber. »
  – le début de la phrase avait disparu, et avec lui l'indication du
  sujet. Seul le nom de l'entreprise lui-même tombe désormais. Là où le
  mot générique fait partie du nom (« Deutsche Bank AG », « Universität
  Wien »), tout reste comme avant.

- **Dans un procès-verbal, des intervenants dont le nom est aussi un
  métier restaient en place.** « Bauer: », « Koch: », « Weber: » devant
  une prise de parole étaient manqués, « Gruber: » à côté non – Maskuro
  avait jusqu'ici besoin d'au moins un nom reconnu dans le document pour
  lire les lignes comme des prises de parole. Si le document porte un
  titre comme « Ergebnisprotokoll » ou « Niederschrift », cela suffit
  désormais. Les lignes mnémotechniques (« Achtung: … », « Hinweis: … »)
  restent intactes.

- **Un libellé de champ disparaissait avec sa valeur.** De « Projekt:
  Sanierung und Erweiterung Gemeindezentrum » résultait un seul espace
  réservé – même le mot « Projekt: » avait disparu, et avec lui
  l'indication de ce qui se trouvait à cet endroit. Les libellés restent
  désormais en place. Là où un libellé fait partie de l'indication et en
  porte le sens (« Durchwahl 214 »), rien ne change.

- **La détection maximale ne débarrassait pas des termes
  techniques.** « Flachdach », « Einspeisepunkt », « Elektrotechnik » et
  des termes techniques similaires étaient remplacés comme lieu ou
  entreprise même avec le niveau IA activé – l'IA ne recevait jamais
  précisément ces résultats pour évaluation. Elle les vérifie désormais
  aussi : sur un corpus de textes d'appel d'offres et de contrat, les 27
  erreurs disparaissent ainsi, sans qu'une seule vraie donnée ne reste.
  Noms, entreprises et lieux continuent d'être reconnus sans
  changement.

- **Des mots génériques pour des types d'établissement étaient pris pour
  des organisations.** Dans un texte contractuel disparaissaient
  « Hochschulen und Universitäten », « Staatliche und private Schulen »,
  « Akademische Lehrkrankenhäuser », « Bildungseinrichtung » et
  « Zulieferfirmen » – des mots qui ne désignent pas un lieu précis, mais
  un type de lieu. Ils restent désormais en place. Si un nom propre les
  précède (« EU-Kommission »), le remplacement continue de s'appliquer,
  et les raisons sociales ne sont pas du tout concernées par cette
  règle.

- **Des noms dans des listes ne tombaient que s'ils étaient
  courants.** Dans une liste de participants ou de présence sous un
  en-tête de colonne « Name », « Anna Huber » et « Thomas Müller »
  étaient supprimés, mais pas « Wójcik Aleksandra » ou « Kücükgöl
  Sinan » – même ligne, même structure. Qui porte un nom plus rare était
  ainsi moins bien protégé. C'est désormais l'en-tête de colonne qui
  décide : ce qui se trouve sous « Name » est un nom. Une liste de
  position avec en-tête de colonne factuel reste non affectée.

- **Un numéro de téléphone après « Durchwahl » était coupé en son
  milieu.** De « Durchwahl 0732 771190 » on obtenait
  « [DURCHWAHL_1] 771190 » – la seconde moitié du numéro restait
  lisible. Le numéro complet tombe désormais entièrement, et le libellé
  reste en place. Un véritable poste (« Durchwahl 214 ») est remplacé
  sans changement, libellé compris.

- **Certains PDF ne pouvaient plus du tout être nettoyés.** Si un
  profil de couleur ou les métadonnées d'une image ne pouvaient pas être
  démontrablement supprimés, le passage échouait sans résultat – étaient
  touchés des documents commerciaux ordinaires comme des pages de CGV,
  des cahiers des charges et des appels d'offres. De tels fichiers sont
  désormais nettoyés, et un avertissement nomme les endroits restés
  ouverts : ils peuvent porter un identifiant d'appareil, de générateur
  ou de capture. L'original reste comme toujours inchangé.

- **Des rôles contractuels étaient pris pour des personnes.**
  « Bieter », « Verbraucher », « Mieter », « Käufer », « Auftraggebers »
  et une quarantaine d'autres mots de rôle étaient remplacés là où ils
  se trouvaient sans article – dans les titres de contrat, colonnes de
  tableau et lignes de signature. Un texte contractuel sans une seule
  donnée personnelle en devenait par endroits illisible. Ces mots
  restent désormais en place. Si une indication de personne se trouve à
  côté – une formule d'appel, un prénom, un mot de champ comme
  « Ansprechpartner » –, le remplacement continue de s'appliquer :
  « Herr Bieter » et « Frau Käufer » sont des noms. Les noms de famille
  fréquents qui sont en même temps des métiers (Bauer, Richter, Koch) ne
  sont pas du tout concernés par cette règle.

- **Une rue écrite en abrégé était manquée quand le numéro de maison
  collait directement au point.** « Schlesischestr.31 » ne comptait pas
  comme adresse – et comme le code postal à côté tire son ancrage du
  résultat d'adresse, il restait lui aussi en place. Dans le résultat,
  l'adresse composée de la rue et du code postal était de nouveau
  reconstituable, et cela seulement sur certaines pages du même
  document. Les deux tombent désormais ensemble. Les désignations
  factuelles avec nombre attaché (« Kabelrinne200 ») restent intactes.

- **Une adresse sur deux lignes était fusionnée en un seul espace
  réservé.** Si dans un bloc d'adresse le code postal se trouvait
  au-dessus de la rue, Maskuro reliait les deux lignes en un seul
  résultat : dans le résultat, le saut de ligne disparaissait, et le
  code postal restait lisible devant. Chaque ligne est désormais trouvée
  et remplacée pour elle-même, et la mise en page est conservée. La même
  cause entraînait parfois aussi le nom de famille de la ligne
  au-dessus dans l'adresse.

- **Le chemin PDF maximal ne reprend plus d'objets originaux.** Avec la
  reconnaissance de texte activée, Maskuro reconstruit désormais
  entièrement chaque page à partir de l'image PDFium visible. Dans le
  nouveau fichier minimal n'entrent que cette page image et une couche
  de recherche nouvellement générée, limitée au texte OCR – pas l'arbre
  d'objets étranger avec commentaires, pièces jointes, actions, calques,
  métadonnées, profils de couleur ou clés privées. Cela vaut aussi pour
  les contenus dans les apparences d'annotation, motifs, polices Type 3,
  objets de formulaire et masques de fondu. Le fichier source reste
  inchangé.

- **Des visages et codes dans des graphiques PDF imbriqués étaient
  manqués.** Les deux détecteurs voient désormais en plus l'image de
  page rendue complète. Les portraits et codes QR/à barres dans des
  annotations, motifs, glyphes Type 3 et masques de transparence
  atteignent ainsi aussi les détecteurs ; les zones détectées sont – si
  activé – rendues méconnaissables avant la construction minimale. La
  détection elle-même reste faillible.

- **Un moteur OCR manquant se terminait pour les PDF par une erreur
  interne.** Le passage maximal échoue désormais de façon contrôlée et
  sans fichier de destination, au lieu de produire un fichier incomplet
  ou non vérifié.

- **Plusieurs vraies valeurs de contact et commerciales passaient à
  travers pendant qu'un texte factuel était remplacé.** Champs de nom
  sur plusieurs lignes, noms de banque et d'entreprise, formes
  juridiques, numéros d'identification libellés, dates de naissance
  ainsi que les limites de téléphone, URL et IBAN sont vérifiés plus
  strictement. En même temps, les pays dans le texte factuel, les mots
  de rôle et génériques, les codes d'article/norme, les colonnes de
  chiffres et les abréviations courantes restent plus souvent intacts.

- **Les lignes OCR mixtes et tournées étaient mal lues.** Les mots
  verticaux incertains sont désormais relus localement redressés ; les
  valeurs latines techniques dans un texte non latin reçoivent un
  témoin anglais indépendant. Un chiffre isolé incertain n'est corrigé
  que si deux séquences de chiffres proches concordent. Les formes
  juridiques polonaises de forme OCR « sp. z 0.0. » sont lues dans un
  contexte fermé comme « sp. z o.o. ».

- **La mesure d'image pouvait manquer des restes de valeur partiellement
  visibles.** Elle vérifie désormais des extraits locaux qui se
  chevauchent, distingue l'écriture blanche d'espace réservé sur une
  barre noire des glyphes d'origine et applique aussi les cadres
  d'image brute sur des PDF minimaux tournés, re-rendus. Le corpus
  principal synthétique fixe atteint ainsi 1 392/1 392 données de
  référence supprimées pour 0 faux positif et 0 erreur de traitement.
  C'est une preuve de corpus, pas une promesse générale de 100 %.

- **Les modèles linguistiques non commerciaux ne sont plus
  proposés.** Les six variantes spaCy italiennes et grecques sous
  CC BY-NC-SA 3.0 sont retirées du catalogue, du téléchargement et du
  chemin de chargement ; les dossiers de modèle déjà présents sont
  également ignorés. Les deux langues utilisent désormais à la place le
  modèle multilingue sous licence MIT.

- **Le nom sous « Ansprechpartner » n'était retiré qu'à moitié.** Si le
  libellé se trouve seul sur une ligne et en dessous « Nachname
  Vorname », le prénom restait en place dès qu'il était en même temps
  un mot ordinaire – de « Mayer Roman » on obtenait
  « [NAME_1] Roman ». De telles lignes sont désormais prises
  entièrement. Un service au même endroit (« Technischer Innendienst »)
  reste toujours intact. Corrigé au passage : « Ansprechpartner » ne
  comptait pas du tout comme champ de nom, bien que « Kontaktperson » le
  fasse depuis toujours.

- **La raison sociale sans forme juridique restait en place quand un mot
  de branche s'interposait.** « Kranzbichler Handels GmbH » était
  supprimé, le simple « Kranzbichler » trois paragraphes plus loin non
  – alors que pour « Kranzbichler GmbH », si. Les deux fonctionnent
  désormais. Les mots ordinaires en sont exemptés : « Deutsche Bank AG »
  ne fait pas de « deutsche » dans le texte une entreprise.

- **La même valeur s'appelait dans le même document tantôt nom, tantôt
  lieu.** « Anna Musterfrau … Musterfrau » donnait « [NAME_1] » et
  « [ORT_1] » – au deuxième emplacement, le prénom manque, et sans lui
  c'est devenu un lieu. Les deux étaient supprimés, mais cela se lisait
  comme deux choses différentes. Une valeur conserve désormais la
  désignation de sa première occurrence.

- **Des dates n'étaient plus supprimées.** Une date entièrement en
  chiffres (« 01.03.2026 ») échouait depuis la dernière version à une
  vérification prévue pour les noms et restait dans le document – aussi
  en mode « décaler », et sans ligne dans le rapport de vérification.
  Seul était concerné qui avait explicitement activé les dates.

- **Les pays et continents ne sont plus caviardés.** « Die Lieferung
  geht in die Vereinigten Staaten », « Marktschwäche in Asien », « die
  Norm gilt in Rumänien » – de telles indications ne disent rien sur
  une personne et restent désormais en place. Si en revanche le nom du
  pays fait partie d'une adresse ou se trouve après un libellé comme
  « Wohnsitz » ou « Geburtsort », il continue d'être supprimé. **Les
  villes ne sont pas concernées** – « Ich bin gerade in Bilbao » reste
  une indication sur une personne et continue d'être caviardée.

- **Des mots abrégés devenaient des adresses web.** Si le texte contient
  « bzw. deutsche » ou « incl. der », certains PDF livrent le point sans
  espace – on obtenait ainsi « bzw.de » ou « incl.de », une adresse
  valide avec extension de pays, et elle était supprimée. De telles
  paires de mots restent désormais en place. Les vraies adresses ne sont
  pas concernées, pas même sans « www. » devant.

- **Des colonnes de chiffres issues de bilans étaient caviardées comme
  numéros de téléphone.** Dans les rapports de gestion et tableaux de
  prix, l'année précédente et l'année en cours figurent côte à côte –
  « 64.518  65.133 ». Cela comptait comme un numéro de téléphone et
  était supprimé, de même que des plages de chiffres comme
  « 12200-23200 » et une date suivie d'un chiffre. De tels nombres
  restent désormais en place. À l'inverse, un vrai numéro de téléphone
  est reconnu plus sûrement : les libellés « Telefon », « Fax »,
  « Mobil », « Durchwahl » et leurs équivalents dans les autres langues
  d'interface comptent désormais aussi – jusqu'ici, le programme n'y
  reconnaissait que les mots anglais.

- **Des noms dans un tableau numéroté restaient en place.** Une liste de
  participants ou un tableau de personnel dans la forme habituelle –
  en-tête de colonne, en dessous « 1.1 Auersperg Bernhard Montage
  03.03.2026 » – n'était pas du tout nettoyé : de telles lignes
  ressemblaient à la liste de position d'une offre, où les termes
  factuels doivent rester. Si l'en-tête de colonne porte un libellé de
  personne (« Name », « Nachname », « Surname » …), les lignes en
  dessous comptent désormais comme des noms. Les listes de position
  restent épargnées sans changement – même quand l'en-tête de lettre
  indique « Sachbearbeiter: ».

- **Un nom devenait parfois deux espaces réservés côte à côte.** Si un
  nom de famille figurait aussi seul dans le document, le passage de
  retraitement remplaçait à un endroit comme « Anna Musterfrau GmbH »
  d'abord le nom de famille puis le prénom – dans le résultat, cela
  ressemblait à deux personnes différentes. C'est désormais le nom
  connu le plus long qui l'emporte.

- **Les valeurs fictives ne figuraient dans aucune affectation.** Qui
  avait choisi « Inventer des valeurs » obtenait un résultat où « Anna
  Musterfrau » était devenu « Greta Mayrhofer » – rien de cela ne
  figurait dans l'affectation dès qu'un seul remplacement anonyme
  apparaissait aussi dans le même document. Aucune valeur fictive ne
  pouvait ainsi être récupérée, et le fichier d'affectation taisait le
  remplacement. Le plus délicat était le troisième point : qui lit le
  résultat voit un nom crédible et n'a aucun indice qu'il est fictif.
  Chaque remplacement figure désormais dans l'affectation.

- **L'affectation appelait « remplacé » ce qui était caviardé.** Un
  e-mail partage une affectation avec ses pièces jointes, et la pièce
  jointe peut être caviardée pendant que le texte du mail porte un
  espace réservé. Dans l'affectation figurait alors la même chose pour
  les trois emplacements – « remplacé » – et la récupération cherchait
  dans la pièce jointe un espace réservé qui n'y existe pas : la barre
  restait en place. Ce qui s'est réellement passé à chaque emplacement
  figure désormais, et les deux pièces jointes reviennent.

- **Des valeurs qui ne figuraient que dans une image ne pouvaient pas
  être récupérées.** Dans le panneau de résultats, elles figuraient en
  double – une fois comme espace réservé introuvable nulle part dans le
  document (« L'espace réservé n'a pas été trouvé dans le document »),
  une fois comme emplacement caviardé. La première ligne était de la
  pure comptabilité et a disparu.

- **Les valeurs caviardées ne pouvaient être récupérées qu'une seule
  fois.** Si la même valeur se trouve à plusieurs endroits, un clic les
  récupère tous – mais les autres lignes restaient dans le panneau de
  résultats, et le clic suivant dessus signalait « Non univoque ».
  Elles disparaissent désormais avec.

- **Des récupérations manquaient dans le journal de vérification quand
  le mode apprentissage était désactivé.** Qui restaurait une valeur
  récupérée dans la fenêtre de retouche ne retrouvait pas l'opération
  dans le journal de vérification dès que les questions d'apprentissage
  étaient désactivées – la preuve dépendait d'un interrupteur qui ne
  concerne que les suggestions de règles. Avec le journal de
  vérification activé, la raison est désormais demandée indépendamment
  de cela et la ligne écrite.

- **Des fichiers glissés dans le document restaient non nettoyés – et
  n'étaient même pas signalés.** Qui glisse un fichier dans un document
  au lieu de l'envoyer en pièce jointe le fait déposer entièrement par
  Word ou PowerPoint dans le document. Il restait ensuite inchangé dans
  le résultat, avec son nom de fichier et son chemin de dépôt d'origine
  – qui portent souvent eux-mêmes un nom en pratique. De tels fichiers
  sont désormais nettoyés comme le reste du document.

- **Et là où ce n'est pas possible, Maskuro le dit.** Si un objet
  intégré contient un ancien format (Word 97, Excel 97) pour lequel il
  n'existe pas de nettoyage, un message ATTENTION apparaît désormais
  avec le nom du fichier. Jusqu'ici, il était transmis silencieusement
  sans changement.

- **Des mots déchirés et des sigles étaient pris pour des noms.** Si un
  mot est coupé en fin de ligne dans un PDF, un fragment ressort à la
  lecture de certains fichiers – « Jahresent… gelts », « Gewerbli… ». De
  tels fragments, des mots collés (« TürverschlussmitV ») et des sigles
  nus (« JY », « FFB ») étaient caviardés comme s'ils étaient des noms.
  Ils restent désormais en place. Un nom avec le même dommage de
  coupure reste toujours caviardé tant qu'une formule d'appel
  l'accompagne – et les noms qui portent naturellement une majuscule au
  milieu du mot (McKenzie, MacDonald, LeBlanc) ne sont de toute façon
  pas concernés.

- **Des indications de mesure et des mois étaient pris pour des
  adresses.** Dans des documents techniques, « 2000 Lux », « 1200
  Mbit », « 1500 Watt », « 5308 Platz » et « 2022 Mrz » étaient
  caviardés – quatre chiffres et un mot en majuscule ressemblaient à un
  code postal avec lieu. Un code postal ne compte désormais plus que si
  un signal d'adresse l'accompagne également : un code pays, un libellé
  de champ, le début de ligne, une rue à la ligne au-dessus ou un lieu
  que la détection de langue y voit aussi. Dans cinq cahiers des
  charges, 14 caviardages erronés disparaissent ainsi, sans qu'une
  vraie adresse ne reste.

- **La détection plus précise remplaçait trop.** Le niveau activable
  « détection plus précise » prenait dans les documents commerciaux
  allemands des termes techniques pour des noms et des lieux –
  « Photovoltaikanlage », « Einspeisepunkt », « Flachdach »,
  « Personaleingang » – et caviardait des désignations d'entreprise
  issues de listes de position courantes. La cause était une protection :
  ses résultats étaient exemptés des vérifications qui reconnaissent une
  ligne de position ou de répertoire. Cette protection ne s'applique
  désormais plus qu'aux noms à plusieurs parties pour lesquels ce
  niveau existe – « Anna Huber » dans une ligne de répertoire reste
  donc reconnu, un terme factuel isolé dans une ligne de position
  disparaît. Dans un appel d'offres technique, cela réduit de moitié
  les caviardages erronés de ce niveau, sans qu'un nom ne se perde.

- **Les diagrammes apportaient leurs données source complètes – non
  vérifiées.** Qui insère un graphique dans Word ou PowerPoint fait
  déposer par le programme le tableau à partir duquel il a été calculé
  comme fichier propre dans le document. Seuls les quelques chiffres du
  graphique sont visibles ; dans le tableau se trouve la liste
  entière, y compris les lignes qui n'apparaissent pas du tout dans le
  graphique. Ce tableau était jusqu'ici transmis sans changement. Il est
  désormais nettoyé également, avec les mêmes espaces réservés que le
  reste du document.

- **De même pour les objets intégrés dans les fichiers OpenDocument**
  (ODT, ODS, ODP) : un graphique ou un tableau inséré restait intact.

- **Documents Word : les notes de bas de page et de fin n'étaient pas
  nettoyées.** Leur texte restait entièrement dans le résultat – noms,
  adresses et numéros de compte compris. Était concerné tout document
  Word avec une note de bas de page ou de fin. De même, un bloc de
  texte automatique voyageant invisiblement avec le document restait
  intact.

- **Word : indications dans les listes de sélection, commentaires et
  descriptions d'image.** Les entrées d'un champ de sélection (visibles
  seulement en le dépliant), l'auteur d'un commentaire, la description
  d'un dessin et l'adresse derrière une commande de renvoi restaient
  dans le résultat.

- **Excel : le tableau croisé dynamique consignait les données source
  une seconde fois.** Un classeur avec un tableau croisé dynamique y
  conserve une copie complète des lignes analysées – invisible, mais
  dans le fichier. Cette copie restait jusqu'ici inchangée, même quand
  tout était remplacé dans la feuille elle-même. Était concernée chaque
  analyse transmise avec un tableau croisé dynamique.

- **Excel : commentaires de conversation et leurs auteurs.** Le texte
  d'un commentaire du type le plus récent et le répertoire des personnes
  commentant – nom d'affichage et identifiant de connexion, dans les
  entreprises le plus souvent l'adresse e-mail – restaient dans le
  résultat. Le même répertoire aussi dans les documents Word.

- **Propriétés de document personnalisées dans Word et Excel.** Des
  champs comme « Mandant » ou « Aktenzeichen », qu'un cabinet ajoute à
  ses modèles, n'étaient jusqu'ici pas nettoyés. Ils ne sont visibles
  dans aucune vue et voyagent quand même avec chaque copie.

- **Tableaux (ODS) : la liste de sélection d'une cellule.** Comme dans
  Excel depuis la version précédente, ce qui apparaît en dépliant une
  cellule est désormais aussi nettoyé dans les tableaux OpenDocument.
  Les références à d'autres cellules ne sont pas touchées, afin que la
  liste continue de fonctionner.

Tous ces emplacements peuvent, comme d'habitude, être récupérés via
l'affectation.

- **Messages Outlook : un fichier endommagé interrompait le nettoyage de
  façon brutale.** Certains fichiers `.msg` cassés provoquaient un
  arrêt au lieu d'un message ; ils sont désormais lus dans la mesure où
  ils sont lisibles.

- **Le fichier d'affectation n'est désormais lisible que par vous.** Il
  contient les données d'origine en clair et se trouvait jusqu'ici avec
  les droits habituels à côté du résultat – sur un dépôt partagé,
  quiconque pouvait donc l'ouvrir. Le résultat nettoyé lui-même ne
  change en rien ; il est en effet destiné à être transmis.

- **Les modèles linguistiques rechargés sont désormais vérifiés plus
  précisément avant décompression.** Un paquet manipulé – par exemple
  issu d'une diffusion d'entreprise alimentant plusieurs postes de
  travail – pouvait déposer des fichiers en dehors du dossier prévu lors
  de la décompression. Le rechargement habituel ne change en rien.

- **Prendre une capture d'écran – et elle est nettoyée aussitôt.** Avec
  `Ctrl+Maj+B`, via « Fichier → Prendre une capture d'écran … » ou via
  l'icône dans la barre des tâches, vous tracez un cadre sur l'écran. Ce
  qui s'y trouve suit ensuite le même chemin que tout autre fichier : la
  reconnaissance de texte lit le texte de l'écran, noms, adresses,
  numéros de téléphone et adresses e-mail sont caviardés, et l'image
  s'ouvre ensuite dans l'éditeur, où vous pouvez caviarder à la main ce
  qui a été manqué. L'image nettoyée atterrit sur le bureau (ou dans
  votre dossier de sortie réglé) ; la capture **brute** n'est déposée
  nulle part et est supprimée en quittant. La reconnaissance de texte
  est activée pour ce passage, même si elle est désactivée par ailleurs
  – sans elle, il n'y aurait rien à trouver dans une image. Sur le Mac,
  le système demande la première fois l'autorisation
  « Enregistrement d'écran ».

- **On peut désormais dessiner sur les images : rectangle, ellipse,
  flèche, texte et marques d'étape numérotées.** En six couleurs et
  trois épaisseurs de trait, sélectionnables avec les touches 1 à 5.
  Cela est conçu pour les captures d'écran et les guides : montrer ce
  qui compte sans ouvrir un second programme. Annuler et le
  redimensionnement aux poignées fonctionnent comme pour toute barre –
  une annotation peut donc être déplacée et redimensionnée après avoir
  été posée.
  **Dessiner n'est explicitement pas caviarder.** Un rectangle dessiné
  est un cadre, pas une barre : ce qui se trouve en dessous reste
  lisible et sort avec le fichier. Pour supprimer des données,
  « Caviarder » et « Pixeliser » restent disponibles ; les outils de
  dessin se trouvent donc dans une ligne propre de la barre d'outils, et
  la ligne d'indication le rappelle tant que l'un d'eux est
  sélectionné.

- **L'image retravaillée passe d'un clic dans le presse-papiers.**
  « Copier l'image » dans l'éditeur (ou `Ctrl+C`) la dépose telle
  qu'elle se présente – coller suffit pour la mettre dans un message ou
  un mail. Le chemin de l'appui sur la touche jusqu'au chat compte
  ainsi quatre étapes et ne nécessite pas de dossier.

- **De plus, un surligneur, des ombres et des dégradés.** « Surligner »
  colore une surface sans la masquer – le contenu en dessous reste
  lisible, et c'est exactement ce qui le distingue de la barre.
  « Ombre » détache une annotation d'un fond agité, « Dégradé » fait
  s'estomper la couleur dans le sens du tracé ; les deux s'appliquent
  aux six outils de dessin.

- **Corrigé avant que quiconque ne soit touché :** la nouvelle ligne
  d'outils serait apparue presque vide pour tous ceux qui avaient déjà
  utilisé Maskuro – la disposition de fenêtre mémorisée datait d'avant
  et ne lui aurait laissé aucune place. Une disposition obsolète est
  désormais rejetée ; la fenêtre de l'éditeur se présente alors une fois
  dans sa disposition de base.

- **Votre propre capture d'écran peut être désactivée.** Qui a
  l'habitude de Greenshot, ShareX ou de l'outil Capture désactive sous
  « Paramètres → Programme » « Prendre une capture d'écran avec
  Maskuro ». Maskuro n'enregistre alors même plus le raccourci clavier –
  il reste à votre outil –, et le changement s'applique immédiatement,
  sans redémarrage. Une image ainsi capturée peut toujours être
  nettoyée : Ctrl+V la récupère du presse-papiers dans la fenêtre.

---

## 0.10.37-alpha.20260821 – 21 août 2026

### Nouveau

- **Lors de l'anonymisation, chaque emplacement trouvé porte désormais son
  propre numéro.** Jusqu'ici, toutes les personnes s'appelaient `[NAME]`,
  tous les lieux `[ORT]` – on ne pouvait donc plus dire quel emplacement
  appartenait à quelle valeur, et il n'y avait rien à récupérer.
  Désormais, les numéros continuent de compter par occurrence : le même
  nom figure à trois endroits comme `[NAME_1]`, `[NAME_3]` et
  `[NAME_7]`. Dans le document, on ne voit toujours pas quels
  emplacements vont ensemble – mais avec le fichier d'affectation,
  chacun peut être récupéré individuellement. Le fichier d'affectation
  est donc de nouveau sélectionnable même lors de l'anonymisation ;
  conservez-le séparément du résultat.
- **Les mois, jours de la semaine, devises, unités et formes juridiques
  d'entreprise dans les 48 langues de document ne comptent plus comme
  noms ou lieux.** Les noms de calendrier et d'unités proviennent
  d'Unicode CLDR (générés, pas écrits à la main), les formes juridiques
  du droit des sociétés des pays – y compris à plusieurs mots
  (« sp. z o.o. », « Pty Ltd ») et placées devant (« 株式会社 »). Là où un
  nom de mois est en même temps un prénom (Juli, August, May), la forme
  décide : avec un jour ou une année à côté, c'est une date, sinon un
  nom. S'y ajoutent formules d'appel et titres, formules de politesse
  entières, types de document et mots de base de rue pour 28 langues
  avec modèle linguistique propre, sigles de loi (DSGVO, UStG, ABGB,
  § 6 Abs 1 Z 27 UStG) ainsi que noms de langue comme valeur de champ
  (« Langue : allemand »). Les listes se trouvent sous
  « Aide → Listes de mots … ».
- **Inde : adresse et code PIN sont reconnus** – « 15 गांधी मार्ग »,
  « नई दिल्ली 110001 » de même que « 15 Gandhi Marg, New Delhi 110001 ».
  Le paquet pays Inde ne connaissait jusqu'ici que les numéros
  d'identification ; dans les documents en hindi, les adresses
  restaient donc en place.
- **Chaque fichier Office nettoyé est de nouveau ouvert comme paquet
  avant remise.** Un extrait de texte ne remarque pas si Word, Excel ou
  LibreOffice refuseraient le fichier (entrée en double, XML rompu,
  partie manquante). Et ce qu'un nettoyage ne doit jamais changer est
  compté par rapport à l'original : pages d'un PDF, feuilles, lignes et
  cellules d'un tableau, diapositives d'une présentation. Si le test
  déclenche, un avertissement ATTENTION figure dans le résultat et dans
  le rapport de vérification – l'original reste inchangé.
- **L'automatisme aussi caviarde le champ entier.** En mode caviardage,
  la barre dans les lignes courtes – bloc d'adresse, cellule de tableau,
  données d'en-tête – couvre désormais toute la ligne au lieu de
  seulement la valeur trouvée : une barre de la longueur du mot trahit
  la longueur du mot. Le libellé et les montants à côté restent en
  place, et les lignes de texte continu (plus longues que la moitié de
  la largeur de texte) continuent d'être caviardées mot par mot, afin
  qu'un nom en plein milieu de la phrase ne noircisse pas toute la
  phrase.
- **Ce qui est récupéré ressemble de nouveau à l'original.**
  « Récupérer l'original » et « Annuler le remplacement » dans l'éditeur
  PDF réécrivent désormais la zone exactement à partir du fichier
  source – même police, même taille, même couleur et même position, sur
  un scan les mêmes pixels. Jusqu'ici, le texte était réinséré dans une
  police de substitution et avait un aspect reconstitué reconnaissable.
  La barre d'un ancien caviardage disparaît alors entièrement, au lieu
  d'être recouverte de blanc – un fond de cellule coloré dans un tableau
  est conservé. Cela vaut aussi sur les pages tournées, pour le texte
  issu d'objets de formulaire intégrés et pour les **champs de
  formulaire remplis** : sur la copie de travail rastérisée à cet effet,
  l'extrait de la page originale re-rendue revient – même là où aucune
  couche de texte ne connaît la valeur du champ. Les **images
  remplacées** dans le PDF reviennent également ainsi – pixelisées,
  floutées ou entièrement supprimées, en entier ou seulement l'extrait
  tracé. Ce n'est que là où le fichier source ne se trouve plus à côté
  du résultat que l'on en reste à l'ancienne méthode.
- **Les valeurs caviardées et supprimées sans remplacement peuvent
  aussi être récupérées dans Word, Excel, PowerPoint et
  OpenDocument.** Jusqu'ici, la récupération y avait besoin d'un espace
  réservé dans le texte – une barre ou un vide n'avait pas de retour.
  Désormais, le panneau de résultats propose les lignes « caviardé » et
  « supprimé » dès que le fichier source intact se trouve à côté du
  résultat : Maskuro compare le résultat à l'original et réinsère la
  valeur à l'emplacement de la barre ou du vide – avec sa mise en forme,
  un passage de texte fragmenté redevient entier. Vaut aussi pour le
  texte, HTML, l'e-mail et les pièces jointes Office d'un e-mail ; si le
  texte du mail porte un espace réservé et la pièce jointe une barre,
  les deux sont récupérés en une seule opération.
- **Les pièces jointes PDF d'un e-mail ou d'un message Outlook peuvent
  aussi être récupérées** – espaces réservés (numérotés et anonymes),
  barres et éléments supprimés sans remplacement. Sans support visuel,
  l'emplacement provient de la pièce jointe originale ; la valeur
  revient au glyphe près, dans l'ordre de lecture de l'original.
- **Les valeurs masquées peuvent être récupérées** – dans le PDF et
  dans la vue texte. Un masque (« **** **** **** **** 3201 ») n'est
  jamais univoque, deux numéros peuvent porter le même ; c'est pourquoi
  la récupération ne prend jamais la voie littérale, mais demande à
  l'original quelle valeur se trouvait à cet emplacement. Jusqu'ici, ces
  lignes n'étaient même pas utilisables dans le panneau de résultats.
- **Les images intégrées dans Word, Excel, PowerPoint et OpenDocument
  peuvent être récupérées.** Une valeur caviardée dans l'image revient
  via sa ligne de panneau – Maskuro lit l'image originale et récupère
  exactement cet emplacement ; une image floutée, supprimée ou traitée
  avec des visages et des codes est récupérée dans son ensemble par la
  nouvelle entrée « Récupérer les images intégrées » du menu Édition –
  aussi à travers les pièces jointes Office d'un e-mail ou d'un message
  Outlook. Une image qui se trouve elle-même en pièce jointe et a été
  caviardée par reconnaissance de texte revient également via sa ligne
  de panneau.
- **Les valeurs fictives peuvent être récupérées dans la vue texte.**
  Jusqu'ici, le panneau y signalait « Non univoque ». Désormais, la
  récupération recherche la valeur dans l'original et exige exactement
  le remplacement fictif au même emplacement dans le résultat – un nom
  fictif n'est jamais remplacé littéralement partout, il pourrait
  figurer réellement quelque part.
- **La récupération dans Word, Excel, PowerPoint et OpenDocument
  conserve la mise en forme de l'original.** Si une valeur s'étendait
  sur plusieurs passages – « Anna » normal, « Musterfrau » gras et rouge
  –, elle revenait jusqu'ici entièrement dans le premier passage et
  perdait le gras et la couleur. Les caractères se répartissent
  désormais de nouveau comme dans l'original ; un paragraphe Word est
  ensuite identique octet pour octet à l'original. Il en va de même pour
  les pages HTML, la partie HTML d'un e-mail et le corps HTML d'un
  message Outlook (.msg) – pour l'e-mail, le Doctype est en outre
  conservé, alors que le nettoyage le supprimait jusqu'ici
  silencieusement.
- **Les fichiers texte conservent leur encodage.** Le nettoyage et la
  récupération écrivent désormais `.txt`, `.md` et `.csv` dans
  l'encodage dans lequel ils ont été fournis – UTF-8 avec et sans BOM,
  UTF-16, Windows-1252. Jusqu'ici, un fichier Windows-1252 devenait
  toujours UTF-8, et un fichier UTF-16 revenait endommagé, même si rien
  n'y était à remplacer.
- **Les images récupérées conservent leur mode couleur.** Un scan en
  niveaux de gris revient en niveaux de gris au lieu d'un fichier RVB
  trois fois plus gros, une palette reste une palette, le noir et blanc
  reste noir et blanc – pour l'image entière, avec les mêmes valeurs que
  dans l'original. Vaut pour les fichiers image et pour les images dans
  les PDF. Le CMJN et le 16 bits restent en RVB, car le résultat PNG ne
  peut porter ni l'un ni l'autre.
- **Un cadre dans l'image récupère toute la modification qu'il
  touche.** Les visages pixelisés portent une bordure autour de la
  zone détectée ; qui ne traçait le cadre que sur le visage gardait un
  anneau pixelisé. Le cadre s'étend désormais à la modification
  contiguë par rapport à l'original – un cadre sur la zone des yeux
  suffit. Les barres séparées à côté restent en place ; pour une photo
  entièrement supprimée ou entièrement floutée, le cadre tracé continue
  de s'appliquer. Vaut pour les fichiers image et les images dans les
  PDF.
- **Barres de caviardage sur toute la ligne.** En mode ligne de
  l'éditeur, la barre s'étend désormais du premier au dernier mot de la
  ligne, plus seulement sur le mot touché – une barre de la longueur du
  mot trahit la longueur du mot, et six caractères devant un code postal
  laissent deviner un nom de lieu. Les libellés, montants et colonnes de
  tableau à côté de la valeur restent en place – la barre couvre le
  champ, pas la ligne de la facture. Le nouvel interrupteur
  « Ligne entière » à côté de « Lignes de texte » repasse en mode mot
  par mot quand les mots voisins doivent rester ; le choix est
  mémorisé.

### Corrigé

- **Les images dans les pages HTML et les e-mails restaient non
  vérifiées – le nom dans le logo restait lisible après le
  nettoyage.** Une image intégrée dans la page (adresse ``data:``)
  n'était pas touchée du tout, seul son texte alternatif l'était ; le
  logo dans la branche HTML d'un mail (image en ligne sans nom de
  fichier) échappait au filtre de pièces jointes ; et pour la pièce
  jointe image nommée, la règle d'image « flouter »/« supprimer » restait
  sans effet. Les trois suivent désormais le même chemin qu'un fichier
  image : reconnaissance de texte dans l'image conservée, visages,
  codes, métadonnées et règle d'image. Le rapport nomme les images –
  aussi l'avertissement quand elles restent non vérifiées sans
  reconnaissance de texte –, et « Récupérer les images intégrées » ainsi
  que la récupération depuis le panneau de résultats connaissent
  également ces images.
- **Un fichier Office avec image ne pouvait pas du tout être nettoyé
  quand la reconnaissance de texte ne maîtrisait pas la langue.** Sur le
  Mac, la reconnaissance de texte du système fait la lecture ; pour le
  hindi, le grec, le croate ou le lituanien, elle ne le peut pas et le
  signale désormais aussi – mais pour Word, Excel, PowerPoint et
  OpenDocument, **tout** le nettoyage échouait pour cela, et aucun
  fichier n'était créé. Pourtant, le texte pouvait être nettoyé
  parfaitement ; seule l'image n'était pas lisible. Le fichier est
  désormais écrit comme pour un PDF et des images isolées, et le
  résultat indique que les images n'ont PAS été vérifiées – avec la
  raison et un renvoi vers « Gérer les langues ».

- **Dans les classeurs Excel, des noms restaient dans les listes de
  sélection.** La liste d'un champ déroulant (validation des données)
  est désormais nettoyée comme tout autre contenu de cellule ; les
  références à des plages de cellules ne sont pas touchées, afin que le
  classeur reste intact.
- **Là où l'espace réservé ne rentrait pas, il y avait une barre noire –
  il y a désormais une écriture plus courte.** `[GEBU_1]` au lieu de
  `[GEBURTSDATUM_1]`, et ce n'est que quand même la forme la plus courte
  ne rentre plus qu'un caviardage a lieu. Une barre ne dit plus à
  personne qu'il y avait quelque chose ; un espace réservé court le
  dit. L'éditeur de retouche le savait déjà faire, le nettoyage
  automatique pas jusqu'ici. Le fichier d'affectation associe les deux
  écritures à la même valeur, afin que la version raccourcie puisse
  aussi être récupérée.
- **Le premier clic sur « Remplacer » figeait brièvement la fenêtre de
  retouche.** La détection qui donne son type à l'espace réservé
  (`[NAME_3]` plutôt que `[BEGRIFF_3]`) n'était chargée qu'à ce moment
  précis – environ deux à trois secondes. Elle est désormais préparée
  en arrière-plan à l'ouverture de la fenêtre ; mesuré, on est passé de
  2289 millisecondes à 193.
- **Deux nettoyages simultanés pouvaient charger le même modèle
  linguistique en double** – par exemple la surveillance de dossier et
  la fenêtre principale. Chaque modèle occupant plusieurs centaines de
  mégaoctets, le besoin en mémoire doublait brièvement. Le second
  passage attend désormais le modèle du premier.
- **Le lieu dans la ligne de date est désormais supprimé même quand le
  modèle linguistique ne le reconnaît pas seul :** ce qui est trouvé de
  façon sûre comme code postal avec lieu (« 3335 Amstetten ») entraîne
  son nom de lieu dans tout le document – comme un nom de famille à
  partir d'un nom complet. Et un sigle avec chiffre devant un nom
  (« T3 Hofbauer Christian ») reste lisible, au lieu de disparaître avec
  l'espace réservé.
- **Trois failles issues de la relecture d'une vraie commande
  fermées :** le chargé de dossier « T3 Hofbauer Christian » était
  considéré, à cause du sigle « T3 », comme un en-tête de colonne et
  restait lisible ; un lieu que le modèle linguistique lisait à travers
  le saut de ligne jusque dans l'en-tête de colonne avalait « Pos. » et
  laissait le prénom du client en place ; et un nom avec formule d'appel
  (« Herr Robert Köttel ») n'entraînait que le nom de famille, pas le
  prénom – et pour cela chaque « Herr ». Les sigles sont désormais de
  purs caractères, les noms à deux mots ne forment pas un en-tête, les
  résultats sont coupés avant un en-tête de colonne, et la formule
  d'appel ne compte pas dans le nom.
- **Le lieu dans la ligne de date (« Melk, 05.08.2026 ») directement sous
  le bloc d'adresse restait lisible.** Le modèle linguistique le
  collait au lieu de la ligne de code postal pour n'en faire qu'un
  résultat, qui tombait dans son ensemble contre le modèle de code
  postal. Le reste qui dépasse reste désormais un résultat propre.
  Trouvé grâce à la nouvelle relecture du résultat
  (`werkzeuge/zweitlesung.py`).
- **Mac : un scan dans une langue que la reconnaissance de texte du
  système ne maîtrise pas (par exemple hindi, grec, croate, lituanien)
  était considéré comme vérifié.** La lecture se faisait avec le
  repli anglais, l'écriture étrangère restait dans l'image, et le
  rapport disait « rien trouvé ». Il indique désormais « Image(s) NON
  vérifiée(s) » avec la raison, et la gestion des langues ne promet
  plus de reconnaissance de texte pour de telles langues, simplement
  parce qu'un fichier de langue Tesseract est présent.
- **Dans le PDF, le signe de ponctuation après une valeur remplacée
  reste en place.** De « Aufnahme am 01.03.2026, Entlassung am
  04.03.2026. » on obtenait jusqu'ici « Aufnahme am [DATUM_1] Entlassung
  am [DATUM_2] » – virgule et point final manquaient, aussi bien pour
  les espaces réservés que pour les dates décalées. Seule la valeur
  détectée est désormais supprimée, pas tout le mot jusqu'au prochain
  espace ; virgule, point-virgule, point ou parenthèse restent à leur
  place, et l'espace réservé ne les recouvre pas.
- **Le russe et l'ukrainien fonctionnaient sans que cela se remarque
  avec le modèle multilingue plus faible** quand un paquet auxiliaire
  pour l'analyse des formes de mots (`pymorphy3`) manquait – les
  modèles propres ne pouvaient alors pas être chargés, et « Львів »
  devenait une personne. L'analyse des formes de mots n'est pas
  nécessaire pour la détection des noms ; le modèle est désormais chargé
  sans elle, et les lieux redeviennent des lieux.
- **Les mentions de licence dans 16 langues étaient obsolètes.** On y
  lisait encore que le code source MPL était fourni « sur demande »,
  QPDF y était compté comme MPL-2.0, sept composants manquaient au
  tableau (wordfreq, Qt, ONNX Runtime, tokenizers, zxing-cpp, llama.cpp,
  YuNet), le paragraphe spaCy était en anglais, et à la fin figurait un
  paragraphe de substitution en anglais. Les 18 versions sont désormais
  au niveau de l'allemande : archives source durablement sous
  maskuro.com/quellcode/oss/, QPDF Apache-2.0, chemin Qt-LGPL,
  provenance des modèles. Le tableau anglais a également les lignes
  manquantes.

- **Les mots de contrat au génitif (« des Angebotsinhaltes », « des
  Anbotes », « des Terminplanes ») ne comptent plus comme lieu.** Un mot
  isolé après un article génitif ou datif avec terminaison fléchie est
  un nom commun – les noms de lieu ne se déclinent pas
  (« nach Graz »). Si le lieu figure ailleurs dans le document sans
  article (« Burgenland »), « des Burgenlandes » reste également
  reconnu.
- **Les valeurs décalées, masquées et fictives déclenchaient la
  rastérisation de la page PDF.** La revérification après suppression
  n'autorisait dans le rectangle trouvé qu'un espace réservé entre
  crochets ; une date décalée (« 01.07.2026 ») ou une valeur masquée
  (« ****1234 ») étaient considérées comme un reste oublié, et la page
  était par précaution convertie en image – pas pour « Remplacer ». De
  telles pages restent désormais du texte, et la récupération depuis le
  panneau ou le cadre restitue de nouveau l'original.
- **Les valeurs de remplacement à plusieurs mots ne pouvaient pas être
  annulées dans le PDF via le panneau de résultats.** Un nom fictif
  (« Greta Mayrhofer ») ou un IBAN masqué (« **** **** **** **** 3201 »)
  se compose de plusieurs mots ; la recherche d'emplacement comparait
  mot par mot et signalait « L'espace réservé n'a pas été trouvé dans le
  document ». Des mots consécutifs de la même ligne sont désormais lus
  ensemble.
- **Après la récupération d'une valeur supprimée sans remplacement, sa
  ligne de panneau restait affichée.** Les valeurs que la stratégie
  « caviarder » supprime sans remplacement en mode espace réservé n'ont
  pas d'espace réservé sur lequel le panneau pourrait mesurer une
  disparition. La ligne est désormais rayée dès que la valeur se
  retrouve dans le document.

- **Les mots composés abrégés comme « E-Helfer » ou « U-Bahn » ne
  comptent plus comme nom.**
- **Les restes de coupure de mots (« Leis- ») et les mots composés
  extrêmement longs (« Bauarbeitenkoordinationsgesetzes »,
  « Baustellenkoordinator ») ne comptent plus comme nom ou lieu.** Dans
  un texte d'appel d'offres scanné, 28 mots de moins ont ainsi été
  caviardés.
- **Les listes de positions d'offres scannées ne comptent plus comme
  répertoire de noms.** Le passage supplémentaire pour répertoires
  (lignes courtes) transformait « Kälterohr » et « Außengeräte » en
  personnes ; il se suspend désormais dès que des numéros de position
  comme « 1.1.5 » figurent en début de ligne. Les lignes de date dans
  les fils de mail ne comptent pas comme numéros de position.
- **Les en-têtes de colonne et numéros de position d'offres scannées
  (« Pos. », « Pos. 1.1.3 », les sigles « E/L/S ») étaient considérés
  comme nom ou lieu.** Une abréviation seule sur sa ligne, un libellé
  avec numéro et des lettres isolées ligne par ligne n'en sont pas.
- **La page « respirait » dans la fenêtre de retouche après l'ouverture
  de la loupe de comparaison** – pour « Largeur de page » et
  « Ajuster », l'échelle dépend de la fenêtre visible, qui change à
  chaque barre de défilement qui apparaît ou disparaît ; chaque action
  suivante décalait la page d'un cran. La zone d'affichage rattrape
  désormais cela d'elle-même, jusqu'à stabilisation. Et les boutons de
  zoom, curseurs et raccourcis clavier maintiennent le centre de l'image
  même si une barre de défilement apparaît lors du zoom avant.
- **Les scans enregistrés en travers sont désormais lus à
  l'endroit, et les petits caractères dans les grands scans ne se
  perdent plus.** Une offre scannée de 24 pages gardait dans chaque pied
  de page six IBAN bancaires, le numéro de registre du commerce et
  l'UID lisibles : le scan était tourné de 90° dans le PDF, et la
  reconnaissance de texte omettait des lignes entières selon la taille
  de l'image pour les très grandes images. La rotation visible est
  désormais prise en compte et les grandes images sont lues par bandes
  chevauchantes – les pieds de page sont noirs.
- **Les rues nommées d'après des personnes avec trait d'union avant le
  mot de base (« Josef Admanseder-Straße 7 », « Abt-Karl-Straße 8 »,
  « Dr.-Karl-Renner-Straße 12 ») sont reconnues comme adresses.** Dans
  l'en-tête d'une offre scannée, une telle adresse restait lisible, car
  le modèle exigeait un espace avant « Straße ».
- **Les IBAN issus de la reconnaissance de texte, portant un O au lieu
  d'un 0 ou un l au lieu d'un 1, sont désormais reconnus.** Dans les
  petits caractères d'un scan, la reconnaissance de texte lit volontiers
  des chiffres comme des lettres ; le numéro avait alors la forme d'un
  IBAN, mais la somme de contrôle ne concordait pas, et il restait en
  place. Si la somme de contrôle échoue, la lecture avec des chiffres
  est désormais essayée – si elle concorde, c'est l'IBAN. Les chiffres
  de contrôle vraiment faux restent faux.
- **Des fragments de phrase comme « folgenden Codes auf der » étaient
  considérés comme lieu.** Un nom ou lieu commençant par un mot en
  minuscule n'en est pas un – sauf pour les particules nobiliaires
  (« van Gogh », « de Vries »).
- **Dans l'éditeur, la dernière lettre restait visible à côté de la
  barre de caviardage** (« …6 », « …t », « …g »), et la barre avait la
  hauteur du cadre tracé au lieu de celle de la ligne. Cause : quand
  l'éditeur ne pouvait pas mesurer la page, il considérait chaque cadre
  comme « aucun mot touché » et l'appliquait exactement – sans la règle
  selon laquelle un demi-mot ne reste jamais. La même chose se
  produisait pour des commandes de texte isolées que l'éditeur ne
  pouvait pas localiser. Désormais, c'est toujours le cadre du mot qui
  compte à côté : ce que le cadre chevauche significativement tombe
  entièrement.
- **La dernière lettre d'un mot dépassait de la barre de
  caviardage.** La barre était dimensionnée d'après la largeur
  d'avancement issue des métriques de police ; si la police dessine un
  glyphe plus large, son reste se trouvait à côté de la barre. Le cadre
  d'un caractère intègre désormais aussi le glyphe dessiné.
- **Le message concernant la conversion d'une page en image promettait
  trop.** « L'affichage reste identique » n'est pas vrai après
  rastérisation : texte et graphiques deviennent alors des pixels, le
  fichier grossit. Le message le dit désormais – et indique aussi la
  deuxième raison pour laquelle la rastérisation a lieu (la
  reconstruction aurait endommagé la page).
- **Le texte après une valeur supprimée se décalait jusqu'à un point
  vers la gauche.** Lors de la refonte d'une ligne, le début était
  mesuré au bord du glyphe, la suite à l'origine de la plume – la
  largeur d'avance du premier caractère restait comme erreur
  (« C » 0,5 pt, « I » 1,0 pt). La refonte calcule désormais de bout en
  bout avec l'origine de la plume ; la suite se trouve au dixième de
  point près à sa place.
- **L'UID autrichien avec espaces (« ATU 187 35901 ») et un numéro de
  registre du commerce sans « FN » sous son libellé (« Firmenbuchnummer :
  30799v ») sont reconnus.** Les deux figuraient à la main sur un
  formulaire d'appel d'offres scanné et restaient lisibles bien que la
  reconnaissance de texte les ait correctement lus.
- **Les pages PDF en orientation paysage étaient converties en image
  sans raison après caviardage.** La vérification d'intégrité comparait
  original et résultat dans l'affichage tourné, mais calculait ses
  zones de caviardage non tournées – sur une page avec mention de
  rotation, son propre caviardage se trouvait donc décalé par rapport à
  sa zone et était considéré comme un dommage. De telles pages
  conservent désormais leur couche de texte et leurs graphiques
  vectoriels.
- **Même des pages droites étaient parfois converties en image sans
  nécessité**, quand le texte après un espace réservé se décalait d'un
  point – autorisé, mais la comparaison d'image était plus fine que sa
  propre tolérance. Elle compare désormais en demi-points et atteint
  ainsi précisément sa tolérance : jusqu'à deux points de décalage, rien
  ne se déclenche, au-delà, tout se déclenche.
- **Des indications dans des objets de formulaire intégrés
  restaient en place.** Certains modèles déposent l'en-tête ou le pied
  de lettre comme formulaire propre que la page ne fait qu'intégrer. Un
  résultat qui s'y trouvait était certes planifié et compté comme
  supprimé, mais jamais écrit – le texte restait présent, et seule la
  rastérisation de la page entière le rattrapait. Le formulaire
  lui-même est désormais réécrit ; un formulaire présent sur plusieurs
  pages, une seule fois.
- **Des pages PDF étaient rastérisées en image alors que rien n'était
  resté lisible.** Une offre de sept pages était touchée sur six pages ;
  elle passait de 73 ko à 3,3 Mo et perdait son texte au profit d'une
  image. La cause était des espaces qui figurent plusieurs fois de
  suite dans le document, mais ne sont signalés qu'une fois par le
  lecteur : le texte après une donnée supprimée se décalait de sa
  largeur vers la droite, la revérification trouvait le mot voisin dans
  le rectangle trouvé et déclenchait la rastérisation. Les restes de
  ligne conservés se trouvent désormais de nouveau exactement à leur
  place ; la même offre est nettoyée sans une seule page rastérisée
  (76 ko).
- **Des noms de clé et en-têtes de facture étaient considérés comme des
  personnes.** Dans un fichier d'accès, le nom de la variable
  d'environnement (« AWS_ACCESS_KEY_ID ») était remplacé, pas seulement
  sa valeur ; sur une facture anglaise, le titre « Bill to » tombait
  comme prénom. Un identifiant en majuscules avec traits de soulignement
  n'est jamais un nom, et un mot dans une ligne qui constitue dans son
  ensemble un libellé de champ non plus – le destinataire en dessous
  continue d'être trouvé.
- **La recherche dans la fenêtre de retouche bloquait sur les grandes
  pages PDF.** Chaque caractère dans le champ de recherche faisait
  rerastériser la page, alors que seul le surlignage changeait. L'image
  de page rendue reste désormais en place tant que page, zoom et vue
  restent les mêmes – aussi l'original dans la loupe de comparaison ;
  feuilleter, zoomer et un nouvel état de fichier continuent de
  redessiner comme avant.
- **Les numéros de position dans les offres étaient considérés comme
  adresse IP ou numéro de téléphone.** Une ligne d'article comme
  « 1.3.3.4 … 5-Port Gigabit Switch » faisait devenir le numéro de
  structure une adresse réseau, parce que « Port » comptait comme
  contexte technique – il ne compte désormais plus que comme donnée
  autonome (« Port 80 »), pas comme partie de mot. Et
  « 1.3.3.6 216879 » (numéro de position plus numéro d'article) n'est
  plus caviardé comme numéro de téléphone. Les vraies adresses IP et
  numéros de téléphone dans de telles listes restent détectés.
- **Des lignes d'article dans les offres étaient considérées comme code
  postal avec lieu.** « 35252 DIETZEL SALR » (numéro d'article avec
  fabricant) et « 1000 AWG » (quantité avec section de conducteur)
  étaient caviardés comme adresse dans des lignes de position numérotées,
  parce qu'un mot en majuscules après un nombre comptait comme nom de
  lieu en capitales. Dans les listes de position, ce n'est désormais
  plus le cas ; « 1080 WIEN » dans le bloc d'adresse et les lieux en
  minuscules restent reconnus partout.
- **La détection de noms supplémentaire caviardait dans les offres des
  lignes de rôle et en-têtes de colonne.** « Partiestundensatz Monteur +
  E-Helfer » était considéré 49 fois comme personne, l'en-tête de
  colonne « Pos. Bezeichnung Menge EH » 19 fois comme lieu – une
  commande de 19 pages en devenait illisible. De tels résultats dans des
  lignes de position tombent désormais s'ils portent eux-mêmes des
  caractères qu'aucun nom ne porte (plus, barre oblique, chiffre,
  sigle) – même quand la ligne se termine par un montant
  (« Alternativ Markt … - PV/LS AC-Versorgung 1 290,00 »). Les noms dans
  les répertoires et listes – la raison d'être de ce niveau – ne sont
  pas affectés.
- **« Der Kunde » transformait dans les conditions générales chaque
  « Kunde » en nom.** Si la détection de noms supplémentaire intégrait
  l'article dans le résultat, celui-ci comptait comme nom à deux
  parties et protégeait les 35 autres occurrences du même mot.
  L'article est désormais retiré, et « der Kunde » tombe comme le
  faisait déjà « des Kunden ».
- **Des libellés étaient considérés comme valeur.** « E-Mail » était
  caviardé sept fois comme adresse e-mail, « Telefonnummer » et
  « Faxnummer » comme numéro de téléphone. Une adresse sans @ et un
  numéro de téléphone sans chiffres ne comptent plus.
- **Les sigles de colonne d'une lettre (« L: 154,50 », « S: 0,00 »)
  étaient considérés comme nom** – 25 fois dans une offre photovoltaïque.
  Une lettre isolée n'est ni un nom ni un lieu.
- **Des pages PDF étaient bien trop souvent converties en image.** Deux
  causes, toutes deux trouvées sur de vraies offres : si un PDF pose
  chaque glyphe comme sa propre commande et qu'un glyphe espace sans
  caractère de texte se glisse en dessous, l'affectation se décalait
  d'un cran à partir de là – de la valeur supprimée restait la dernière
  lettre (« ŠkodaTopCar**d** »), et la revérification rastérisait la
  page à juste titre. Et un mot coupé en fin de ligne (« Datenschutz- »)
  était considéré comme décalé à cause de la marque de trait d'union de
  la bibliothèque de lecture. Les deux corrigés : une offre de véhicule
  est passée de 4 pages rastérisées à 0, une commande de 19 pages de 7
  à 0 – le texte reste du texte, le fichier reste petit.
- **Deux autres causes de rastérisation corrigées :** si un document
  apporte lui-même une police nommée « F1 », les espaces réservés
  au-dessus des images étaient posés dans cette police et étaient
  illisibles – la police de libellé propre reçoit désormais un nom
  libre. Et si la bibliothèque de lecture manque un espace au milieu
  d'une longue commande de texte, l'emplacement est désormais prouvé
  même pour les polices multi-octets (même code, même caractère) au
  lieu d'être deviné à la fin – auparavant, une lettre de la valeur
  supprimée restait en place et le reste du texte se décalait
  visiblement de côté. À cela s'ajoutent deux derniers cas : une
  commande composée de dizaines de glyphes espace faisait dériver
  l'affectation (le nom qui suivait restait en place), et un grand
  titre avec largeur d'avance ne trouvait pas son premier caractère (le
  nom de l'entreprise restait en place). **Sur neuf vraies offres, plus
  aucune page n'est désormais rastérisée** – auparavant, c'était 30 sur
  90.
- **Lors de la rastérisation, des images disparaissaient sous un bloc
  noir.** Quand une page doit être convertie en image, elle est rendue à
  partir de l'original – ce qui ignore tout nettoyage d'image. Jusqu'ici,
  *toute* zone d'image de la page tombait donc sous une barre, même les
  zones non touchées. Sur une offre, l'adresse et deux logos de
  certificat se trouvaient dans la même image d'en-tête ; la barre
  emportait les logos. L'image déjà nettoyée est désormais insérée :
  l'adresse y est caviardée, tout le reste reste visible. Une image
  supprimée laisse du papier blanc au lieu d'un bloc noir.

- **Les scans nettoyés devenaient plusieurs fois plus gros que
  l'original.** Chaque image dans laquelle quelque chose était caviardé
  revenait dans le fichier comme image brute non compressée – pour un
  scan de 24 pages, cela le faisait passer de 11,8 à 52,9 Mo. Les
  images conservent désormais le type sous lequel elles se présentaient :
  une photo reste une photo, un scan de fax reste noir et blanc, une
  image sans couleur n'est pas déposée comme image couleur. Le même
  fichier fait désormais 15,6 Mo, sans différence visible.

- **Les fichiers PDF scannés issus d'appareils de bureau revenaient sous
  forme de motif rayé.** De tels scans posent le texte comme une couche
  noir et blanc nette sur une image couleur grossière – Canon, Xerox et
  Kofax construisent ainsi leurs fichiers. Lors du caviardage dans
  l'image, cette couche était mal réécrite ; le résultat était
  illisible. Pour une offre de six pages, cela touchait neuf images sur
  seize. Elle est désormais traitée correctement, dans sa propre
  couleur, et les zones caviardées y sont vraiment supprimées.

- **« Supprimer toutes les images » retirait son texte à une page
  scannée.** La couche de texte d'un tel scan est techniquement une
  image – elle était supprimée ou floutée avec le reste, et il ne
  restait qu'une feuille vide. Elle reste désormais en place ; logos,
  tampons et signatures continuent de disparaître.

- **La vérification des pages PDF endommagées ne rastérise plus à
  cause d'un décalage minime.** Un morceau de texte réancré lors du
  nettoyage peut glisser jusqu'à deux points ; la comparaison d'image le
  comptait malgré tout comme un dommage et reconstruisait la page en
  image – les graphiques vectoriels comme les lignes de tableau se
  perdaient alors, et une barre se trouvait sur les emplacements trouvés
  au lieu d'un espace réservé. La comparaison autorise désormais le
  même petit décalage que la vérification des mots ; les vrais dommages
  continuent d'être détectés.

- **La récupération de nombreuses valeurs à la suite n'échouait plus sous
  Windows à cause d'un « Accès refusé ».** Qui annulait de nombreuses
  lignes de panneau coup sur coup dans un fichier Office pouvait
  échouer à cause d'un verrou de fichier éphémère de l'antivirus ;
  l'échange attend désormais brièvement de tels verrous.

- **Le chemin Windows de transmission des commandes terminait le
  vérificateur au lieu de vérifier.** Le contrôle de vie de l'instance
  à l'écoute envoyait par erreur sous Windows un vrai Ctrl+C à son
  propre groupe de console ; il interroge désormais le système sans
  signal.

- **Les libellés de champ à plusieurs mots n'agissaient pas, mais leurs
  fragments oui.** « Date of birth », « Bank account », « Cuenta
  bancaria » et « Numero de cliente » figuraient dans la liste des
  libellés, mais y étaient décomposés en mots isolés et ne
  déclenchaient donc jamais ; il restait des fragments de mot comme
  « de » et « of », qui comptaient depuis comme libellé – or « de » est
  un composant de nom (« Anna de Vries »). Les deux sont corrigés : les
  expressions agissent désormais dans leur ensemble, les fragments ont
  disparu.

- **Les formules de politesse allemandes avec « ß » étaient traitées
  comme nom de personne malgré leur présence dans la liste.** Sous
  « Herzliche Grüße » ou « Mit freundlichen Grüßen » se trouvait dans le
  résultat un espace réservé, bien que les deux expressions figurent
  depuis toujours dans la liste d'exclusion. La cause était une
  écriture qui n'arrivait jamais lors de la comparaison ; huit entrées
  sur cinq listes étaient concernées. Elles agissent désormais toutes.

- **« John Staff » restait non remplacé.** Un nom de famille qui est en
  même temps un titre de colonne anglais était rejeté en même temps par
  le filtre de libellés. Le titre reste toujours intact, le nom en
  dessous est de nouveau remplacé.

- **Les valeurs issues de champs de formulaire libellés restent
  protégées au niveau IA.** L'arbitre local du niveau IA recevait
  jusqu'ici aussi pour évaluation des résultats dont le sens était déjà
  attesté par le libellé du champ (« Geburtsdatum : » au-dessus de la
  valeur) – et pouvait les rejeter. De telles valeurs attestées
  structurellement ne lui sont plus soumises. Le fichier d'affectation
  indique désormais en plus, pour chaque remplacement, la voie de
  détection (« attesté »).

- **Une page PDF dont le texte conservé a été endommagé lors du
  nettoyage est désormais détectée et reconstruite comme image de
  l'original.** Avec certaines polices de générateurs, des passages de
  texte conservés pouvaient apparaître comme des blocs noirs ou des mots
  collés après le nettoyage, bien que toutes les données à supprimer
  l'aient été correctement. Maskuro compare désormais le résultat mot
  par mot et pixel par pixel avec l'original ; une page endommagée est
  remplacée par son image propre – avec des barres de caviardage sur
  les emplacements trouvés, des zones d'image caviardées et du texte
  consultable par recherche. La page reste lisible, la suppression
  fiable.

### Modifié

- **Dans les interfaces traduites, chaque terme technique s'appelle
  désormais partout de la même façon.** Pour un seul et même mot
  allemand, deux ou trois traductions figuraient côte à côte selon la
  fenêtre : le journal de vérification s'appelait en norvégien tantôt
  « Revisjonslogg », tantôt « Kontrollogg », l'offre gratuite tantôt
  « Gratisnivå », tantôt « Gratisversjon » – et de même dans une
  douzaine d'autres langues. Qui cherchait un paramètre le trouvait
  dans la fenêtre suivante sous un autre nom. L'unification s'est faite
  sur le mot que l'interface utilise de toute façon le plus souvent.

  Cela a mis en lumière des endroits où un mot désignait deux choses
  **différentes** : le français, le grec et le coréen utilisaient la
  même expression pour « caviarder » et « masquer » – justement là où le
  programme explique la différence (« Caviarder supprime sans
  remplacement, masquer conserve la forme »). Les deux sont désormais
  distingués. Pour le suédois, cette décision reste en attente : là,
  caviarder se dit « maskera » – le même mot que masquer.

- **La question sur le type d'usage au premier démarrage a
  disparu.** Peu après le démarrage apparaissait une fenêtre
  (« Usage privé ou professionnel ? »), et dans les paramètres figurait
  une ligne à ce sujet. Les deux n'existent plus – sans remplacement.
  Une indication à laquelle rien n'est rattaché donne une fausse
  information sur qui a besoin de quelle licence, et qui est honnête n'en
  a pas besoin ; elle coûtait à chacun un clic à un moment où personne
  ne pense aux types de licence. Quelle licence est la bonne figure là
  où la décision se prend : sur la page des prix, à la caisse et dans
  l'aide. Les entreprises qui déploient Maskuro de façon centralisée
  continuent d'imposer le type d'usage via le fichier de consignes.

- **Les indications sur le type de licence nomment désormais le cas
  concerné.** La licence privée s'applique exclusivement à l'usage
  privé ; tout travail professionnel ou commercial nécessite la licence
  d'entreprise – même en tant qu'entrepreneur individuel sans employés.
  C'était ainsi dans les conditions de licence, mais ni dans le
  programme ni dans l'aide : il n'y était toujours question que du
  domaine d'entreprise, qui ne couvre justement pas ce cas : l'ordinateur
  d'un indépendant n'appartient à aucun domaine. L'indication lors de la
  lecture d'une licence privée le dit désormais, de même que le
  chapitre licence du manuel et la foire aux questions, qui a reçu une
  entrée propre à cet effet. Rien n'est bloqué pour autant.

- **Les voies pas encore livrées sont désormais regroupées.** Les
  paramètres ont reçu une page « Développeur » ; s'y trouvent la
  détection maximale (IA) avec sa contre-vérification, le catalogue de
  listes de mots et la surveillance de dossier. Les trois sont
  construites, mais pas éprouvées sur le terrain – elles ne sont donc
  visibles qu'avec une licence développeur, et ce partout en même
  temps : la page, les entrées de menu et l'effet en cours d'exécution
  dépendent de la même décision. Sans cette licence, un niveau IA
  précédemment activé reste sans effet ; son paramètre n'est pas
  supprimé et redevient effectif dès que la voie est livrée.

### Amélioré

- **« Ce qui est détecté » affiche trois autres listes issues de la
  détection de noms.** Les formules d'appel après lesquelles le mot
  suivant est lu comme un nom ; les titres et rôles qui ensuite ne sont
  **pas encore** le nom (« Herr Bürgermeister Huber ») ; et les quatre-vingts
  libellés multilingues auxquels sont reconnus les numéros de dossier,
  d'affaire et de cas. Les trois ont toujours agi, mais n'étaient pas
  visibles dans l'aperçu.

- **« Ce qui est détecté » affiche deux listes de mots manquantes
  jusqu'ici.** Les formules d'appel et titres qui font d'un mot
  précédent un nom (« Herr », « Frau », « Dr. »), et les sigles des
  organismes de normalisation auxquels Maskuro distingue une référence
  normative comme « ÖNORM B 2110 » d'une personne. Les deux influencent
  la détection depuis toujours, mais ne figuraient pas dans l'aperçu.

- **Les listes de position, tables des matières, énumérations
  d'équipement et références normatives restent lisibles.** La
  détection voit désormais la forme de la ligne : un nom deviné dans une
  ligne de structure (« 1.3.1 Energieerdkabel 1kV »), une ligne de table
  des matières avec points de conduite, une énumération
  (« - kabelloses Laden mit Magnetring »), au-dessus d'une ligne de
  quantité/prix, dans un en-tête de colonne ou après « mittels » est un
  terme technique et n'est plus remplacé. Les vrais noms restent
  protégés – par la formule d'appel, le libellé de champ et l'attestation
  ailleurs dans le document ; sur le corpus de mesure, aucune donnée n'a
  perdu sa protection. Dans le corpus commercial, les faux positifs
  passent ainsi de 25 à 6.

- **Titres, libellés de formulaire et formules de politesse sont moins
  souvent pris pour des noms – en allemand et en anglais.** Les listes
  de mots par lesquelles Maskuro distingue les mots communs des noms de
  personne ont nettement grandi : libellés de factures, formulaires et
  courrier administratif (« Aktenzeichen », « Verwendungszweck »,
  « Kostenstelle », « Sort code », « Subtotal »), titres de section de
  candidatures et rapports (« WERDEGANG », « QUALIFIKATIONEN »,
  « SUMMARY », « REFERENCES »), types de document allemands et anglais
  (« Auftragsbestätigung », « Niederschrift », « Timesheet »,
  « Agreement ») ainsi que formes impératives de guides
  (« Sende… », « Select… »). Le côté anglais était jusqu'ici
  particulièrement peu fourni.

- **Les champs libellés révèlent désormais aussi ce qu'ils contiennent
  quand le libellé est composé.** « Lieferanschrift »,
  « Rechnungsadresse », « Sachbearbeiterin », « Kontoinhaber »,
  « Contact person » et « Billing address » associent désormais la
  valeur à côté ou en dessous au même type que le simple « Anschrift »
  ou « Name » – dans un formulaire rempli avec des cases, c'est la
  différence entre trouvé et manqué.

- **Dans la fenêtre de retouche, la molette de la souris continue de
  faire défiler au bord de page.** Qui continue de faire défiler à la
  fin d'une page atterrit en haut de la suivante ; qui remonte au début
  atterrit en bas de la précédente – un document peut ainsi être
  parcouru du début à la fin sans toucher les boutons de page. Le
  clavier (Page↑/Page↓) le savait déjà faire ; une courte pause entre
  deux changements de page empêche l'inertie d'un trackpad d'emporter la
  moitié du document.

- **Les vignettes de page dans la fenêtre de retouche sont désormais
  centrées dans le volet.** Jusqu'ici, elles collaient au bord gauche,
  et en élargissant, seule la marge vide à droite grandissait.

- **La barre d'outils de la fenêtre de retouche affiche ses groupes.**
  Les traits de séparation ont désormais de l'espace et de la couleur,
  « Rechercher » et « Transférer à toutes les pages » figurent comme
  groupes propres à côté des outils, et « Transférer » n'apparaît plus
  que pour les types de document où cela peut avoir un effet. Chaque
  entrée de la barre et des menus porte désormais une image : « Lignes
  de texte » et la loupe de comparaison ont reçu leurs propres icônes
  (la loupe partageait jusqu'ici la sienne avec « Avant/Après »),
  ainsi que le zoom, la page entière, la largeur de page, la rotation,
  le défilement et les raccourcis clavier. « Ouvrir avec le programme
  système » figure désormais aussi dans la barre à côté d'Imprimer – le
  chemin du résultat terminé vers le programme habituel est un clic, pas
  un passage par le menu.

- **Le nettoyage du presse-papiers rappelle de nouveau qu'une
  vérification est nécessaire.** Dans les paramètres, l'indication
  figure désormais en permanence à côté de l'interrupteur : Maskuro peut
  manquer des données personnelles ou mal traiter des indications, le
  texte collé doit être vérifié avant transmission. À l'activation, le
  message le rappelle en plus, et cela est noté dans la zone de sortie –
  même quand aucune icône ne tourne dans la zone d'information. À
  chaque copie individuelle, il n'apparaît volontairement pas : une
  indication qui reviendrait cinquante fois par jour ne serait plus lue
  après la troisième fois.

## 0.10.36-beta.1 – 20 août 2026

### Amélioré

- **Les documents commerciaux techniques ne sont plus caviardés à
  outrance.** Quatre freins de détection, tirés de onze offres et
  commandes réelles : les numéros de structure (« 1.3.1.1 ») ne comptent
  plus comme adresses IP, les références normatives (« ÖNORM EN 62446 »)
  et codes d'identification plus comme code postal ou numéro de
  téléphone, et les mots de rôle après un article (« der Kunde »,
  « des Auftraggebers ») plus comme noms – dans les conditions générales
  d'une offre réelle, les 46 mots de rôle sont ainsi de nouveau lisibles
  au lieu d'être caviardés. Les adresses avec code pays (« A 3390
  Melk », « D-94032 Passau ») sont désormais entièrement supprimées, au
  lieu de laisser le code postal orphelin.

- **Les listes de mots sont désormais entièrement consultables.** Sous
  « Aide → Listes de mots … », les listes de détection et de
  contre-vérification utilisées localement peuvent être parcourues avec
  langue, objectif, source et contenu. Cela inclut aussi les listes
  Wordfreq, médicales, personnelles et gérées de façon centralisée ainsi
  que les réservoirs de valeurs de remplacement fictives. Le manuel
  décrit le catalogue dans une section propre.

- **Les lignes de fichier terminées affichent la langue de détection
  utilisée.** Derrière « terminé » figure désormais par exemple
  « Allemand » ou « Anglais », afin qu'un choix automatique de langue
  inadapté se remarque immédiatement. Si une autre langue installée a dû
  prendre le relais, une flèche affiche les deux langues.

- **La nouvelle loupe de comparaison affiche immédiatement l'emplacement
  correspondant dans l'original pendant la lecture.** Son extrait
  d'original agrandi suit le curseur de la souris au-dessus du résultat
  qui reste modifiable ; pour du texte, elle suit le paragraphe. La
  loupe peut être utilisée au bord de la fenêtre ou détachée comme
  fenêtre propre, maximisable. Son zoom est réglable directement entre
  50 et 300 pour cent et est mémorisé au même titre que son activation.
  « Réinitialiser » ramène aussi une loupe maximisée ou mal ancrée à une
  taille utilisable à gauche. Les valeurs originales remplacées sont
  surlignées en jaune dans la loupe, afin que les mots concernés se
  remarquent immédiatement à la lecture. Une fois activée, elle
  s'ouvre à nouveau pour les futurs documents adaptés – même après un
  redémarrage du programme. L'ancien commutateur avant/après est
  conservé dans le menu Affichage. Le manuel la décrit dans une section
  propre.

- **Les attestations open source et de modèles sont désormais précises
  par version.** La construction du paquet génère une liste de
  composants lisible par machine avec les hachages des textes de
  licence joints. Sources MPL, provenance des modèles, révisions fixes,
  modifications et SHA-256 sont attestés séparément ; les modèles
  rechargés reçoivent leur preuve de provenance directement dans le
  dossier du modèle. Les listes de référence mobiles de Tesseract et
  spaCy ont été fixées définitivement. Les artefacts de vente restent
  bloqués tant que toutes les sources et annexes de modèles ne sont pas
  publiées et vérifiées.

- **Le stock local de données wordfreq est entièrement justifié en
  matière de licence.** La construction du paquet vérifie la version
  3.1.1, 39 petites listes inchangées y compris CJK et la table de
  caractères chinois, par rapport au nombre, à la taille et à la somme
  de contrôle du manifeste. La mention de code Apache-2.0, la licence
  CC-BY-SA-4.0 complète, l'attribution, les sources de données et les
  grandes listes omises, Jieba et les listes non prises en charge sont
  documentées dans le paquet.

- **Les mots de phrase fréquents sont moins souvent caviardés par
  erreur.** Un dictionnaire de fréquence local sert de
  contre-vérification supplémentaire quand la détection de noms prend un
  verbe, un pronom, un article ou une préposition pour une personne. Le
  dictionnaire ne décide jamais seul : les noms communs, les noms à
  plusieurs parties ainsi que les noms dans des champs, des listes et
  après des formules d'appel restent protégés. Le chinois, le japonais
  et le coréen utilisent exclusivement les limites de jetons exactes de
  leurs modèles linguistiques déjà présents ; pour les langues absentes,
  aucune langue de dictionnaire prétendument similaire n'est utilisée.
  Aucun texte de document n'est transmis sur internet pour cela.

- **Les termes techniques de produit et d'équipement sont moins souvent
  pris pour des noms ou des lieux.** La contre-vérification locale
  combine désormais fréquence, nature du mot, formation technique de
  mots et champs thématiques. Ainsi, « Travel-Assistent »,
  « Family-Bonus », « WLTP-Wert », « Easy-Start » et des termes composés
  de numéro, de support ou de frein restent par exemple dans le
  document. Les composants anglais sont aussi vérifiés localement dans
  du texte technique allemand ; les vrais noms propres, formules d'appel
  ainsi que les champs de personne et de lieu gardent la priorité. En
  outre, une « garantie constructeur de 2 ans » ne compte plus comme un
  âge.

- **Les droits de licence Qt/PySide sont désormais entièrement
  traçables.** Le paquet du programme contient en plus le texte complet
  de la GPL-3.0, les versions exactes de Qt, une offre de code source et
  un guide allemand/anglais pour l'échange des bibliothèques
  dynamiques, y compris une nouvelle signature locale sous macOS. Une
  construction de vente est bloquée tant que les archives source exactes
  de la version livrée ne sont pas disponibles sur la propre page de
  code source.

- **La licence et l'état de mise à jour indiquent désormais clairement,
  pour chaque niveau, ce qui s'applique.** Dans la fenêtre de licence et
  les paramètres de mise à jour figure si des mises à jour sont
  incluses, jusqu'à quelle date elles vont et si la version en cours
  reste utilisable durablement. Les licences privées n'installent plus
  après la date limite de version parue plus tard ; même un programme
  d'installation fraîchement téléchargé reconnaît, grâce à sa date de
  parution intégrée de façon fixe, si la clé saisie le couvre. La
  dernière version privée couverte reste utilisable durablement. Si en
  revanche un abonnement d'entreprise se termine, l'utilisation et les
  mises à jour se terminent ; la période d'essai et l'offre gratuite ne
  s'ouvrent pas comme détour.

- **Les licences privées permanentes retrouvent désormais aussi le bon
  état du programme après une nouvelle installation.** Un catalogue de
  versions signé répertorie toutes les versions stables et leurs
  paquets. Si le dernier programme d'installation couvert par l'achat
  n'est plus disponible, la prochaine version stable disponible
  immédiatement supérieure peut être utilisée automatiquement à sa
  place – jamais une bêta ou une nightly. En cas d'installation trop
  récente, le client peut installer la version autorisée ou passer à la
  page d'achat pour une nouvelle période de mise à jour ; un retour en
  arrière ne se produit jamais silencieusement. Cela vaut aussi pour les
  installations MSI gérées.

- **Le floutage automatique des visages est désormais décrit sans
  ambiguïté.** L'aide du programme et le texte de confidentialité
  nomment la fonction « Détecter et rendre méconnaissables les zones de
  visage » et la distinguent de l'identification, de la reconnaissance,
  de la comparaison faciale, des modèles biométriques et des bases de
  données de personnes ou de visages. Ils indiquent en outre clairement
  que la détection entièrement locale peut manquer ou marquer par
  erreur des zones, et que le résultat doit donc être vérifié
  visuellement. Même pour un fichier image nettoyé individuellement, le
  rapport de résultat indique désormais les zones de visage détectées et
  pixelisées ; une reconnaissance de texte manquante n'est plus
  faussement décrite comme un fichier entièrement inchangé.

## 0.10.36-alpha.20260820 – 20 août 2026

### Corrigé

- **Les données anonymisées peuvent désormais être récupérées entièrement,
  indépendamment de l'ordre.** L'ancienne récupération cherchait la valeur
  via des ancres de texte visibles. Dans les tableaux denses, entre des
  espaces réservés directement voisins et dans les emplacements Office/mail
  invisibles, ces ancres manquaient ; parfois un terme ne devenait
  récupérable qu'après qu'un autre texte en clair ait créé par hasard une
  nouvelle ancre. Désormais, le résultat et l'original sont comparés pour
  chaque support de format réel avec l'affectation complète, et seuls les
  emplacements attestés de la valeur choisie sont écrits.

- **Les noms, adresses e-mail, numéros et termes de vérification propres
  restent utilisables de façon univoque même en cas de détection
  chevauchante.** Si la même valeur en clair est associée à deux types,
  c'est l'espace réservé réellement présent à l'endroit trouvé, combiné à
  la ligne de la barre latérale cliquée, qui décide. Une paire
  valeur/espace réservé non attestée reste bloquée en toute sécurité.

- **Les cas particuliers de mail ne laissent plus d'espaces réservés
  cachés.** Cela vaut pour les objets encodés en MIME, les pièces jointes
  texte et les noms séparés par du balisage HTML dans les fichiers EML et
  MSG. Le HTML UTF-8 sans indication de jeu de caractères propre n'est en
  outre plus recodé en mojibake à chaque étape d'édition dans les fichiers
  Outlook ; les résultats plus anciens déjà écrits ainsi restent
  récupérables.

### Amélioré

- **Une nouvelle matrice de validation traite chaque ligne anonyme de la
  barre latérale individuellement et délibérément à rebours.** Elle vérifie
  les 14 formats texte, Office, web et mail ainsi que le PDF, puis
  également les formules, attributs, relations, commentaires, en-têtes de
  mail, pièces jointes et emplacements internes annexes. L'exécution
  complète sous macOS comprend désormais 149/149 scripts de vérification
  au vert.

## 0.10.35-alpha.20260820 – 20 août 2026

### Amélioré

- **Les mesures linguistiques comparent désormais vraiment du semblable
  avec du semblable.** Le corpus de mesure régulier contient les mêmes 14
  cas de documents avec les mêmes sept tâches de texte et quatre tâches
  d'image en allemand et en anglais. Une exécution complète répète
  exactement cette matrice pour les douze langues de corpus existantes.
  Les formulaires, tableaux, discussions et autres échantillons de
  structure pas encore entièrement traduits sont conservés, mais indiqués
  séparément et ne sont plus mélangés dans les quotas de langue.

- **L'exécution complète écrit un rapport de mesure propre pour chaque
  langue.** Sans sélecteur de langue, l'allemand et l'anglais sont vérifiés
  délibérément ; `--alle-sprachen` demande le corpus complet des douze
  langues et s'interrompt avant le premier document si une langue ou un
  cas manque. Les résultats de même nom se trouvent dans des dossiers de
  langue séparés. Le rapport global indique, en plus du taux de détection
  pondéré, la moyenne non pondérée des taux par langue.

- **La comparaison linguistique ouverte montre désormais aussi sa limite
  réelle.** Dans l'exécution régulière avec reconnaissance de texte,
  l'allemand et l'anglais suppriment 218/218 données connues sans faux
  positif. Le test complet avec reconnaissance de texte et niveau élevé
  supprime 1 255/1 308 données pour 17 faux positifs ; onze langues
  atteignent 100 pour cent, l'hindi 51 pour cent. Les taux complets
  antérieurs reposaient sur des ensembles de documents et de valeurs de
  référence inégaux et ne sont pas comparables à la nouvelle matrice.

## 0.10.34-alpha.20260819 – 19 août 2026

### Corrigé

- **Les noms apparaissant plusieurs fois restent accessibles dans la barre
  latérale après une seule récupération.** Jusqu'ici, toute la ligne du nom
  disparaissait déjà après la première position `[NAME]` récupérée. D'autres
  positions du même nom restaient alors comme espace réservé et étaient
  parfois même bloquées, jusqu'à ce que d'autres noms aient été récupérés.
  Désormais, la ligne ne disparaît qu'après la dernière position ; un texte
  en clair déjà récupéré n'est malgré tout pas réanonymisé automatiquement.
  Cela vaut aussi pour une récupération groupée partiellement réussie et
  pour l'outil de cadre dans les PDF.

- **« Annuler le remplacement » fonctionne aussi depuis l'aperçu des pages
  Office.** La page visible n'y est qu'un aperçu PDF éphémère ; c'est
  désormais correctement le document Word, tableur ou présentation
  sous-jacent qui est modifié, puis l'aperçu est actualisé.

- **La récupération ramène désormais aussi entièrement les équivalents
  cachés d'une valeur.** Dans les fichiers Word, OpenDocument, Excel et
  PowerPoint, les mêmes données peuvent en outre se trouver dans des
  formules, commentaires, diagrammes, valeurs de champ, textes alternatifs
  et cibles de renvoi ; HTML, EML et MSG les portent en outre dans des
  attributs, du JSON, des en-têtes de message et des pièces jointes.
  Jusqu'ici, une partie restait comme espace réservé selon le format.
  Désormais, chaque donnée proposée dans la zone de résultats peut être
  récupérée indépendamment et dans n'importe quel ordre. Les métadonnées,
  historiques de modifications et en-têtes de transport volontairement
  supprimés restent supprimés pour des raisons de sécurité.

- **Lors de la récupération depuis des images, il ne reste plus de ligne de
  bordure noire.** Les bords droit et inférieur d'un cadre étaient tracés,
  lors de la copie depuis l'original, un pixel trop court chacun. Les
  coordonnées correspondent désormais au caviardage.

### Amélioré

- **La vérification de validation fait désormais passer chacune des 22
  extensions de fichier prises en charge par un cycle complet.** Les
  fichiers riches en contenu sont nettoyés, toutes les valeurs proposées
  restaurées, puis vérifiées en profondeur. S'y ajoutent une utilisation
  réelle de la barre latérale, des comparaisons d'image au pixel près et un
  rendu LibreOffice visible des sept formats bureautiques. Les petits tests
  de régression subsistent là où ils couvrent un cas d'erreur ou de
  sécurité propre ; une vérification HTML manifestement redondante et le
  test du mode noir et blanc supprimé ont été retirés.

- **Le corpus de mesure complet de cette version est disponible pour un
  nouveau mesurage.** Le paquet contient 294 documents synthétiques en
  douze formats et douze langues, 2 564 données connues, quatre listes de
  référence lisibles par machine et un guide. Le téléchargement sur la
  page qualité utilise un nom de fichier dépendant du contenu, afin que les
  navigateurs ne livrent pas par erreur une ancienne version depuis le
  cache.

## 0.10.33-alpha.20260819 – 19 août 2026

### Nouveau

- **Dans les fichiers image aussi, des zones isolées peuvent désormais être
  récupérées depuis l'original.** L'outil de cadre « Récupérer l'original »
  recopie les pixels à la même position depuis le fichier source intact. Le
  chemin reste bloqué si la source manque ou a d'autres dimensions d'image ;
  ainsi aucun contenu ne peut être inséré depuis un emplacement décalé.

### Amélioré

- **Les barres de caviardage manuelles s'accrochent désormais par défaut
  aux lignes de texte.** Un tracé sur plusieurs lignes produit une barre de
  hauteur régulière par ligne et laisse libre l'espace blanc entre elles.
  Pour les signatures, graphiques et autres cas particuliers, « Cadre libre »
  revient à une hauteur choisie librement.

- **L'éditeur explique le prochain geste directement au-dessus du
  document.** L'indication change selon le type de document et l'outil, et
  précise si un clic sur un mot, une sélection de texte ou un cadre est
  attendu. En outre, l'outil, le curseur de la souris et l'aperçu en direct
  montrent déjà, avant le relâchement, ce qui va se produire.

### Supprimé

- **La sortie noir et blanc, source d'erreurs, a été supprimée.** Dans
  certains PDF, des champs de texte invisibles restaient décalés par
  rapport à la page rastérisée ; la réduction apparente de la taille du
  fichier ne valait pas ce risque de sécurité et d'affichage. Le nettoyage
  PDF normal et la rastérisation ciblée des pages problématiques sont
  conservés.

## 0.10.32-alpha.20260819 – 19 août 2026

### Nouveau

- **La surveillance de dossier tourne désormais vraiment en arrière-plan.**
  Entrée, sortie et règles se trouvent sur une page propre sous
  « Paramètres ». Elle se lance et s'arrête via l'icône Maskuro dans la
  barre des tâches ou de menu ; l'entrée n'apparaît qu'avec la licence
  débloquée pour cela. La fenêtre des paramètres peut ensuite être fermée
  et la fenêtre principale réduite dans l'icône sans arrêter la
  surveillance.

- **L'éditeur de retouche dispose désormais d'un interrupteur permanent de
  mode apprentissage.** Il se trouve dans la zone de résultats et dans le
  menu « Outils ». Une fois désactivé, ni la récupération ni les
  corrections manuelles ne font apparaître de questions sur la création de
  règles propres. Maskuro mémorise le choix pour tous les documents ouverts
  à l'avenir ; la récupération elle-même fonctionne sans changement.

### Corrigé

- **Le grand modèle complémentaire peut de nouveau être chargé.** Le stockage
  public rejetait l'identifiant standard générique de Python avec un 403.
  Les téléchargements de modèle utilisent désormais le même chemin réseau
  Maskuro déclaré que les autres services propres ; le fichier de près de
  596 Mo et sa somme de contrôle restent inchangés.

- **Une loupe de comparaison maximisée ne reste plus accrochée comme une
  barre étroite en haut de l'écran lors de l'ancrage.** Avant l'ancrage, son
  état de fenêtre libre est normalisé. Un état maximisé enregistré est
  également ramené à une taille modifiable à la prochaine ouverture.

- **Une récupération groupée ramène désormais vraiment toutes les valeurs
  sélectionnées dans les tableaux et autres formats texte.** Pour les
  espaces réservés anonymisés comme `[EMAIL]`, Maskuro écrivait jusqu'ici
  les valeurs les unes après les autres. Dès que la première était
  remplacée, les numéros de tous les emplacements restants avançaient, mais
  le plan déjà calculé pointait encore vers les anciens numéros. Seule une
  partie de la sélection revenait de ce fait. Désormais, toutes les valeurs
  choisies du même espace réservé sont écrites ensemble et avec des numéros
  d'emplacement stables. Si un emplacement ne devient univoque que grâce à
  une autre valeur récupérée, Maskuro le revérifie dans la même opération –
  l'ordre de la sélection n'a donc plus d'importance.

- **« Annuler le remplacement » ne laisse plus de côté de valeurs
  sélectionnées dans les PDF.** Si un espace réservé se trouvait très près
  d'un autre mot ou qu'une virgule collait directement à la valeur dans
  l'original, la vérification de position pouvait par erreur attribuer le
  mot voisin ou le signe de ponctuation à la valeur. Lors d'une récupération
  groupée, certains espaces réservés et lignes de résultat restaient alors
  en place. La vérification s'aligne désormais sur le véritable début de
  mot et tient aussi compte d'une rotation de page différente entre
  l'original et le résultat.

- **Le texte PDF récupéré conserve désormais sa taille d'origine.** Jusqu'ici,
  l'espace réservé déjà réduit servait de référence ; de plus, le plafond de
  11 points prévu pour les espaces réservés s'appliquait aussi au texte
  original. Désormais, le cadre et la taille de police d'origine sont
  repris du fichier source – aussi bien pour l'outil de cadre que pour la
  récupération depuis le panneau de résultats.

### Amélioré

- **L'avertissement de vérification nomme désormais plus clairement le
  risque résiduel.** Il indique explicitement que Maskuro peut manquer des
  données ou mal traiter certaines indications, et exige avant toute
  publication ou transmission une vérification complète et, si nécessaire,
  une correction manuelle. Cela vaut aussi pour le texte issu du
  presse-papiers et a été intégralement répercuté dans les 17 traductions.

- **Le journal de vérification démarre désormais aussi sans nom d'utilisateur
  au sein de ses lignes.** Le journal lui-même reste désactivé tant qu'une
  entreprise ne l'active pas délibérément. Ensuite, sans consigne
  d'entreprise supplémentaire, aucun nom d'utilisateur ne figure ni dans une
  ligne ni dans le nom d'un fichier mensuel central ; un pseudonyme non
  devinable, dérivé uniquement du secret de profil local aléatoire, sert
  à la séparation sécurisée. La boîte de dialogue de licence ne recommande
  plus l'activation, présuppose « Sans journal » et signale au préalable le
  comité d'entreprise, la représentation du personnel et la protection des
  données.

- **Remplacer nomme désormais ce qu'il remplace.** Un nom marqué devient
  `[NAME_3]`, un lieu `[ORT_1]`, un numéro de téléphone `[TELEFON_2]` –
  au lieu de tout transformer en `[BEGRIFF_n]` comme jusqu'ici. Le type
  est détecté au clic ; s'il n'est pas univoque – un mot ordinaire, ou un
  nom *et* un lieu dans une même sélection –, on en reste au terme
  générique. Un espace réservé qui prétend un type erroné serait pire
  qu'un espace réservé qui n'en indique aucun.

- **Les outils de la fenêtre de retouche ont désormais chacun une touche.**
  **S** caviarde, **E** remplace, **Z** récupère l'original, **V** pixelise.
  Dans la vue texte, ils agissent immédiatement sur la sélection ; sur
  l'aperçu des pages, ils sélectionnent l'outil. **Les lettres suivent la
  langue** dans laquelle vous utilisez le programme – anglais B/R/O/P,
  italien O/S/R/P –, car un moyen mnémotechnique n'aide que dans sa propre
  langue. La touche figure sur le bouton.
  Qui est en train de taper dans la barre de recherche continue d'écrire
  des lettres ; elles n'y ont aucun effet.

- **Le programme signale une fois par jour dans quel état il fonctionne –
  sans aucun identifiant.** Cela nous permet de compter combien
  d'installations sont utilisées et comment cela se répartit entre période
  d'essai, offre gratuite et licence. Sont transmis : état, système
  d'exploitation, version, canal, pays, langue, environnement et niveau de
  détection – **rien sur vos documents et rien qui permette de reconnaître
  votre ordinateur**. Deux signalements de votre part nous apparaissent
  comme des signalements de deux personnes différentes ; aucun chemin
  individuel ne peut en être suivi. Ce qui est exactement envoyé et comment
  le désactiver figure dans le texte de confidentialité au point 5.

- **Les pages numérisées de travers s'affichent désormais d'elles-mêmes dans
  le bon sens.** Une feuille scannée de travers sans que cela soit indiqué
  est détectée par la retouche via le flux du texte, qui redresse la vue.
  Là où ce n'est pas possible – pour un scan pur sans texte lisible – deux
  nouvelles entrées dans le menu « Affichage » permettent la rotation
  manuelle (Ctrl+Maj+L et Ctrl+Maj+R). Seul l'affichage est tourné : le
  fichier lui-même n'est pas modifié, et le caviardage continue de
  toucher exactement l'endroit sur lequel on clique.

- **La sortie locale répertorie désormais ses licences de manière complète et
  visible.** La construction détermine les paquets Python réellement
  intégrés, dépose leurs textes de licence avec un aperçu des versions sous
  `lizenzen` et s'interrompt en cas de lacune. Qt, Tesseract et le modèle
  de reconnaissance faciale disposent aussi de leurs textes nécessaires ;
  les conditions de Maskuro lui-même sont jointes sous forme de contrat de
  licence.

- **On voit désormais dans quel espace réservé se trouve le curseur.** Qui
  clique dans un espace réservé le voit s'illuminer entièrement – crochets
  et numéro compris. Le bouton « Récupérer la sélection » réagissait déjà
  auparavant à un simple clic ; seulement on ne voyait pas quelle marque il
  visait. L'illumination reste visible même lorsque la souris se déplace
  vers le bouton.

- **Le curseur de la souris indique désormais quel outil est sélectionné.**
  Quatre outils partagent la même zone et le même geste ; jusqu'ici, tous
  se ressemblaient. Réticule signifie caviarder, main fermée remplacer,
  main ouverte récupérer.

- **Un document Office préparé est désormais refusé par le programme
  lui-même.** Un fichier Word, Excel ou OpenDocument peut contenir des
  instructions qui, à l'ouverture, font entrer un fichier étranger de votre
  ordinateur dans son texte ou saturent la mémoire vive. Les deux étaient
  déjà refusés jusqu'ici – mais par la bibliothèque XML intégrée, pas par
  Maskuro. Désormais, le programme en décide lui-même, indépendamment de la
  version de cette bibliothèque présente dans le paquet. Pour les documents
  ordinaires, rien ne change.

### Corrigé

- **Le panneau de résultats supprime désormais les espaces réservés
  caviardés.** Si par exemple `[NAME_1]` était caviardé dans la fenêtre de
  retouche, sa ligne de valeur restait jusqu'ici à droite, bien qu'il n'y
  ait plus un tel emplacement dans le document. La ligne disparaît
  désormais avec le dernier emplacement trouvé ; si le même espace réservé
  apparaît encore ailleurs, elle est conservée.

- **Lors de la récupération sur une page tournée, le mot voisin reste
  désormais en place.** La barre de caviardage dépasse volontairement un
  peu le texte ; cette fine bordure suffisait jusqu'ici parfois à emporter
  un mot adjacent comme « im ». Seul un chevauchement net compte désormais,
  pas le simple contact au bord.

- **Un deuxième remplacement dans la même ligne emportait la suite de la
  phrase.** Qui remplaçait deux fois de suite « Sachbearbeitung Quaxi
  Blubbo übernimmt » obtenait « Sachbearbeitung [ORT_1] [ORT_2] » – le mot
  qui suivait avait disparu sans remplacement, sans aucun message. La
  cause était l'espace réservé voisin : le reste de la ligne commence après
  le premier remplacement par un espace, et la recherche de sa position
  textuelle saisissait la parenthèse fermante du voisin. Ensuite, tout
  était décalé d'un caractère. Était touchée chaque ligne dans laquelle on
  remplaçait ou caviardait deux fois – y compris lors de la récupération à
  côté.

- **Remplacer ne caviarde plus lorsque l'espace réservé est trop long.**
  S'il n'y avait pas de place à côté du mot pour `[BEGRIFF_2]`, la zone
  était jusqu'ici recouverte de noir – et l'on ne voyait alors plus qu'il y
  avait eu quelque chose là, encore moins de quoi le récupérer. Une
  écriture plus courte est désormais utilisée : `[BEGR_2]`, `[BE_2]`, en
  dernier recours `[B_2]`. Le numéro d'ordre reste présent à chaque
  niveau – c'est lui qui permet à la récupération de retrouver
  l'emplacement. Seulement là où même la plus courte ne rentre pas, on en
  reste à la barre.

- **Remplacer laissait le texte en place si un caviardage avait déjà eu lieu
  sur la même ligne.** Qui récupérait un nom depuis l'original dans la
  fenêtre de retouche, en remplaçait le prénom (il n'y avait pas de
  place – une barre était apparue), puis remplaçait le nom de famille,
  obtenait l'espace réservé inséré, mais le nom **n'était pas supprimé**.
  Cela n'a été remarqué qu'à l'avertissement de la relecture. La cause
  était la ligne elle-même : après le premier caviardage, le reste
  commence par un espace, et la recherche de la position textuelle n'y
  trouvait pas de point d'ancrage. Cela touchait chaque deuxième caviardage
  sur la même ligne.

- **Une détection avancée activée sans son modèle est désormais signalée.**
  La case pouvait être cochée alors que le modèle manquait – les
  paramètres valent pour chaque installation, mais le modèle se trouve à
  côté du programme. Le nettoyage se déroulait alors sans ce niveau, sans
  un mot à ce sujet. Désormais, la case indique que le modèle manque, et le
  résultat porte un avertissement. Votre choix une fois fait reste
  enregistré : dès que le modèle est chargé, il redevient effectif.

- **Lors de l'anonymisation, c'est désormais le bon terme qui est
  récupéré.** Qui remplaçait manuellement plusieurs termes puis en
  récupérait un obtenait toujours le **premier** – « Schmidt » devenait
  « Müller ». L'affectation ne mémorisait qu'un seul remplacement par
  espace réservé, et lors de l'anonymisation tous portent le même espace
  réservé ; le deuxième terme et tous les suivants disparaissaient donc.
  Désormais, chaque valeur reçoit sa propre ligne – aussi dans la liste des
  remplacements, qui était auparavant trop courte.

- **Dans les tableaux, la récupération fonctionne désormais aussi.** Dans un
  CSV ou une liste de personnel, les espaces réservés se trouvent
  directement côte à côte, séparés seulement par un point-virgule. Jusqu'ici,
  le programme ne pouvait pas y établir quelle valeur se trouvait à quel
  endroit, et refusait – cela fonctionnait pour `[NAME]`, pas pour
  `[GEBURTSDATUM]` et `[TELEFON]`. Désormais, il décompose la ligne à tous
  les espaces réservés. Si un emplacement reste vraiment ambigu, il continue
  de refuser : une valeur mal réinscrite serait pire qu'une information
  manquante.

- **Et le refus est désormais visible.** Il figurait en gris discret au bas
  de la fenêtre, et la phrase était si longue qu'elle était tronquée – on
  aurait dit que rien ne se passait. Les phrases sont raccourcies, et la
  ligne s'illumine quelques secondes dans la couleur d'avertissement.

- **Une récupération tient désormais aussi après l'intervention
  suivante.** Qui récupérait plusieurs emplacements lors de l'anonymisation
  puis remplaçait autre chose retrouvait tous les emplacements récupérés à
  nouveau remplacés et devait recommencer depuis le début. La cause était
  l'affectation : elle conservait la valeur, et le rapprochement
  automatique pour des espaces réservés uniformes la récupérait à la
  prochaine écriture. Désormais : ce que vous récupérez reste récupéré –
  d'autres emplacements de la même valeur n'en sont pas affectés.

- **Dans les fichiers texte, Word, Excel et e-mail, un simple clic dans
  l'espace réservé suffit désormais vraiment.** Le message à ce sujet
  figurait déjà dans la version précédente, mais le bouton « Récupérer la
  sélection » restait verrouillé tant que rien n'était marqué précisément –
  on n'arrivait donc pas du tout au chemin qui aurait posé lui-même la
  sélection.

### Corrigé

- **Le journal de vérification ne révèle plus le nom du fichier.** Il
  répertorie délibérément les fichiers sous forme de valeur de hachage
  plutôt qu'en texte clair, car un nom de fichier trahit le client et
  l'objet du litige. Cette valeur de hachage pouvait cependant être
  confirmée par tâtonnement – un chemin n'est pas un nombre aléatoire.
  Désormais, une valeur aléatoire propre à cette installation entre dans le
  calcul : compter et distinguer dans le journal continuent de
  fonctionner, mais plus le recalcul depuis l'extérieur.

## 0.10.31-alpha.20260819 – 19 août 2026

### Amélioré

- **Dans les fichiers texte et tableur aussi, l'espace réservé s'allume en
  rouge au survol.** Jusqu'ici, l'aperçu rouge n'existait que sur une page
  PDF. Les deux vues montrent désormais la même chose : ce qui est rouge est
  touché par le prochain geste – et un clic dedans suffit pour récupérer.

- **Un clic sur un mot suffit – l'éditeur pose lui-même le rectangle.** Dans
  la fenêtre de retouche, il fallait jusqu'ici tirer un rectangle sur chaque
  emplacement. Désormais un clic suffit : le cadre se pose autour du mot et
  reste manipulable, donc peut encore être agrandi ou déplacé. Au survol de
  la souris, le mot s'allume déjà en rouge, ce qui permet de voir à l'avance
  ce que le clic toucherait. Là où il n'y a pas de mot, on trace un cadre
  comme avant.

- **Il n'est plus nécessaire de viser précisément avec le rectangle.** Qui
  trace un rectangle sur un espace réservé ou un caviardage vise toujours
  l'emplacement entier – jamais la moitié. Le cadre s'étend donc
  automatiquement à l'ensemble qu'il touche : à tout l'espace réservé, à
  toute la barre ou, sur une page scannée, à toute la zone caviardée. Il ne
  devient jamais plus petit que le cadre tracé.

- **Le caviardage se fait désormais mot par mot.** Un cadre sur la moitié
  d'un mot ne caviardait jusqu'ici que cette moitié – et un nom à moitié
  caviardé reste un nom. Les mots touchés sont désormais entièrement
  supprimés ; le voisin reste intact.

- **Dans le texte et les tableaux, un clic dans l'espace réservé suffit.**
  « Récupérer la sélection » exigeait jusqu'ici que l'on marque précisément
  l'espace réservé avec ses crochets. Désormais il suffit d'y placer le
  curseur ; la sélection saute visiblement sur l'espace réservé entier.

- **La Belgique s'est ajoutée comme pays.** Sélectionnable dans les
  paramètres ; sont alors reconnus les numéros de téléphone belges, le
  numéro de registre national (avec chiffre de contrôle), le numéro de
  TVA/d'entreprise (avec chiffre de contrôle), les adresses dans les deux
  langues officielles et le code postal avec localité. Jusqu'ici, les
  numéros de téléphone belges restaient en place, le pays ne figurant pas
  du tout dans le catalogue.

- **Le canal de mise à jour indique désormais à quel point vous recevez les
  nouveautés tôt – pas jusqu'où.** Qui était réglé sur « version de test »
  ne se voyait même pas proposer une nouvelle préversion ou une nouvelle
  version stable, et devait changer de canal manuellement pour même en
  entendre parler. Désormais, tout ce qui est plus fiable est aussi
  proposé : version de test prend versions de test, préversions et
  versions stables, préversion prend préversions et stables. Jamais
  l'inverse – sur préversion, aucune version de test n'est proposée, même
  plus récente.

- **Dans la fenêtre des paramètres, les lignes restent davantage
  espacées.** Les quatre pages utilisaient leurs propres espacements au
  lieu de la grille valable dans le reste du programme ; sur la page
  « Détection » en particulier, les cases à cocher se trouvaient de ce fait
  sensiblement trop serrées.

### Corrigé

- **Les formulaires PDF remplis n'apparaissent plus vides lors de la
  retouche manuelle.** Pour cela, Maskuro ne transforme en pages statiques
  que la copie de travail éphémère : les valeurs saisies deviennent
  visibles et peuvent vraiment être caviardées ; les champs de formulaire
  lisibles ne restent pas cachés dans le fichier. L'original reste
  interactif et inchangé.
  Cela vaut désormais aussi pour les formulaires XFA dynamiques : un PDFium
  compatible XFA construit d'abord les valeurs et sauts de page, puis un
  nouveau PDF est créé exclusivement à partir de pages image statiques. Si
  la construction XFA échoue, le fichier est refusé en toute sécurité au
  lieu d'être ouvert apparemment vide.

- **« Annuler » agit désormais aussi pendant la détection plus précise.**
  Jusqu'ici, le bouton se verrouillait au clic, mais l'exécution continuait
  de calculer jusqu'au dernier bloc – pour un fichier long, cela représente
  des minutes sans issue, et le bouton avait pourtant l'air d'avoir agi.
  Désormais l'exécution se termine au prochain bloc.

- **Dans les fichiers CSV, les noms sont désormais trouvés aussi quand il
  n'y a pas d'espace devant eux.** Dans `P-1000;Brunnthaler, Elisabeth`, le
  numéro de personnel colle au nom par-dessus le point-virgule, et pour la
  détection c'était un seul mot sans nom dedans – dans les listes de
  personnel, le nom entier restait donc en place selon la ligne. Les
  numéros de téléphone, les formules et le nombre de colonnes du fichier ne
  sont pas affectés.

- **Un nom dont le prénom et le nom de famille portent tous deux un
  trait d'union est désormais reconnu.** « Marie-Luise Habsburg-Ott »
  restait en place en plein milieu de la phrase, tandis que
  « Dragan Mitrović » était trouvé dans la même phrase – c'est justement
  la combinaison de deux moitiés couplées que le modèle de langage
  manquait. Les mots communs couplés comme « Nord-Süd-Verbindung » ou
  « Software-Entwickler » ne sont pas affectés.

## 0.10.30-beta.1 – 18 août 2026

### Amélioré

- **La taille de police de la vue texte peut désormais être réglée
  visiblement.** Le curseur en bas à droite, qui ne faisait jusqu'ici
  zoomer que l'aperçu des pages, règle dans la fenêtre de retouche pour
  les fichiers texte et Office la taille de police (50–300 %) – de même
  « Agrandir »/« Réduire » dans le menu Affichage. Ctrl+molette pouvait
  déjà toujours le faire, mais seul le savait qui l'avait essayé ;
  désormais curseur, affichage et molette vont de pair.

- **Dans l'apparence sombre, une feuille blanche repose désormais sur un
  plan de travail sombre.** Jusqu'ici c'était l'inverse : autour de la
  feuille restait une zone claire, et le texte lui-même était clair sur
  fond sombre. Désormais la feuille reste blanc papier avec une écriture
  noire dans les deux apparences – comme une page PDF, qui elle non plus
  ne devient pas sombre en mode sombre – et la zone autour est sombre.

### Corrigé

- **Après un caviardage en plein milieu d'une phrase, le reste de la
  phrase ne se perd plus.** Qui, dans la fenêtre de retouche, revenait
  trois fois sur le même endroit – remplacer, caviarder, puis « récupérer
  l'original » – voyait le début de la phrase supprimé : de
  « Rückfragen richten Sie bitte an das Rechnungswesen. » on obtenait
  « bitte an das Rechnungswesen. », sans avertissement. Était touché tout
  emplacement où quelque chose avait déjà été retiré une fois en plein
  milieu d'une ligne.

- **Une erreur au démarrage n'entraîne plus la fermeture avec elle.** Si
  la construction de la fenêtre principale échouait, la fermeture via
  l'icône de la barre des tâches plantait ensuite aussi – et cette
  seconde erreur masquait la cause réelle dans le rapport d'erreur.
  Désormais le programme se ferme proprement même depuis une fenêtre à
  moitié construite, et les paramètres enregistrés restent intacts.

- **« Avant/Après » ne saute plus au début du document.** Qui avait fait
  défiler vers le bas dans la fenêtre de retouche et basculait sur
  l'original pour comparer se retrouvait tout en haut – et devait
  retrouver l'endroit à la main. La vue reste désormais sur la même
  ligne, dans les deux sens.

- **Lors du caviardage, le dernier caractère restait sur les lignes en
  justifié.** Quand une commande de texte dessine plus de glyphes que la
  bibliothèque de lecture n'en signale de caractères – elle avale
  volontiers un espace en justifié –, l'affectation se décalait d'un
  cran, et « Dr. Michael Handler aus Willendorf » devenait
  « [NAME] r aus f » : deux lettres restées en place au milieu de la
  phrase nettoyée (trouvé dans un vrai procès-verbal de conseil).
  L'affectation est désormais revérifiée sur le libellé même de la
  commande, là où celui-ci est lisible – on ne devine plus.

- **« Lerchenfelder Gürtel 43/12 » n'était supprimé qu'à moitié.** Les
  modèles d'adresse ne connaissaient ni Gürtel, Kai, Lände, Zeile, Markt
  ni Graben comme mot de base de rue, et le numéro de maison ne pouvait
  pas comporter de parties séparées par une barre oblique (43/12,
  Haus/Tür) – le numéro restait à côté de l'espace réservé. Les deux ont
  été complétés ; les adresses viennoises et salzbourgeoises tombent
  désormais entièrement.

- **Les pages web enregistrées restent fonctionnelles après le
  nettoyage.** Les adresses que le chargement différé (lazy loading)
  dépose dans des attributs data (`data-lazy-src`, `data-lazy-srcset`)
  étaient remplacées comme des liens – seize occurrences sur une vraie
  page de commune – et les images de la page ne se chargeaient plus
  ensuite. Les adresses web y restent désormais en place, comme dans
  `src` et `href` également ; les noms, adresses e-mail et numéros de
  téléphone dans les attributs data continuent d'être remplacés.

- **Les documents japonais et coréens étaient traités comme du
  chinois.** La détection de langue mettait les trois écritures dans le
  même panier, ne trouvait dans le texte japonais (sans espaces) et
  coréen (avec particules collées) aucun mot fonctionnel – et prenait
  alors simplement la première langue CJK du catalogue. Un
  procès-verbal de conseil japonais et un procès-verbal de réunion
  coréen étaient ainsi lus avec le modèle chinois. Désormais, l'aspect
  de l'écriture décide lui-même : kana signifie japonais, hangeul
  signifie coréen.

- **Autres erreurs de l'essai terrain dans dix autres langues :** des
  fonctions comme « Primar », « Gradonačelnik », « Ordfører », « Başkanı »
  ou « Δήμαρχος » ne comptent plus comme noms de personne ; les libellés
  de champ turcs (« Adı », « Soyadı ») et les mots de conversation grecs
  (« Ωραία », « Βεβαίως ») ne disparaissent plus ; les numéros de
  décision et de paragraphe avec date (« 323/25-6-2008 », « 27
  30.09.2024 ») ne sont plus des numéros de téléphone ; et les fragments
  de phrase avec point (« 10.An », « T.U.EE », « …pa ») ne sont plus
  remplacés comme adresses web.

### Nouveau

- **Rapports de vérification automatiques sur demande.** Une case dans
  les paramètres (page « Programme ») dépose de elle-même un PDF de
  rapport de vérification après chaque nettoyage – avec horodatage dans
  le nom, dans un dossier propre, jamais à côté du résultat. Une feuille
  ne peut pas être générée après coup ; qui en a besoin pour le dossier
  l'a ainsi toujours. Le dépôt est désactivé par défaut.

- **Le journal de vérification peut désormais être activé dans le
  programme.** Lors de la lecture d'une licence d'entreprise, Maskuro
  demande une fois si le journal doit être tenu – une preuve ne vaut que
  si elle fonctionne dès le début. Il existe pour cela un interrupteur
  dans les paramètres (page « Programme », visible avec une licence
  d'entreprise ou pendant la période d'essai) ; le fichier de consignes
  de l'administration reste valable et peut toujours imposer la valeur
  comme avant. Une ligne de journal propre « activé » consigne depuis
  quand le journal est tenu – ce qui atteste et signe aussi le début de
  l'enregistrement. Le journal reste désactivé par défaut.

- **Le volet des indicateurs montre ce qu'a fait le niveau IA.** Une
  nouvelle ligne indique combien de résultats incertains le modèle a
  évalués, conservés et rejetés, et combien il en a trouvé en plus –
  jusqu'ici son travail était invisible tant qu'on ne cliquait pas sur
  chaque valeur dans l'éditeur de retouche. Seulement des chiffres,
  jamais de valeurs ni de justifications ; sans travail de l'IA, la
  ligne n'apparaît pas.

- **La récupération fonctionne désormais aussi dans les e-mails et les
  pages HTML.** Dans les fichiers `.eml`, `.msg` et les pages web
  enregistrées, un espace réservé ne pouvait jusqu'ici pas être annulé –
  l'application le disait honnêtement, mais c'est justement l'e-mail qui
  est le format avec le plus de données personnelles. Désormais la
  récupération y fonctionne pareillement : depuis le panneau de
  résultats, avec une sélection marquée et même pour les espaces
  réservés anonymisés. La branche HTML invisible d'un e-mail (ce
  qu'Outlook affiche réellement) est alors entraînée avec, afin que la
  vue et le message disent la même chose.

- **Le panneau de résultats récupère aussi les valeurs anonymisées – par
  valeur.** « Annuler le remplacement » était jusqu'ici verrouillé pour
  les fichiers anonymisés, car « [NAME] » représente tous les noms à la
  fois. Désormais la récupération vérifie dans l'original quel
  emplacement appartient à quelle valeur – dans le PDF aux coordonnées
  de l'emplacement trouvé, dans la vue texte via la comparaison avec
  l'original – et ne ramène que les emplacements de la valeur choisie.
  Les lignes des autres valeurs restent en place.

- **Les espaces réservés anonymisés aussi peuvent être récupérés
  individuellement.** Lors de l'anonymisation, toutes les données d'un
  type portent le même nom – « [NAME] » représente chaque personne, et
  jusqu'ici il était donc dit : récupérer individuellement n'est pas
  possible. Désormais, on consulte l'original, qui se trouve de toute
  façon à côté du résultat : marquer l'espace réservé dans la vue texte
  et choisir « Récupérer la sélection » – revient exactement cet
  emplacement avec exactement sa valeur. Si la valeur ne peut pas être
  lue sans ambiguïté dans l'original, l'application le dit au lieu de
  deviner. Aucun fichier d'affectation n'est créé pour autant.

- **La fenêtre de retouche s'ouvre désormais d'elle-même après le
  nettoyage.** Aucun outil ne trouve tout – c'est pourquoi le regard de
  vérification sur le résultat fait partie du cas normal, pas d'un clic
  supplémentaire. Qui ne le souhaite pas le désactive dans les
  paramètres sous « Détection » (« Afficher ensuite le résultat dans la
  fenêtre de retouche »).

### Amélioré

- **Le choix du pays est désormais réglé sur « automatique ».** Jusqu'ici,
  l'aire linguistique de l'interface s'appliquait par défaut – sur un
  ordinateur allemand, des documents néerlandais ou français n'étaient
  donc nettoyés qu'avec les détecteurs DACH, et une adresse comme
  « Universiteitslaan 1 » restait en place (trouvé dans de vrais
  procès-verbaux de conseil publics). Le choix du pays s'oriente
  désormais selon la langue du document ; qui a fait un choix fixe dans
  les paramètres le conserve.

- **Moins de caviardages erronés.** Une série de faux positifs, mesurés
  sur le corpus de vérification et sur de vrais procès-verbaux de
  réunion en six langues, disparaît : les raisons sociales avec forme
  juridique (« Musterfirma GmbH ») ne comptent plus comme personne ou
  lieu, mais comme organisation ; les formules de politesse et
  formules d'appel nues (« Saygılarımızla », « Buenas tardes », un
  « Frau » isolé) ne sont plus des noms ; les fonctions (« Bürgermeister »,
  « Sindaco », « Alcalde ») restent en place ; les numéros de loi et de
  décision (« 39/2015 ») et les montants avec point de milliers
  (« 330.000 ») ne sont plus des numéros de téléphone ; les débuts de
  phrase comme « Envíame » ou « Estarei » ne tombent plus comme nom ; un
  résultat traversant une ligne vide ne compte plus comme nom. Le numéro
  de facture d'une facture reste conservé en tant qu'indication de
  pièce comptable – numéro de client et référence de dossier continuent
  de tomber.

- **Avant le chargement du modèle IA figure désormais à quoi il sert.**
  La boîte de dialogue de téléchargement nomme les tâches du modèle –
  évaluer des résultats limites, trouver des noms supplémentaires,
  proposer des règles et des profils – et dit ouvertement que ce n'est
  pas un assistant de conversation. La FAQ répond en détail à la même
  question (« Que peut faire le niveau IA – et que ne peut-il pas
  faire ? »), dans toutes les versions linguistiques.

### Corrigé

- **Les PDF de rapport de vérification depuis la ligne de commande sont
  désormais consultables par recherche.** Sous Windows, le chemin PDF
  sans interface démarrait sans une seule police – chaque caractère
  était dessiné comme une case de substitution, et la feuille ne portait
  aucun texte lisible : qui voulait y chercher ou en copier quelque
  chose ne trouvait rien. Désormais le rapport recharge dans ce cas les
  polices du système ; le texte est intégré et lisible. Les rapports
  générés depuis la fenêtre n'ont jamais été touchés.

- **« Récupérer l'original » sur plusieurs lignes d'un scan laissait des
  bandes noires entre les lignes.** Sur une page convertie en image, le
  cadre ne nettoyait que les bandes de ligne elles-mêmes ; les restes de
  l'ancien caviardage subsistaient dans les interstices. Désormais le
  cadre tracé se répartit entièrement sur les lignes.

- **Un deuxième cadre sur un espace réservé laissait un reste rouge.**
  L'espace réservé est presque toujours plus large que le mot qu'il
  remplace ; qui caviardait ensuite au même endroit ne touchait que son
  début – il restait un fragment comme « RIFF_1] » au milieu de la
  phrase, et la récupération plaçait ensuite le texte original à sa
  position au lieu de celle du mot. Un espace réservé partiellement
  touché tombe désormais toujours en entier.

- **Sur une page tournée, le caviardage sur un espace réservé supprimait
  une phrase sans rapport.** L'espace réservé dessiné après coup était
  confondu, lors de la suppression, avec le texte devant lui : il
  restait lui-même en place, l'avertissement « figure encore dans le
  document » apparaissait – et ailleurs sur la page, une phrase sans
  rapport avec le cadre disparaissait sans remplacement. Un espace
  réservé est désormais retrouvé via son libellé ; la chaîne
  « remplacer, caviarder, récupérer » fonctionne donc aussi sur des
  pages tournées.

- **Le manuel conseillait encore `python3-tk` dans dix langues.** Dans le
  dépannage, il était indiqué que tkinter pouvait manquer sous Linux –
  un conseil datant d'avant l'interface Qt, qui n'aide plus personne.
  Désormais, toutes les versions comportent le même paragraphe qu'en
  allemand : ce sont les bibliothèques système dont Qt a besoin pour
  l'affichage qui manquent.

- **Le chapitre licence du manuel était obsolète dans les seize
  traductions.** Dans dix langues, on y lisait encore que Windows Server
  nécessitait une licence d'entreprise avec accès serveur et que la
  période d'essai et l'offre gratuite n'y existaient pas – depuis qu'une
  place compte une personne et non une machine, les deux sont faux. Il
  manquait en outre partout les informations sur le moment où une place
  occupée se libère à nouveau, sur le fait que la licence se confirme
  régulièrement et ce qui est transmis à cette occasion, et
  l'activation sans internet ne figurait que sous forme abrégée sans
  les trois étapes et sans l'indication que l'ordinateur travaille
  ensuite un an sans connexion.

- **Sept paragraphes sur la retouche manquaient dans dix langues.** Qui
  lisait l'aide en danois, finnois, français, italien, néerlandais,
  norvégien, polonais, portugais, suédois ou espagnol ne trouvait ni
  l'aperçu des pages pour les fichiers Office, ni « Caviarder à la
  main », ni toute la section sur la façon dont le programme apprend
  d'une correction – tableau des trois niveaux de largeur compris. Dans
  « Ce qui est détecté », il manquait dans ces mêmes dix versions la
  voie passant par le libellé dans le document.

- **Avec une licence lue, le programme ne démarrait plus.** Au lieu de la
  fenêtre apparaissait « Le programme n'a pas pu démarrer » – et cela
  pour chaque licence, quelle qu'elle soit. La cause était la ligne de
  l'affichage de licence qui avertit peu avant l'expiration de la
  période d'essai ; elle accédait à quelque chose qui n'était pas
  disponible à cet endroit. Sans licence – pendant la période d'essai et
  dans l'offre gratuite – l'erreur ne se produisait pas, c'est pourquoi
  elle n'a été remarquée que maintenant.

- **Dans le formulaire, les noms de champ restent en place.**
  « Geburtsdatum » et « Anschrift » disparaissaient avec leur valeur :
  l'espace réservé se trouvait petit et rouge à l'emplacement du *nom du
  champ*, le champ en dessous restait vide. Le nom du champ ne fait pas
  partie des données – il reste désormais, et l'espace réservé se trouve
  là où était la valeur.

- **Les titres de document en langue étrangère ne sont plus pris pour des
  noms.** Au-dessus d'un formulaire italien figurait « FATTURA », au-dessus
  d'un espagnol « PERMISO PARENTAL » – les deux étaient remplacés. La
  liste des mots de document ne connaissait que les équivalents
  allemands.

- **Une position ne disparaît plus d'une facture.** « Materialaufschlag
  1  84,00 » était pris pour une adresse et remplacé par un espace
  réservé de lieu – il manquait ensuite une ligne à la pièce comptable.
  Une ligne se terminant par un montant est une position et non une
  adresse ; les vraies adresses (« Hauptstraße 1  120,00 ») ne sont pas
  affectées.

### Modifié

- **« Surveiller un dossier … » et la ligne de commande ne sont pour
  l'instant plus là.** Les deux voies sont construites et fonctionnent,
  mais aucune des deux n'est éprouvée sur le terrain : la surveillance de
  dossier n'a jamais connu de passage sous Windows, et la ligne de
  commande met deux douzaines d'interrupteurs entre les mains d'un
  script, qui n'ont jamais tourné chez aucun utilisateur. Ce qui modifie
  des documents sans surveillance ne doit pas le faire sans avoir été
  vérifié – c'est pourquoi elles sont retirées jusqu'à ce que le passage
  soit rattrapé. L'entrée de menu manque, et `--wache` ne figure plus
  dans `maskuro --help`.

- **Ce qui reste, c'est ce qui ne fait que lire et ce dont on a besoin de
  toute façon.** La recherche (`--suchlauf`) et la vérification
  (`--nachpruefen`) continuent de fonctionner en ligne de commande –
  elles ne modifient aucun fichier. De même le démarrage via l'Explorateur,
  le menu contextuel, le presse-papiers et la fenêtre ; rien n'y change.

- **« Récupérer depuis le scanner » a désormais son propre chapitre dans
  le manuel.** Il figurait jusqu'ici à la fin de « Surveiller un
  dossier ». Sur le Mac, le conseil y était de faire surveiller un
  dossier ; il est désormais de glisser les pages numérisées dans la
  fenêtre.

### Corrigé

- **« Récupérer l'original » sur plusieurs lignes détruisait la
  structure.** Un cadre par-dessus un espace réservé, un intitulé de
  poste inchangé et un deuxième remplacement recomposait toute la zone en
  **une seule** ligne – trois lignes devenaient une, et ce qui ne
  rentrait plus devenait une barre. Désormais chaque ligne est récupérée
  séparément.

- **Et le texte inchangé reste intact.** Qui trace un cadre sur un
  remplacement *et* du texte ordinaire ne récupère que le remplacement ;
  le reste n'est pas touché. Le dernier reste de l'ancien espace réservé
  disparaît également au passage – auparavant sa parenthèse fermante
  restait au milieu de la phrase.

- **Lors du remplacement, il ne reste plus de restes de l'ancien
  texte.** Dans un titre en gras se trouvait ensuite
  « 1. R[BEGRIFF_2]ige [BEGRIFF_1] … che » – l'espace réservé était bien
  là, mais des syllabes de l'original juste à côté. C'est désormais la
  zone que vous entourez qui est nettoyée, pas seulement les cadres des
  mots qu'elle contient.

- **Un espace réservé anonyme n'est plus récupéré.** Lors de
  l'anonymisation, chaque nom porte le même `[NAME]`. La récupération
  prenait la première entrée venue et l'écrivait à chaque emplacement
  trouvé – « Georg Aigner » devenait « Anna Musterfrau », donc un nom
  erroné dans le document. Il est désormais indiqué qu'on ne peut plus
  dire quelle donnée était visée ; le document reste intact.

### Nouveau

- **« Récupérer l'original » fonctionne désormais aussi sur une page
  rastérisée.** Si une page avait été convertie en image, un refus
  apparaissait jusqu'ici : le texte récupéré se retrouverait sous
  l'image de page. Désormais, l'emplacement dans l'image est nettoyé et
  le texte y est écrit – comme un espace réservé sur un scan. Le contenu
  provient alors du fichier original, qui lui n'est pas rastérisé.

- **« Récupérer la sélection » est désormais un bouton à part
  entière.** C'était déjà possible auparavant, mais seulement si l'on
  marquait par hasard un espace réservé et appuyait sur « Remplacer la
  sélection » – une fonction que l'on ne trouve que par hasard n'existe
  pas pour l'utilisateur.

### Modifié

- **En texte brut, CSV et messages Outlook, il n'y a plus de « Caviarder
  la sélection ».** Ces formats ne peuvent pas porter de barre ; le
  bouton y posait un espace réservé et le disait aussi – mais un bouton
  qui fait autre chose que ce qu'il annonce n'a pas sa place.

- **Un outil indique désormais quand il n'y a rien à faire à cet
  endroit.** Un espace réservé ne peut pas être remplacé une deuxième
  fois, aucun espace réservé n'est posé sur un caviardage, et là où se
  trouve déjà l'original, il n'y a rien à récupérer. Jusqu'ici, ces
  gestes faisaient quelque chose qui avait l'air d'un effet, sans qu'il
  y en ait un.

## 0.10.29-alpha.20260817 – 17 août 2026

### Corrigé

- **Dans la fenêtre de retouche, chaque cadre que l'on trace agit
  désormais.** Qui travaillait deux fois au même endroit – d'abord
  remplacer, puis caviarder, puis récupérer l'original – voyait son
  deuxième et son troisième geste s'évaporer sans un mot : le cadre
  encore manipulable du geste précédent l'interceptait. Même chose lors
  d'un changement d'outil, où l'ancien outil continuait même
  silencieusement à agir.
- **Un cadre tracé trop étroit indique désormais qu'il est trop
  étroit.** Jusqu'ici, l'aperçu allumait un mot en rouge, et au
  relâchement, rien ne se passait sans un mot.

- **Les messages Outlook peuvent enfin être retouchés.** Un `.msg`
  affichait dans la fenêtre de retouche « Ce format ne peut pas être
  affiché ici » – c'était le seul format pris en charge sans aucun moyen
  de retravailler à la main. Désormais, l'expéditeur, le destinataire,
  l'objet et le texte du message figurent nommés dans la vue et peuvent
  être marqués et remplacés comme dans tout autre format texte.

- **« Remplacer la sélection » reste limité à la sélection dans un
  e-mail.** Qui marquait un nom dans le corps du texte perdait aussi
  l'expéditeur et le destinataire des en-têtes, et le message citait un
  autre espace réservé que celui figurant dans le texte. Désormais, la
  valeur marquée est remplacée partout – aussi dans l'expéditeur, si
  elle y figure – et rien d'autre n'est touché.

- **Un cadre sur plusieurs lignes ne détruit plus le texte.** Jusqu'ici,
  un seul espace réservé apparaissait à un endroit : du mot coupé
  restait un reste collé, et le texte de la deuxième ligne disparaissait
  sans remplacement – ni espace réservé, ni barre, seulement un trou.
  Désormais, chaque ligne reçoit son propre espace réservé avec la
  valeur qui s'y trouvait réellement.

- **« Récupérer l'original » agit désormais aussi après un
  caviardage.** La fenêtre signalait un succès, et le texte ne revenait
  jamais : la barre noire comptait comme obstacle, si bien qu'il ne
  restait plus de place pour le texte récupéré. La barre cède désormais,
  et le texte récupéré s'affiche en noir comme un texte ordinaire – pas
  en rouge comme un espace réservé.

- **« Récupérer l'original » à un endroit non touché ne fait désormais
  plus rien.** Qui traçait le cadre sur du texte où rien n'avait été
  modifié voyait le texte supprimé puis réinséré plus petit et décalé –
  un succès était pourtant signalé. Il est désormais indiqué qu'il n'y a
  rien à récupérer.

### Nouveau

- **Le caviardage est désormais aussi possible dans Word, Excel,
  PowerPoint, OpenDocument et texte.** Jusqu'ici, il n'y avait là que
  « Remplacer la sélection » ; une barre était réservée à la vue PDF,
  sans qu'il y ait de raison à cela. Là où une barre n'est pas
  représentable – en texte brut et dans un message Outlook –, la valeur
  est remplacée comme avant par un espace réservé, et cela est indiqué
  ainsi dans le message.

- **Marquer un espace réservé le récupère.** Dans la vue texte (Word,
  Excel, PowerPoint, OpenDocument, texte), il suffit désormais de
  marquer l'espace réservé et d'appuyer sur « Remplacer la sélection » :
  la valeur d'origine revient. Jusqu'ici, la fenêtre renvoyait pour cela
  au panneau de résultats.

- **Les intervenants dans un procès-verbal de réunion sont désormais
  reconnus même quand leur nom est en même temps un mot ordinaire.**
  « Gruber: Die Abnahme erfolgt kommende Woche. » était remplacé,
  « Bauer: Ich stimme zu. » restait en place – le nom de famille
  ressemble pour la détection à un nom commun. Les lignes mnémotechniques
  de la même forme restent intactes : « Achtung: Die Anlage ist
  abzuschalten. » ne donne pas de nom.

- **« Vous utilisez la dernière version » était affiché même quand il
  était impossible de vérifier.** Si le serveur de mise à jour rejette
  la demande – parce que trop de demandes provenaient de la même adresse
  internet ou parce qu'il est lui-même momentanément perturbé –, le
  programme restait alors bloqué sur son ancienne version tout en
  affirmant qu'il s'agissait de la dernière. C'est exactement ce qui
  s'est produit le 17 août sur un Mac : la 0.10.25 est restée en place
  pendant que la 0.10.28 était disponible depuis des heures.

  La fenêtre indique désormais ce qui se passe, donne l'heure de la
  prochaine vérification – et signale explicitement qu'il n'est **pas**
  établi que sa propre version soit la dernière.

  La cause n'en est généralement pas l'ordinateur lui-même : sur de
  nombreuses connexions, de nombreux clients partagent la même adresse
  internet, et le serveur les compte ensemble. C'est pourquoi Maskuro
  recherche dans ce cas la liste des versions par une **deuxième voie**
  et trouve la plupart du temps quand même de nouvelles versions. Si le
  refus persiste, le serveur est laissé tranquille jusqu'à l'heure
  indiquée – même si l'on appuie de nouveau sur le bouton ; insister ne
  fait que prolonger le blocage.

- **Les indications de quantité ne sont plus prises pour des noms de
  lieu.** Dans un contrat de service, « Vier-Tage-Woche » disparaissait
  derrière un espace réservé de lieu – en plein milieu de l'objet du
  contrat. De telles combinaisons de mots avec un nombre et un trait
  d'union (« Drei-Punkte-Plan », « 24-Stunden-Dienst ») restent
  désormais en place. Les adresses en sont exclues : un
  « Zwei-Brüder-Weg » continue d'être remplacé.

## 0.10.28-alpha.20260817 – 17 août 2026

### Modifié

- **Les places de licence sont désormais vraiment comptées.** Jusqu'ici,
  aucun poste de travail ne s'enregistrait jamais auprès du service de
  licence – une licence à dix places tournait sur un nombre quelconque
  d'ordinateurs sans que personne ne le sache. Nouveau : l'ordinateur qui
  lance le programme occupe une place ; une place se libère d'elle-même
  après **sept jours sans démarrage**, afin qu'un appareil hors service
  ou un collaborateur parti ne bloque rien durablement.

  Un léger dépassement est **seulement affiché et non bloqué** : jusqu'à
  dix pour cent au-dessus du nombre acheté, tout continue de fonctionner
  – le nouvel ordinateur portable à côté de l'ancien encore connecté ne
  doit pas devenir un cas pour le support. Qui s'ajoute au-delà retombe
  dans l'offre gratuite et en est informé ; les ordinateurs déjà présents
  ne remarquent rien.

- **Une licence achetée se confirme régulièrement.** Si cela échoue
  pendant **30 jours**, l'offre gratuite s'applique à nouveau jusqu'à ce
  que cela réussisse de nouveau. Rien n'est désactivé, et à partir d'une
  semaine à l'avance l'indication figure dans la fenêtre. Dès que
  l'ordinateur retrouve internet, cela se résout de soi-même. La période
  d'essai et l'offre gratuite ne signalent toujours rien du tout – qui
  n'achète jamais n'appelle jamais.

- **« Activer sans internet » fonctionne enfin.** L'activation était
  jusqu'ici bien vérifiée et déposée, mais ensuite lue par personne –
  elle ne changeait rien aux droits. Elle est désormais la solution pour
  les ordinateurs sans accès réseau : elle porte pendant **un an**, après
  quoi on en obtient une nouvelle avec un code de demande récent. Un
  appareil avec internet n'est nécessaire pour cela qu'une fois par an –
  l'ordinateur lui-même reste durablement hors ligne.

- **L'activation se fait désormais aussi depuis le compte client** – sous
  « Mes licences » sur le site. On y trouve en outre quels ordinateurs
  sont rattachés à votre licence et quand leurs places se libèrent à
  nouveau ; cela n'était jusqu'ici visible nulle part. La page sans
  connexion reste disponible pour tous ceux qui n'ont pas d'accès à la
  boutique – elle exige en contrepartie aussi l'adresse e-mail de la
  commande, afin que la clé de licence seule ne suffise pas.

- **Et la fenêtre indique désormais où mettre le code de demande.** La
  procédure papier disait « saisir sur un appareil avec connexion
  internet » sans indiquer d'adresse ; la page d'activation existait
  déjà depuis longtemps, mais n'était liée nulle part. Désormais figure
  **maskuro.com/lizenz-freischalten** dans la boîte de dialogue, dans le
  manuel et dans la FAQ – et sur le site sous la clé de licence.

- **Le bouton « Activer sans internet … » reste visible**, même quand la
  licence n'est pas valide en ce moment. Auparavant, il disparaissait en
  même temps qu'elle – donc précisément quand on en a besoin.

- **« Toutes les places occupées » dit désormais la vérité.** L'indication
  se terminait par « Le programme continue de fonctionner sans
  changement » ; ce n'est plus vrai lorsqu'aucune place n'a été
  attribuée. Il y est désormais indiqué que l'offre gratuite s'applique
  jusqu'à nouvel ordre.

### Nouveau

- **En activant le nettoyage du presse-papiers, il est désormais précisé
  qu'une vérification est nécessaire.** Le message reprend désormais la
  même phrase que celle figurant sur le résultat d'un fichier : Maskuro
  ne détecte pas systématiquement toutes les données personnelles.

  Ici, elle pèse plus lourd qu'ailleurs. Pour un fichier, on voit le
  résultat avant de le transmettre. Pas pour le presse-papiers – on
  copie, on colle, et le texte nettoyé se trouve déjà dans la fenêtre de
  mail. Le message demande donc explicitement de relire le texte
  **collé**.

  Il apparaît à l'activation, pas à chaque copie : ce qui apparaîtrait
  cinquante fois par jour, plus personne ne le lit après la troisième
  fois.

- **« Tout copier » sous la liste – et « Tout supprimer » s'éloigne.** Le
  nouveau bouton met d'un coup tous les résultats terminés dans le
  presse-papiers, pour les joindre à un mail ou les coller dans un autre
  programme. Jusqu'ici, cela ne passait que par le menu et là aussi
  seulement pour les lignes **sélectionnées** – qui voulait tout devait
  d'abord appuyer sur Ctrl+A.

  La rangée de boutons est réorganisée à cette occasion : à gauche se
  trouve ce qui ajoute quelque chose, à droite après un espace ce qui
  retire quelque chose. « Tout supprimer » se trouvait jusqu'ici juste à
  côté de « Ajouter … », et une erreur de clic coûtait toute la liste. La
  même règle vaut déjà depuis le 13 août pour chaque ligne terminée.

- **Les postes de travail sans internet reçoivent désormais leurs modèles
  linguistiques depuis l'entreprise.** Le nettoyage y fonctionnait déjà
  toujours sans connexion – pas le téléchargement d'un modèle
  linguistique, et un modèle pèse plusieurs centaines de mégaoctets.

  L'administration rassemble une fois les fichiers sur un ordinateur
  connecté et les dépose sur un partage, dans le déploiement ou sur une
  clé USB. L'emplacement est saisi de manière centralisée (champ
  `modellquelle` dans `vorgaben.json` ou la variable d'environnement
  `MASKURO_MODELLQUELLE`). À partir de là, chaque téléchargement se sert
  d'abord là – modèles linguistiques, dictionnaire japonais et niveau
  élevé – et ne va sur internet que si un fichier manque.

  Les sommes de contrôle restent valables sans changement. Un partage de
  fichiers interne est souvent plus facile à décrire qu'une publication
  sur internet ; il ne doit pas devenir la voie la plus commode vers un
  modèle glissé en fraude.

  La façon dont un tel stock est constitué et le fonctionnement de la
  licence et de l'activation sans internet figurent dans `OFFLINE.md`.

- **« Récupérer l'original » – un cadre ramène ce qui a été supprimé en
  trop.** Un nouvel outil apparaît dans la fenêtre de retouche : tracer
  un cadre sur l'emplacement, et le texte réapparaît tel qu'il était dans
  l'original.

  Cela comble la lacune que laissait le panneau de résultats. Là, un
  remplacement ne pouvait être annulé que si son espace réservé était
  univoque – donc pas lors de l'anonymisation, où « [NAME] » figure pour
  chaque donnée de ce type, et pas du tout pour les emplacements
  caviardés, où il ne reste aucun espace réservé. C'est justement là que
  s'accumulent les erreurs : « Benutzer », « Inventarnummer »,
  « Unterschrift » sont volontiers pris pour des noms.

  Le cadre n'a pas besoin de l'espace réservé : l'**emplacement** vient
  du rectangle, le **contenu** du fichier original – le même que montre
  le commutateur avant/après. Anonymisé ou pseudonymisé n'a donc plus
  d'importance.

  Le texte récupéré s'affiche en noir, pas en rouge : il redevient du
  texte en clair et non un espace réservé. Une entrée ne disparaît de la
  liste des résultats que lorsque son espace réservé ne figure **plus
  nulle part** dans le document – si la même valeur a été remplacée à
  plusieurs endroits, elle reste pour les autres.

  Sur une page convertie en image, l'outil refuse et explique pourquoi :
  le texte récupéré se retrouverait sous l'image de page et ne serait pas
  visible.

### Corrigé

- **En repliant « Détails » et « Indicateurs », des restes d'image
  restaient à l'écran.** Une fois repliée, une partie du contenu
  glissait sous le bord inférieur de la fenêtre et y restait au-dessus
  de l'arrière-plan, jusqu'à ce que quelque chose d'autre soit dessiné
  par-dessus.

  Les deux zones ont une hauteur minimale afin d'être utilisables une
  fois ouvertes. Le mouvement de repliement ne réduisait toutefois que la
  hauteur maximale – et une zone ne rétrécit pas en dessous de sa hauteur
  minimale. Le contenu restait donc haut de 200 points pendant que la
  fenêtre se contractait déjà à 24 ; la différence se trouvait sous le
  bord. Désormais, la hauteur minimale cède pendant la durée du
  mouvement et revient ensuite.

- **La fenêtre devenait toujours plus petite à chaque repliement et
  dépliement répété.** Au dépliement, elle croît au maximum jusqu'à 92 %
  de la hauteur de l'écran ; si la place manque, elle croît donc moins
  que nécessaire. Au repliement, elle retirait pourtant le montant
  complet. Elle rend désormais exactement ce que le dépliement a coûté.

- **Un reste d'une donnée caviardée pouvait rester visible.** Dans un
  curriculum vitae, les caractères « *30.1 » restaient lisibles dans le
  résultat à partir de « *30.12.1991 » – donc le jour et le début du mois
  de la date de naissance. Le programme avait même remarqué ce reste et
  avait pour cela converti la page en image ; c'est précisément ce qui
  aggravait les choses, car le reste n'était alors plus consultable par
  recherche, mais restait lisible – et n'était plus corrigible.

  La cause se trouvait entre deux vérifications. La plus stricte des deux
  contrôle si, dans la surface d'une donnée supprimée, se trouve encore
  quelque chose qui n'y a pas sa place ; elle signale son constat comme
  un ensemble de caractères, car l'ordre de lecture se décale lors du
  remplacement. Le mécanisme de repli, qui recouvre de telles zones
  avant la conversion, cherchait cet ensemble de caractères comme texte
  sur la page – et ne le trouvait jamais. Rien n'était donc recouvert.
  L'emplacement était connu depuis le début et est désormais transmis
  directement, au lieu d'être recherché à nouveau.

  Était touchée toute page dont le reste n'était trouvé que par cette
  vérification – indépendamment du type de fichier et de la langue.

- **Sur un scan inséré en travers, la reconnaissance de texte ne trouvait
  rien.** Qui insère une feuille latéralement dans le bac obtient un
  fichier où l'écriture est tournée de 90 degrés. Jusqu'ici, Maskuro n'y
  lisait **aucune** donnée – et le fichier avait ensuite l'air anodin :
  rien n'étant trouvé, rien n'était signalé, et l'adresse restait
  lisible dans l'image. Désormais, la reconnaissance de texte redresse
  elle-même la page ; sur l'image de vérification, toutes les données
  tombent de nouveau.

  Deux limites clairement nommées : une feuille **tête en bas** (180
  degrés) n'est toujours pas lue, et pour un scan de très mauvaise
  qualité, le redressement n'aide pas – trop peu y est lisible pour
  seulement déterminer l'orientation. Chaque image nécessite pour cela
  environ un cinquième de temps en plus.

### Modifié

- **« Installer automatiquement » signifie désormais ce que cela fait.**
  La case dans les paramètres promettait plus qu'elle ne tenait : elle
  télécharge d'elle-même la nouvelle version et lance l'installation –
  mais celle-ci se déroule **visiblement** et demande confirmation, sous
  Windows y compris la demande du contrôle de compte utilisateur. Qui
  lisait « automatiquement » s'attendait à un ordinateur qui se met à
  jour lui-même pendant la nuit et se retrouvait le matin devant
  l'assistant d'installation. La case s'appelle désormais « Télécharger
  automatiquement les mises à jour et lancer l'installation », avec une
  phrase en dessous expliquant ce que cela signifie. Le comportement ne
  change en rien : que Maskuro ne se remplace pas à l'insu de
  l'utilisateur est intentionnel et le reste.

## 0.10.27-alpha.20260817 – 17 août 2026

### Nouveau

- **Nouveau : `--ersetzen` pour le rattachement à un logiciel de
  cabinet.** Le résultat prend la place du fichier source, au lieu de se
  créer à côté. L'extraction et la réintégration d'un logiciel de
  cabinet (« ouvrir et modifier » dans le dossier électronique)
  fonctionnent ainsi sans aucune interface : le logiciel restitue le
  fichier et le récupère nettoyé au même emplacement.

  **Cet interrupteur lève le premier principe fondamental**, et c'est
  pourquoi il n'existe qu'en ligne de commande – pas dans la fenêtre –
  et seulement si votre administration l'autorise (entrée `ersetzen`
  dans le fichier de consignes). Sans autorisation, l'appel échoue et
  dit pourquoi ; créer silencieusement un second fichier serait l'erreur
  la plus grave, car la version non nettoyée serait alors réintégrée.

  Seul un fichier voisin est d'abord écrit ; ce n'est que lorsqu'il est
  terminé qu'il prend la place de la source. Une interruption ou une
  erreur laisse ainsi la source **inchangée octet pour octet** et ne
  laisse aucun fragment. Dans le journal de vérification, le
  remplacement figure comme champ propre – un vérificateur doit savoir
  que la version non nettoyée ne se trouve plus ici.

- **Le manuel explique désormais l'avertissement Windows au premier
  démarrage.** Nouvelle première section « Windows avertit au premier
  démarrage – que faire », avec deux images et trois étapes :
  « Informations complémentaires » est un petit lien, pas un bouton –
  c'est exactement là que la plupart restent bloqués –, puis
  « Exécuter quand même ».

  Que « Éditeur inconnu » y figure est le message entier de
  l'avertissement : les paquets sont actuellement livrés sans
  certificat. Nous jugeons plus juste de l'expliquer que de le taire.

- **Le chemin de retour remarque désormais quand texte et affectation ne
  vont pas ensemble.** Qui collait la réponse dans un autre processus
  obtenait jusqu'ici des noms étrangers dans le bon texte – pas
  d'erreur, pas de message, juste faux. Maskuro mémorise désormais quels
  espaces réservés le dernier passage a réellement générés, et signale
  chacun qui n'en fait pas partie. Si aucun d'eux ne provient du dernier
  passage, rien n'est inséré et la fenêtre dit pourquoi – au lieu de
  supposer, comme avant, un délai expiré.

  **Une limite demeure, et elle figure aussi dans le manuel :** les
  espaces réservés sont numérotés par passage, le premier nom s'appelle
  donc `[NAME_1]` dans chaque document. Si le texte étranger ne porte
  que de tels espaces réservés, la confusion n'est pas détectable.

- **Le PDF peut désormais être produit en noir et blanc.** Une case dans
  le mode de fonctionnement convertit chaque page en image noir et
  blanc – avec une couche de texte invisible en dessous, donc toujours
  lisible et consultable par recherche. Pour l'envoi via beA et des
  voies similaires avec des limites de taille strictes : en moyenne
  **68 % plus petit** sur notre corpus de mesure (ligne de commande :
  `--monochrom`).

  **Le gain dépend du document** – et cela figure aussi près de la
  case : le contenu scanné et riche en images se réduit fortement, un
  document texte léger sans polices intégrées peut même grossir.
  Essayez-le sur un fichier avant de l'activer pour un lot.

  Le prix : chaque page est recalculée – pour mille pages, cela prend des
  minutes. Et les illustrations perdent tout ce qui se trouve entre le
  noir et le blanc ; pour du texte, cela est indifférent, pour une photo
  non.

- **La liste de résultats dans la fenêtre de retouche compte
  désormais.** Au-dessus de la liste figure « 5 résultats », et dès que
  vous filtrez, « 1 sur 5 résultats ». C'est la différence entre « j'ai
  filtré » et « il y en a cinq, et je les ai tous vus » – le geste par
  lequel on vérifie qu'un nom a vraiment été remplacé partout.

- **Le journal de vérification peut désormais être parcouru et
  filtré.** La vue sous « Fichier → Journal de vérification » n'avait
  jusqu'ici qu'un tableau et rien d'autre – pour un mois avec trois
  mille passages, on voyait que beaucoup s'était passé, mais pas quoi.

  Sont nouveaux un **champ de recherche**, **trois filtres**
  (procédure, résultat, type) et la **pagination**, ainsi que trois
  colonnes qui n'existaient pas avant : **procédure** (caviardé ou
  remplacé), **confiance** et **durée**. Au-dessus de la liste figure ce
  qui est actuellement visible et ce que le filtre masque.

  « Enregistrer en CSV … » exporte désormais **ce qui est affiché** –
  qui a filtré obtient le résultat filtré, et le message indique le
  nombre.

  Un tiret pour la confiance ou la durée signifie que rien n'a été
  mesuré pour cette ligne – par exemple parce qu'elle est plus ancienne
  que cette fonction. Ces valeurs ne sont **pas** calculées après
  coup. Il n'existe toujours pas de filtre par utilisateur ; une ligne
  individuelle est quand même trouvée par la recherche.

### Supprimé

- **La mention de transparence dans la fenêtre « À propos de ce
  programme » a de nouveau disparu.** Elle y figurait depuis
  0.10.22-beta.1 et indiquait que l'application avait été développée
  avec l'aide de l'intelligence artificielle. Elle n'est exigée nulle
  part, et justement dans une application pour la protection des
  données, certains la lisaient comme une affirmation sur le mode de
  fonctionnement – comme si les documents allaient vers un service en
  ligne. Le nettoyage continue de se faire exclusivement sur
  l'ordinateur lui-même ; cela figure là où c'est sa place, dans
  l'onglet « Confidentialité ».

### Corrigé

- **Le programme échangeait sa propre icône contre une moins bonne.**
  Qui inscrivait le menu contextuel depuis le programme avait ensuite un
  bouclier différent dans la barre des tâches par rapport à celui
  d'après l'installation – similaire, mais avec des barres alignées à
  gauche au lieu du centre, et visiblement plus grossier. La cause était
  un pis-aller : si le programme ne trouve pas le modèle d'icône, il en
  dessine une lui-même. Cela était prévu pour le cas où **aucune** icône
  n'existe ; en réalité, il dessinait aussi quand celles fournies
  étaient déjà présentes – et les écrasait. Dans une version installée
  depuis le programme d'installation, il n'y a pas de modèle, cela
  touchait donc tout le monde là. Les icônes présentes restent désormais
  intactes.

  **Les installations déjà touchées ne récupèrent pas d'elles-mêmes la
  bonne icône** – réinstaller une fois pour cela.

- **« Objektkennung: OB-4711-22 » était considéré comme un nom de
  connexion.** Le détecteur de noms d'utilisateur vérifiait ses
  libellés sans limite de mot devant – donc **chaque** mot se terminant
  par l'un d'eux était saisi : Objektkennung, Fahrzeugkennung,
  Gerätekennung. La valeur derrière était supprimée, bien qu'elle n'ait
  rien à voir avec un nom de connexion.

  Les mots composés réellement visés – « Benutzerkennung »,
  « Anmeldekennung » – figurent séparément dans la liste et continuent
  d'être trouvés.

- **En anglais, grec, japonais et coréen, seize espaces réservés
  restaient en allemand dans le résultat.** Qui avait réglé l'interface
  sur l'une de ces quatre langues obtenait pour les types de données
  plus récents les libellés allemands écrits dans le document – d'un
  mot de passe résultait `[ZUGANGSDATEN_1]` au lieu de
  `[CREDENTIALS_1]`, d'une clé de diagnostic
  `[DIAGNOSESCHLUESSEL_1]` au lieu de `[DIAGNOSIS_CODE_1]`. Étaient
  concernés santé, diagnostic, médication, clés de diagnostic et de
  médicament, religion, syndicat, opinion politique, droit pénal,
  identifiants de connexion, nom d'utilisateur, données de carte,
  coordonnées, profession, montant et caractéristique.

  Les 44 autres langues n'ont jamais eu ce défaut : elles tirent leurs
  libellés des fichiers de langue, où ces types figuraient depuis le
  début. Précisément ces quatre langues gèrent, pour une autre raison,
  leurs propres tableaux – leur écriture ne survit pas au jeu de
  caractères du PDF, c'est pourquoi des libellés latins y figurent –, et
  dans ces tableaux, les nouveaux types manquaient tout simplement.

  Cela a été remarqué en traduisant la page du catalogue : le site web
  promettait aux lecteurs anglais des libellés que le programme
  n'écrivait pas. Un test vérifie désormais les quatre tableaux par
  rapport à la liste de tous les libellés pouvant exister.

- **La fenêtre des règles ne s'ouvre plus trop petite pour son
  contenu.** Dans l'onglet « Modèles de recherche personnalisés », la
  ligne d'explication de l'assistant (« Est recherché : … ») se trouvait
  à moitié derrière le champ « Texte d'essai » – justement la phrase
  qui permet de vérifier, sans connaître les expressions régulières, si
  sa propre règle cherche la bonne chose. La fenêtre avait une taille
  minimale fixe datant d'une époque avec moins d'onglets et pouvait donc
  être tirée en dessous de ce qui y tient. Elle s'adapte désormais à son
  contenu et ne descend que jusqu'à la taille où tout reste lisible.

- **Les noms dans les formules de tableur ne restent plus en place.**
  Une cellule a plus d'un emplacement pour du texte, et jusqu'ici un
  seul était nettoyé. Si un nom se trouvait dans une formule –
  `="Frau "&"Sieglinde Ortner"` – ou était le dernier résultat calculé
  d'une formule, il restait inchangé dans le classeur, bien que la même
  personne soit remplacée dans la cellule voisine. Qui cliquait sur la
  cellule le lisait dans la barre de formule.

  Les deux sont désormais remplacés. Seul ce qui se trouve entre
  guillemets est touché : les références de cellule, noms de fonction et
  noms de feuille ne sont pas affectés, `=SUMME(K2:K6)` continue de
  calculer. Comme le même nom reçoit partout le même espace réservé,
  `=SUMMEWENN(A:A;"Huber";B:B)` retrouve aussi ses lignes.

- **Les diagrammes n'affichent plus de noms.** Un diagramme enregistre
  une copie propre de ses libellés d'axe – il continue de les dessiner
  même quand les cellules source sont vides depuis longtemps. Sous les
  barres restaient donc cinq noms de personne alors que le tableau
  au-dessus était propre. Vaut pour les tableurs **et** les
  présentations.

- **Les plages nommées avec texte fixe sont nettoyées.** Une plage
  nommée peut contenir un texte fixe au lieu d'une référence de
  cellule ; si un nom s'y trouvait, il restait. Le **nom** de la plage
  reste toujours en place – des formules y font référence, et un
  renommage donnerait une erreur de référence. Comme pour le nom de
  feuille, il est signalé, pas remplacé.

- **Une date de naissance reconnue une fois disparaît dans tout le
  document.** Une date seule ne dit rien – seul un mot de champ en fait
  une date de naissance, et c'est justement pour cela qu'une date de
  facture reste tranquille. Mais si la même donnée figurait une seconde
  fois dans le même document sans ce mot – dans le titre d'une image,
  dans un champ de formulaire rempli –, elle y restait, bien que
  quelques lignes au-dessus « geboren am … » ait été reconnu sans
  ambiguïté. Seul ce qui a déjà été reconnu comme date de naissance dans
  **ce** document est transmis ; rien n'est jamais deviné.

- **Les données structurées dans les pages web révèlent leur date de
  naissance.** Dans le bloc JSON-LD pour les moteurs de recherche, la
  date se trouve sous la clé `birthDate` – la clé indique ce que c'est,
  comme le fait sinon l'en-tête de colonne. Elle est désormais lue
  aussi ; « Birthday » et « Birthdate » comptent ainsi aussi dans les
  formulaires comme désignation de champ.

- **Date de naissance et numéro de personnel sont désormais trouvés
  aussi dans les tableaux.** Dans une cellule ne se trouve que la valeur
  nue – `14.03.1988`. Ce qu'elle signifie n'est dit que par l'en-tête de
  colonne, qui se trouve plusieurs lignes plus haut. Dans Excel, elle
  était déjà lue ; dans les tableaux LibreOffice et dans les fichiers
  CSV non, et la date de naissance y restait donc en place.

  Les deux lisent désormais aussi l'en-tête – **mais seulement si
  celui-ci est lui-même une désignation de champ**. Sous « Geburtsdatum »
  la date tombe, sous « Rechnungsdatum » ou « Lieferdatum » non. C'est
  délibérément l'interprétation prudente : un en-tête comme « Name »
  au-dessus d'une remarque quelconque aurait sinon déjà posé un espace
  réservé sur une phrase où ne figure aucune personne.

### Corrigé

- **Un CSV nettoyé reste un tableau.** La détection lit une ligne CSV
  comme une phrase et posait donc parfois ses résultats au-delà d'un
  point-virgule. L'espace réservé avalait le séparateur, la ligne avait
  ensuite une colonne de moins, et le fichier ne pouvait plus être
  ouvert comme tableau. Les emplacements trouvés s'arrêtent désormais à
  la limite de la cellule, et les guillemets de mise entre échappement
  restent en place. Les cellules concernées sont ensuite relues
  séparément – sinon la cellule voisine resterait non nettoyée, celle
  que le résultat trop long avait masquée.

- **Commentaires dans les présentations.** La remarque en marge d'une
  diapositive – souvent exactement l'endroit où figure « Bitte Frau …
  vor der Sitzung anrufen » – restait intacte, avec le nom de son
  auteur. Dans Excel, les deux étaient déjà nettoyés depuis longtemps ;
  PowerPoint dépose le texte du commentaire et son auteur autrement,
  et cela avait été manqué. Concerne les deux formes : l'ancienne et
  celle que PowerPoint écrit depuis 2019 – là aussi l'adresse e-mail
  professionnelle attachée à l'auteur. Les initiales que PowerPoint
  affiche sur la bulle sont également supprimées.

- **Fichiers LibreOffice : formule, champ utilisateur, auteur de
  note.** Ce qui était déjà nettoyé dans Excel restait en place dans le
  tableau ODS – là, la formule ne figure pas comme élément propre, mais
  comme propriété de la cellule, et le nom qu'elle contenait
  survivait. À la prochaine ouverture, LibreOffice le recalculait.

  À cela s'ajoutent trois autres emplacements : la valeur d'un
  **champ utilisateur** se trouve dans OpenDocument une fois en haut
  dans la déclaration et n'est appelée que dans le texte – jusqu'ici,
  seul l'appel était remplacé, si bien qu'à l'ouverture l'ancienne
  valeur revenait. L'**auteur d'une note** et d'une modification suivie
  restait en place. Et dans un **tableau**, le suivi des modifications
  n'était pas du tout nettoyé – contrairement au document texte –, si
  bien que des contenus de cellule supprimés restaient conservés avec
  le nom de l'éditeur. Les références de cellule et les formules de
  somme ne sont pas touchées.

- **Les pages web enregistrées révèlent leurs attributs.** Une page ne
  montre de loin pas tout ce qu'elle contient. Un champ de formulaire
  rempli porte la saisie dans `value`, une interface JavaScript dépose
  ses données dans `data-…`, et le bloc pour les moteurs de recherche
  (JSON-LD) le répète entièrement et proprement : nom, date de
  naissance, adresse, téléphone. Le texte visible était nettoyé, tout
  cela restait présent.

  Ces emplacements sont désormais aussi nettoyés, ainsi que `aria-…`
  (ce qui est lu par le lecteur d'écran), `placeholder`, `summary` et le
  nom de fichier proposé d'un lien. Le bloc JSON-LD est lu comme des
  données et reste valide – ses clés et son vocabulaire restent, seules
  les valeurs disparaissent. Le JavaScript ordinaire n'est toujours pas
  touché.

- **Les images perdent leurs métadonnées même sans EXIF.** Une photo
  porte le nom du photographe, l'heure de prise de vue et les
  coordonnées GPS du lieu de prise de vue écrits à côté – pour une
  annonce de logement, cela révèle l'adresse, même si aucune ne figure
  dans le texte. Cela était supprimé tant que l'image avait des
  données EXIF. Mais si les indications n'étaient déposées **que** sous
  forme XMP (ainsi enregistrent Lightroom et Photoshop) ou comme bloc de
  texte dans un PNG (`Author`, `Comment`), l'image restait entièrement
  intacte. Les deux sont désormais détectées et supprimées – même pour
  les images intégrées dans un document et conservées à l'intérieur.
  L'orientation continue de survivre, et une image sans métadonnées
  n'est pas réenregistrée inutilement.

- **Cibles de liens dans les tableurs, présentations et documents
  Word.** Où mène un lien ne figure pas dans le texte, mais dans un
  emplacement propre du fichier. Une adresse e-mail derrière « Écrire un
  mail » survivait donc intacte au nettoyage, alors que la même adresse
  était remplacée dans le texte. `mailto:` et `tel:` y sont désormais
  nettoyés comme dans les pages web enregistrées.

### Nouveau

- **Les lettres de médecin ne reviennent plus endommagées.** Jusqu'ici,
  la détection de noms prenait des principes actifs pour des noms de
  personne : de « Metoprololsuccinat » résultait `[NAME]`, de
  « Ramipril » résultait `[ORT]`. Le plan de médication en devenait
  inutilisable – alors que les diagnostics restaient intacts, donc
  exactement à l'envers. Mesuré, cela touchait **63 % des principes
  actifs** et **53 % des termes techniques cliniques**, et pas
  seulement en allemand : sur sept langues 74 %, en italien tous les cas
  vérifiés.

  Maskuro connaît désormais le vocabulaire médical et le laisse
  tranquille. Il reste 6 % au lieu de 43 % (allemand) et 1 % au lieu de
  74 % (toutes langues confondues). Là où une formule d'appel précède
  – « Sehr geehrte Frau … » –, le nom reste un nom, même s'il ressemble
  par hasard à un principe actif.

- **Maladies et médicaments peuvent être supprimés – si vous le
  voulez.** Nouvelle case dans les paramètres : « Supprimer aussi
  maladies et médicaments » (ligne de commande : `--mit-diagnosen`).
  Pour les dossiers du personnel, licenciements et expertises, où le
  diagnostic ne regarde personne.

  **Désactivé par défaut**, et ce délibérément : une lettre de médecin
  *se compose* de diagnostics et de principes actifs. Qui l'anonymise –
  pour la recherche, pour une formation, pour un outil d'IA – veut le
  plus souvent conserver exactement ce contenu et seulement se
  débarrasser de la personne concernée. Le diagnostic y est le
  contenu utile, pas l'identifiant.

  La détection trouve les désignations courantes et ne remplace pas la
  relecture : une liste de maladies n'est jamais complète, car le
  médecin écrit « C2-Abusus » là où la classification indique
  « troubles liés à l'alcool ».

- **Les codes de diagnostic et de médicament sont trouvés.** ICD-10
  (`I48.2`), ATC (`A10BA02`) et le numéro pharmaceutique central sont
  des données de santé comme n'importe quel diagnostic écrit en toutes
  lettres – dans les lettres de sortie et documents de facturation,
  c'est même la forme la plus fréquente. Ils sont activés par défaut,
  comme les autres catégories particulières selon l'art. 9 du RGPD.

  Un code de diagnostic n'est reconnu qu'avec justification : avec
  « ICD » devant ou entre parenthèses derrière la ligne de diagnostic.
  Sans cette condition, le programme prendrait la touche de fonction
  **F10** pour un diagnostic d'addiction – dans la classification, F10
  désigne exactement cela.

- **Le fichier terminé peut désormais être copié.** Sur chaque ligne
  terminée figure, à côté de « Voir », « Retoucher » et « Afficher dans
  le dossier », un quatrième bouton : **Copier**. Il dépose le fichier
  nettoyé dans le presse-papiers – de là, il passe avec Ctrl+V (Mac :
  ⌘V) dans un mail, une fenêtre de chat ou un outil d'IA, sans détour
  par le dossier.

  C'est le **fichier** qui est copié, pas son texte : mise en page,
  images et barres de caviardage sont ainsi conservées. Via le menu
  contextuel de la liste, plusieurs résultats sélectionnés passent aussi
  d'un coup dans le presse-papiers, et dans le menu « Fichier » figure le
  même chemin sous **« Copier le résultat »** pour tous ceux qui
  préfèrent le clavier.

- **Le choix du pays peut désormais suivre le document.** Les numéros de
  carte d'identité, de sécurité sociale et fiscaux diffèrent d'un pays à
  l'autre, et quels pays sont vérifiés était jusqu'ici fixé pour toute
  la session – déduit de la langue de l'interface. Qui travaille en
  allemand et nettoie une lettre française y cherchait donc des
  numéros fiscaux allemands et non le numéro de sécurité sociale
  français.

  Dans la fenêtre des règles figure désormais pour cela
  **« Automatiquement selon la langue du document »**. Le choix fixe
  reste disponible à côté, et ce délibérément : la détection de langue
  n'est pas infaillible – si elle se trompe, c'est le mauvais choix de
  pays qui s'applique. Qui ne traite que des dossiers d'un seul pays est
  plus en sécurité avec la liste fixe.

  Non affectés par cela restent les modèles **allemands** (numéro
  fiscal, immatriculation, poste) : ils dépendent de la langue, pas du
  choix de pays, et s'appliquent même quand un texte allemand court est
  classé comme anglais.

- **Mots de passe, clés et noms de connexion sont désormais trouvés.**
  Qui colle un message d'erreur, un journal ou un extrait d'un fichier
  de configuration dans une fenêtre d'IA y a presque toujours une clé
  d'accès – et elle restait jusqu'ici inchangée.

  Les deux formes sont reconnues : les formes de clé courantes qui
  parlent d'elles-mêmes (`sk-…`, `ghp_…`, `AKIA…`, `AIza…`, `xoxb-…`,
  JSON Web Token, l'en-tête d'une clé privée), et la forme libellée –
  « Passwort: », « API-Key = », « Token: », « Benutzername: ». Seule la
  valeur est remplacée, jamais le libellé : « Passwort: [ZUGANGSDATEN_1] »
  reste lisible, et qui vérifie le résultat voit qu'un mot de passe s'y
  trouvait.

  Nom de connexion et mot de passe sont deux types séparés. Qui veut
  seulement supprimer les mots de passe désactive l'un et garde l'autre.

- **Les codes à barres et QR dans les images sont rendus
  méconnaissables.** Sur un avis scanné se trouve presque toujours un
  code, et il contient le numéro de dossier – le même numéro qui est
  supprimé dans le texte à côté. Jusqu'ici, la version lisible par
  machine restait en place : la barre sur le numéro ne sert à rien si,
  deux centimètres plus loin, un appareil le lit en une seconde.

  Sont reconnus le QR code, Data Matrix, Aztec, Code 128, EAN et les
  autres formes courantes. Méconnaissable signifie pixelisé, et de
  façon plus grossière que pour les visages : la correction d'erreur
  d'un code récupère étonnamment beaucoup à partir de peu de champs
  conservés, un voile timide ne serait pas une suppression.

  L'option se trouve à côté de « Rendre les visages méconnaissables »
  et est tout aussi **activée par défaut**. Même avec l'option
  désactivée, le rapport indique combien d'images portent un code – on
  voit un visage en feuilletant, on prend un code pour un accessoire.

- **Le numéro de sécurité de carte, le code PIN et la date
  d'expiration sont trouvés.** Le programme trouvait déjà le numéro de
  carte de crédit ; ce n'est qu'avec les trois indications à côté
  qu'elle est utilisable, et sur chaque relevé elles figurent
  ensemble. Les trois seulement derrière leur libellé – « 123 » seul
  est un numéro de maison, un numéro de page ou une quantité.

- **Les coordonnées dans le texte sont trouvées.** Maskuro supprimait
  déjà le lieu de prise de vue des images ; si la même indication
  figurait comme texte dans l'expertise ou le rapport d'intervention,
  elle restait en place. Sont reconnus le degré décimal et l'écriture
  degrés-minutes-secondes. Pour le degré décimal, un mot comme
  « Standort », « Fundort » ou « Koordinaten » doit se trouver à
  proximité – sinon toute série de mesures avec deux décimales serait
  une indication de lieu.

- **Les montants d'argent peuvent désormais aussi être supprimés.**
  Nouvelle case « Supprimer aussi les montants d'argent », désactivée
  **par défaut** comme les dates au-dessus : dans un contrat, le
  montant est le contenu, et qui caviarde tout ne protège personne.
  Dans une fiche de paie, une proposition de transaction ou un relevé de
  compte, c'est en revanche exactement l'indication qui en dit plus sur
  la personne que le nom à côté – ce que seul sait celui qui a le
  document sous les yeux.

  Un montant n'est reconnu **qu'avec indication de devise** :
  « 4.250,00 » seul est une quantité, ce n'est qu'avec
  « 4.250,00 EUR » que c'est de l'argent. Le symbole de devise, le
  sigle et le nom écrit en toutes lettres comptent, devant comme
  derrière, y compris l'écriture « 990,– CHF ».

- **Les catégories particulières selon l'art. 9 du RGPD sont
  reconnues.** Appartenance religieuse, appartenance syndicale,
  conviction politique, indications de santé – et à côté les
  indications de droit pénal selon l'art. 10. Ce sont les données dont
  le traitement est en principe **interdit** par le règlement ; elles
  sont donc le seul nouveau groupe activé **par défaut**. Qui veut les
  conserver en décide.

  Est reconnue la forme sous laquelle elles figurent en pratique : le
  champ de formulaire sur la fiche du personnel – « Religionsbekenntnis:
  röm.-kath. », « Gewerkschaft: ÖGB », « Grad der Behinderung: 50 »,
  « Vorstrafen: keine » –, aussi bien avec un deux-points à côté qu'avec
  le libellé au-dessus, comme le fournit une fiche remplie.

  **Le texte continu appartient au niveau IA.** « Il s'engage depuis des
  années dans le syndicat » est la même donnée, et aucun modèle de
  recherche ne la trouve de façon fiable. Le niveau IA recherche depuis
  cette version aussi explicitement ces catégories ; qui a besoin du
  texte continu l'active.

- **Caractéristiques personnelles et profession – les indications qui
  montrent qui est visé même sans nom.** Sexe, état civil, taille,
  couleur des yeux et des cheveux sont supprimés à partir de cette
  version ; profession, fonction et service sur demande, via une case
  propre (« Supprimer aussi profession et service ») ou
  `--mit-berufen`.

  **Pourquoi l'un est activé et l'autre non :** « La responsable du
  service Achats » désigne dans une entreprise exactement une personne,
  même si le nom à côté est caviardé – dans une expertise ou un
  licenciement, cela doit être supprimé. Un annuaire du personnel se
  *compose* en revanche de désignations de fonction ; qui les
  supprimerait par défaut rendrait une feuille vide. Quel cas s'applique,
  seul le sait celui qui a le document sous les yeux. Les
  caractéristiques ci-dessus se trouvent presque uniquement dans des
  champs de formulaire, sont rares et ne portent jamais le contenu –
  elles ne coûtent donc rien.

- **Vérifier un fichier étranger.** « Fichier → Vérifier un fichier … »
  relit un document déjà caviardé et signale ce qui s'y trouve
  encore – et **à quel endroit** : page et ligne, type et longueur.
  Pour le cas où quelqu'un vérifie le travail d'un autre : un dossier du
  cabinet, une information de l'administration, son propre courrier
  sortant avant l'envoi.

  **La valeur elle-même ne figure pas dans le rapport.** Qui ouvre
  l'emplacement la voit de toute façon – et le rapport peut donc être
  enregistré et transmis sans être lui-même une collecte de données
  personnelles.

  **Et le rapport dit dans tous les cas ce qu'il n'a pas pu voir.** Les
  images ne sont pas lues ; pour un scan sans couche de texte,
  « aucun emplacement trouvé » signifie *non vérifié*, pas *propre*. En
  ligne de commande, la valeur de retour distingue cela :
  `--nachpruefen` renvoie 0 pour vérifié et propre, 4 pour des
  emplacements trouvés et 5 pour non vérifiable. Cela permet de
  retenir automatiquement le courrier sortant, au lieu de le laisser
  passer.

- **Rapport de vérification : une feuille par nettoyage.** « Fichier →
  Enregistrer un rapport de vérification … » – ou `--pruefbericht
  <dossier>` en ligne de commande – écrit un PDF d'une page (au choix
  CSV ou texte) avec les indications sur le passage, les types trouvés
  avec leur nombre, deux indicateurs et une mention de vérification.
  Pour le classeur et pour l'autorité de contrôle : le journal de
  vérification est la preuve solide, mais personne ne présente un
  fichier JSON Lines.

  **Deux chiffres sont nouveaux**, invisibles jusqu'ici : la
  *confiance moyenne* – la certitude de la détection sur ce qu'elle a
  trouvé – et le *taux de masquage*, la part de caractères remplacés
  dans le texte. Les deux figurent avec leur limite : la confiance ne
  dit **rien** sur ce qui a été manqué, et à côté d'elle figure toujours
  sur combien de résultats elle porte ; le taux ne compte pas les
  images et est trop élevé pour un document illustré.

  **Les valeurs trouvées ne figurent pas sur la feuille** – même limite
  que pour le journal et pour la recherche. En bas figurent deux lignes
  qui ne disent pas la même chose : la somme de contrôle montre que la
  feuille est inchangée ; la ligne de journal – seulement si le journal
  fonctionne – renvoie à la ligne **signée** qui atteste le passage.
  Seule elle prouve la provenance.

- **« Quelle était la certitude ? » – les indicateurs sur le
  résultat.** Un bouton « Indicateurs » sous le résultat déplie ce qui
  n'était visible nulle part jusqu'ici : emplacements trouvés, mots et
  caractères, la répartition par type en ligne de barres, ainsi que la
  confiance moyenne et le taux de masquage. Les mêmes chiffres que dans
  le rapport de vérification, mais immédiatement et sans impression.

  **Avec sa réserve dans la même zone :** à côté de la confiance figure
  sur combien de résultats elle porte, et en dessous la phrase qu'elle
  ne dit **rien** sur ce qui a été manqué. Un pourcentage sans cette
  phrase se lit comme un taux de réussite – et qui le comprend ainsi
  est moins bien loti que sans le chiffre.

  Le calcul n'a lieu qu'au dépliement : le dénominateur du taux de
  masquage coûte une lecture par fichier, et cela ne doit pas être payé
  par qui ne regarde même pas les chiffres.

- **Construire des modèles de recherche personnalisés sans en écrire
  un.** L'onglet « Modèles de recherche personnalisés » guide désormais
  en trois étapes : *Que cherchez-vous ? → À quoi ressemble une telle
  donnée chez vous ? → Nommer et enregistrer.* Vous tapez un exemple –
  par exemple `KD-004711` –, le programme en déduit la règle et écrit
  en mots ce qu'elle recherche. Un aperçu avec compteur de résultats
  vérifie à chaque frappe.

  **Aucune expression régulière n'y intervient.** La capacité n'a
  jamais été le problème : les modèles de recherche personnalisés
  existent depuis longtemps, mais exigeaient une expression comme
  `\bKD-\d{6}\b`, et personne dans un cabinet ou un service du
  personnel n'en écrit une. Qui *veut* en écrire une déplie le mode
  expert.

  **Le catalogue de modèles est réorganisé :** treize fiches avec nom,
  explication et valeur d'exemple, filtrées par étiquettes de
  catégorie – Finances, Administrations, Contact, Personnel, Médecine.

  Et si le modèle déduit saisit trop large, le programme le dit de
  lui-même : un exemple composé uniquement de chiffres touche chaque
  année et chaque montant, et qui ne peut pas lire l'expression ne
  pourrait sinon pas le remarquer.

- **Sept étiquettes au lieu de cinquante-six cases.** Un nouvel onglet
  « Ce qui est recherché » regroupe tous les types détectables en sept
  groupes – Personne, Contact et lieu, Identifiants, Finances,
  Technique, Catégories particulières, Entreprises et Personnalisé. Une
  étiquette active son groupe, « Tout activer » et « Tout désactiver »
  la liste entière ; en dessous, chaque type reste cochable
  individuellement.

  **Tout est activé par défaut, et cela reste ainsi.** Ce qui est
  désactivé ici n'est même plus recherché – l'intervention la plus
  radicale que la fenêtre des règles permette, et elle agit sur chaque
  document. C'est pourquoi il est indiqué en permanence sous la liste
  combien de types sont désactivés, et seul ce qui est désactivé est
  enregistré : un nouveau type est ainsi activé même dans un fichier de
  règles d'avant-hier, au lieu de disparaître silencieusement.

- **Transférer un cadre à toutes les pages.** Dans la fenêtre de
  retouche, le bouton **Transférer à toutes les pages** prend le
  dernier cadre tracé et caviarde le même emplacement sur chaque autre
  page – pour l'en-tête de lettre, le pied de page et le champ de
  numéro de dossier. Pour un dossier scanné de quatre-vingts pages,
  cela transforme vingt minutes en deux.

  **« Le même emplacement » signifie la même position *relative* sur la
  feuille.** Dans une pile issue du bac, une page se trouve
  régulièrement en travers, une autre est en A3, une troisième est
  tournée ; un rectangle transféré de façon absolue atterrirait à côté
  de l'en-tête de lettre – et l'on verrait une barre et croirait
  l'affaire réglée.

  **Le résultat est caviardé, pas remplacé**, même si le cadre de
  départ était un espace réservé : sous le même rectangle se trouve à
  la page quarante quelque chose de différent qu'à la page un, et un
  espace réservé avec le même numéro affirmerait une égalité qui
  n'existe pas.

- **Une mention sur la barre de caviardage.** Dans le droit de
  consultation du dossier, chaque caviardage est accompagné de la
  raison du caviardage. Le nouveau champ **Mention sur la barre** dans
  les paramètres – ou `--balkenvermerk` – écrit un court texte sur
  chaque barre : « § 203 StGB », « RGPD », « confidentiel ». Pour un
  document remis par une administration, c'est la différence : le
  destinataire voit la raison sans disposer d'un journal qu'il
  n'obtient de toute façon jamais.

  **Vide par défaut**, car la mention est visible dans le document remis
  et est elle-même une donnée – elle indique au destinataire sous quel
  motif quelque chose est retenu. Elle n'agit que pour le
  **caviardage** ; là où se trouve un espace réservé, il n'y a pas de
  barre. Sur une barre trop petite pour un texte lisible, elle est
  omise – une mention illisible ressemblerait à une erreur.

- **Activation sans connexion internet – désormais complète.** Dans la
  fenêtre de licence, il existait depuis longtemps « Activer sans
  internet » : en haut un code de demande à emporter, en bas le champ
  pour l'activation qui revient. Seulement, jusqu'ici, **personne ne
  pouvait l'établir** – l'outil manquait, et le code tombait dans le
  vide. C'est corrigé.

  Pour les administrations et cabinets avec ordinateurs isolés, ce n'est
  pas un cas particulier mais le cas normal – et c'est exactement le
  groupe cible pour lequel la promesse « vos documents ne quittent
  jamais l'ordinateur » pèse le plus lourd. Le code ne révèle rien sur
  les documents : il contient l'identifiant de licence et une valeur de
  hachage de l'ordinateur, rien de plus.

- **Récupérer depuis le scanner.** « Fichier → Récupérer depuis le
  scanner … » lit directement une pile et dépose les pages dans la
  liste – pour un service courrier, la différence entre deux étapes de
  travail et une seule. Un bac d'alimentation est vidé jusqu'à la
  dernière page ; l'appareil, la résolution et la couleur sont choisis
  par la boîte de dialogue système du scanner, que vous connaissez déjà.

  **Le nettoyage ne se fait pas automatiquement.** Vous voyez d'abord ce
  qui est arrivé, puis appuyez sur « Nettoyer » comme pour tout autre
  fichier – un scan qui passerait immédiatement vous ôterait la vue sur
  une pile insérée de travers.

  **Cela n'existe que sous Windows**, et l'entrée de menu le dit aussi
  sur le Mac : là, le logiciel de votre scanner écrit dans un dossier,
  et « Surveiller un dossier … » nettoie tout ce qui y atterrit.

### Divers

- **La liste de toutes les données trouvées est désormais jointe** et
  générée à partir du code source (`hilfe/GEFUNDENE-ANGABEN.md`) : 177
  types dans 35 pays, dont 23 avec calcul de chiffre de contrôle. Elle
  indique aussi comment le comptage a été fait – nous comptons
  `[NAME]` une fois, là où d'autres comptent prénom, deuxième prénom et
  nom de famille comme trois entrées.

- **Le caviardage existe désormais aussi dans Word, PowerPoint,
  OpenDocument et HTML.** Le choix entre espace réservé et caviardage
  n'existait jusqu'ici que pour les fichiers PDF. Les autres le peuvent
  désormais aussi : le résultat est supprimé, et une barre noire se
  trouve à sa place – dans le document lui-même, pas comme image
  par-dessus. Qui transmet le fichier transmet un dossier caviardé et
  non un dossier où le caviardé se trouve encore comme texte en
  dessous.

  **La décision se prend séparément**, dans deux champs de choix :
  « Pour le PDF » et « Pour Word, PowerPoint, OpenDocument et HTML ». On
  le veut différemment – le PDF caviardé va à l'administration, la
  même chose en fichier Word circule dans l'entreprise et doit rester
  lisible. En ligne de commande, correspondant `--pdf-modus` et
  `--office-modus` ; un « Caviarder » enregistré de versions antérieures
  continue de s'appliquer au PDF.

  Dans les tableurs, le texte brut, le CSV et l'e-mail, la barre ne
  fonctionne pas – il y manque la surface sur laquelle elle pourrait se
  poser. Un espace réservé continue d'y être inséré, et le résultat
  **le dit désormais**, au lieu de le faire silencieusement.

- **Nouveau : « Supprimer » – l'emplacement trouvé reste simplement
  vide.** Le troisième mode de fonctionnement à côté d'espace réservé et
  caviardage, et le seul qui fonctionne pour **chaque** format : omettre
  quelque chose ne nécessite pas de surface. Dans le PDF, rien n'est
  dessiné ; dans Word et HTML, l'emplacement reste vide, dans un tableau
  de même.

  C'est le plus discret des trois : qui lit le résultat ne voit pas
  qu'il y avait quelque chose autrefois – même la longueur de la valeur
  ne se trahit plus. Pour un document destiné à être vérifié, l'espace
  réservé reste le plus souvent le meilleur choix.

  Dans les images, aucun des trois choix ne s'applique : les pixels ne
  peuvent être ni remplacés par un espace réservé, ni omis. Ce que la
  reconnaissance de texte y trouve continue toujours d'être recouvert.

- **La fenêtre de retouche n'affirme plus des remplacements qui
  n'existent pas.** À droite figurait un espace réservé pour chaque
  valeur – même pour un fichier caviardé où aucun n'apparaît. Un clic
  sur une telle ligne ne marquait rien, et « Annuler » tombait dans le
  vide. Il y figure désormais « caviardé » ou « supprimé », et ces
  lignes ne peuvent même plus être annulées : le texte a disparu, il n'y
  a rien à récupérer. Cela valait pour les fichiers PDF caviardés, pour
  Word et OpenDocument et pour tout ce qui a été trouvé dans des
  images.

- **La vue texte affiche désormais les barres comme des barres.** Un
  fichier Word caviardé avait l'air **vide** lors de la retouche : aux
  emplacements caviardés se trouvaient des vides, comme si le programme
  avait avalé le texte. La cause était l'affichage, pas le résultat –
  dans le document lui-même, la barre était correcte depuis le début.
  Elle figure désormais aussi dans la vue à cet endroit, noire comme
  dans le résultat, dans Word, PowerPoint, OpenDocument et HTML.

- **Les messages Outlook (`.msg`) sont désormais nettoyés.** Le
  `.eml` existait depuis longtemps – mais dans les entreprises
  allemandes, Outlook est l'e-mail, et un message enregistré s'y
  appelle `.msg`. Le format le plus dense en données personnelles est
  ainsi couvert aussi dans sa forme de dépôt la plus répandue : objet,
  expéditeur, lignes de destinataire, texte du message, version HTML,
  liste de destinataires et pièces jointes – ces dernières via les
  chemins existants et avec les mêmes espaces réservés que le texte du
  mail.

  **Un `.msg` porte le même texte plusieurs fois**, et c'est le piège :
  en texte brut, en HTML **et** en RTF. Qui ne nettoie que le texte
  brut n'a rien fait – Outlook affiche préférentiellement le RTF. La
  version RTF est donc entièrement supprimée, de même que les en-têtes
  internet avec leur chaîne Received et les clés de recherche binaires
  qui survivent à tout nettoyage de texte, noms et adresses compris. Le
  résultat s'ouvre toujours dans Outlook et affiche le texte sans mise
  en forme ; le rapport le dit explicitement.

- **Décrire des règles avec ses propres mots au lieu d'écrire une
  regex.** La fenêtre des règles peut beaucoup et exigeait pour cela un
  modèle d'expression régulière – l'endroit où la plupart des gens
  s'arrêtent. Une phrase suffit désormais : « Nos numéros de dossier de
  la forme 12 C 345/26 doivent rester. » Le niveau IA en déduit des
  termes et modèles de recherche.

  **Seul ce que vous cochez est repris – et rien n'est coché par
  défaut.** Chaque suggestion est accompagnée d'une phrase expliquant
  ce qu'elle signifie, et du nombre de ses résultats dans un texte
  d'exemple que vous pouvez fournir. Ce qui **retire** de la
  protection est signalé comme tel : « toujours supprimer ce terme » et
  « ne jamais supprimer ce terme » se ressembleraient sinon dans une
  liste. Les suggestions qui correspondraient à tout ne sont même pas
  affichées.

- **Le journal de vérification compte désormais toutes les postes de
  travail ensemble.** Si une entreprise dépose les journaux via
  `protokoll_pfad` sur un partage, chaque poste y écrit son propre
  fichier mensuel – jusqu'ici, un délégué à la protection des données
  avec trente postes devait examiner trente fichiers un par un.
  Au-dessus de la liste figure désormais une ligne avec les sommes du
  mois, et **elle signale les chaînes rompues avec des noms** : une
  modification a posteriori ne se remarque que si quelqu'un vérifie, et
  dans trente fichiers, personne ne vérifie à la main.

  **Aucun relevé par personne** – pas même dans cette vue. Un
  classement « qui a nettoyé combien » se prêterait au contrôle du
  comportement et de la performance, et c'est ce qui compte au regard
  du droit de codétermination, pas l'intention. Sont comptés les
  passages, fichiers et résultats à l'échelle de l'entreprise.

- **« Proposer un profil à partir d'un document » : interroger les
  règles une fois au lieu de parcourir quarante-quatre types.** La
  fenêtre des règles dispose d'un nouveau bouton : il montre un document
  au niveau IA, détermine de quoi il s'agit – lettre de médecin,
  candidature, contrat, facture, avis – et propose les stratégies
  adaptées. Pour la lettre de médecin par exemple, les dates sont
  décalées plutôt que remplacées, car dans un dossier médical la
  chronologie est le contenu.

  **Les profils se trouvent dans le programme, le modèle ne fait que
  choisir** – les règles de caviardage ne dépendent pas de ce qu'un
  modèle de langage estime être une bonne idée. Chaque point est
  proposé individuellement et avec justification ; rien n'est repris
  sans confirmation, et ce que vous avez défini vous-même reste
  intact. Sans niveau IA, on en reste au réglage sûr : espace réservé
  pour tout.

- **Nouvelle stratégie « inventer » : une fausse valeur plausible au
  lieu d'un espace réservé.** « Frau Berger schrieb an Herrn Doppler in
  Fulda » au lieu de « [NAME_1] schrieb an [NAME_2] in [ORT_1] » –
  pour les supports de formation, dossiers de démonstration, jeux de
  données de test et tout ce qui est ensuite soumis à une IA. Formule
  d'appel, construction de phrase et lisibilité sont conservées.

  La même valeur reçoit la même fausse valeur, sur tous les fichiers
  d'un dossier et sur chaque ordinateur avec le même fichier de règles
  – **sans qu'une affectation ne soit enregistrée nulle part** (le même
  mécanisme que pour le hachage). Les adresses e-mail se trouvent sur
  des domaines d'exemple réservés, les numéros de téléphone dans la
  plage réservée à cet effet, les IBAN inventés portent un chiffre de
  contrôle correctement calculé. Possible pour noms, lieux, adresses,
  entreprises, e-mail, téléphone et IBAN ; pour les autres types, la
  règle est refusée plutôt que de rester sans effet.

  **Le rapport indique explicitement qu'il y a eu invention.** Un
  document ainsi nettoyé se lit comme un vrai et n'en est pas un – il
  ne vaut pas comme preuve et ne doit pas être transmis comme
  original.

- **La contre-vérification : « Qui reste identifiable ? »** Une nouvelle
  case sous le niveau IA soumet à nouveau le **résultat terminé** au
  modèle de langage et demande qui reste identifiable malgré le
  nettoyage. Est visé le cas qu'aucune détection au monde ne trouve,
  parce qu'aucun nom ne s'y trouve : « la seule sage-femme du
  district », « le collègue qui a démissionné en mars après
  l'incendie ». Aucun modèle ne saisit cela, et sur place tout le monde
  sait pourtant de qui il s'agit.

  **Rien n'est supprimé pour autant.** Les emplacements figurent avec une
  phrase de justification dans le rapport, et la décision se prend à la
  main – un programme qui retirerait de lui-même des phrases d'un
  document parce qu'elles lui semblent révélatrices ferait d'un
  nettoyage une réécriture, et personne ne verrait ce qui manque. Cinq
  emplacements maximum par fichier ; ce que le modèle ne peut pas
  attester littéralement disparaît. En ligne de commande :
  `--restrisiko` avec `--ki`.

- **Le chemin retour depuis l'IA : « Retraduire la réponse ».** Jusqu'ici,
  seule la moitié de la boucle était construite – copier le texte,
  coller le résultat nettoyé, le soumettre à l'IA. La réponse revenait
  avec `[NAME_1]`, et qui en avait besoin réinsérait à la main ce qu'il
  avait retiré à la main. Le chemin retour se trouve désormais dans le
  menu « Programme » : copier la réponse, cliquer sur l'entrée, les
  vrais noms sont de retour.

  L'affectation pour cela se trouve **uniquement en mémoire vive**, ne
  vaut toujours que pour le dernier emplacement nettoyé et expire après
  une heure ; qui désactive le veilleur du presse-papiers s'en
  débarrasse immédiatement. Seul ce qui a été remplacé peut être
  récupéré ainsi – ce qui est caviardé, masqué et haché n'est pas
  réversible, et le programme indique combien d'emplacements il a donc
  dû laisser en l'état. Les installations gérées désactivent
  entièrement le chemin retour via la consigne `rueckweg`.

- **Surveiller un dossier : ce qui est déposé se retrouve peu après
  nettoyé dans la sortie.** Pour un service courrier, une équipe de
  boîte postale ou un dossier de scan – configuré une fois, plus
  personne ne clique ensuite. À trouver sous « Fichier → Surveiller un
  dossier … », en ligne de commande via `--wache <dossier>`.

  L'original reste où il était ; sur demande, il migre inchangé vers le
  sous-dossier « Terminé », sans jamais rien écraser. Un fichier n'est
  touché qu'une fois entièrement écrit – un fichier encore en cours de
  copie sur le réseau serait sinon lu à moitié et signalé comme
  nettoyé. Ce qui échoue reste en place et est signalé, au lieu d'être
  répété indéfiniment. Et la surveillance mémorise ce qui est terminé
  sans nom de fichier : ce qui se trouve dans un dossier d'entrée
  révèle souvent déjà dans son nom de quoi il s'agit.

  **La surveillance d'un dossier en dehors de son propre profil
  utilisateur – par exemple sur un lecteur réseau – nécessite une
  licence d'automatisation.** Un dossier accessible à plusieurs
  personnes est un service, pas un poste de travail ; dans son propre
  profil et pendant la période d'essai, cette restriction ne
  s'applique pas.

### Corrigé

- **Les paramètres étaient coupés à droite.** La fenêtre s'ouvrait avec
  une taille fixe, qui ne suffisait que pour la taille de police utilisée
  au développement : sur le Mac, « Vérifier maintenant », « Modifier … »
  et les indications à côté se trouvaient à moitié en dehors. Elle
  s'ouvre désormais aussi large que ses pages en ont besoin – dans
  chaque langue et à chaque taille de police, limitée seulement par
  l'écran.

- **« Vérifier maintenant » répond désormais visiblement.** Le résultat
  se trouvait dans la barre d'état de la fenêtre principale – donc
  derrière la fenêtre des paramètres, depuis laquelle on avait
  demandé. Qui vérifiait ne voyait rien. La réponse arrive désormais
  comme message au-dessus des paramètres, et si une nouvelle version
  est disponible, elle mène directement à l'installation. Au démarrage
  du programme, cela reste comme avant à la barre d'état, aucune
  fenêtre ne s'ouvre sans qu'on l'ait demandé.

- **Les fichiers copiés n'arrivaient pas dans le presse-papiers sur le
  Mac.** La remise de fichiers nettoyés dans le presse-papiers
  signalait un succès et ne déposait pourtant rien d'utilisable –
  coller ne donnait rien. Était concerné tout ce qui écrit des fichiers
  dans le presse-papiers.

- **Et depuis le presse-papiers, seul le premier fichier était lu sur le
  Mac.** Qui copiait trois fichiers dans le Finder et choisissait
  « Nettoyer le presse-papiers maintenant » en récupérait deux non
  nettoyés – sans que rien ne le signale. Tous arrivent désormais.

- **« Vérifier un fichier » accepte désormais aussi les fichiers
  glissés** – comme la fenêtre principale. Ce qui est déposé s'ajoute au
  lieu de rejeter la sélection précédente ; déposer deux fois la même
  chose ne change rien, et ce que le programme ne peut pas lire est
  signalé plutôt qu'avalé.

- **Et la fenêtre indique qu'elle attend de vous.** Elle s'ouvrait avec
  un cadre vide et un bouton gris « Vérifier » – cela ressemble à
  l'absence de contenu, pas à l'absence de sélection. Il y figure
  désormais « Aucun fichier sélectionné pour l'instant – glissez-le ici
  ou choisissez-le en bas via « Sélectionner des fichiers … ». »

- **Un long passage indique désormais qu'il est en cours.** « Chargement
  du modèle complémentaire pour la détection plus précise – un
  instant … » restait affiché tant que la détection calculait : pour un
  fichier de 47 500 mots, donc dix-huit minutes, alors que le
  chargement était terminé après neuf secondes. Qui voit cela pense que
  le programme est bloqué. Suit désormais « Détection plus précise en
  cours – cela prend quelques minutes pour les longs textes », et la
  barre d'état compte : « Détection plus précise (7/312) ». C'est
  signalé depuis la boucle du modèle – toutes les 250 mots, donc environ
  toutes les six secondes –, pas par bloc de texte : un bloc de texte
  porte douze mille mots et prend des minutes.

- **Un passage interrompu indique désormais qu'il a été interrompu.**
  Qui appuyait sur « Annuler » lisait ensuite « 0 sur 1 fichier(s)
  nettoyé(s). » – correctement compté et pourtant la mauvaise
  information. Le message indiquant quel fichier était concerné était
  écrasé au même instant par le message de comptage. Et dans la liste
  de fichiers figurait toujours « en cours … », bien que plus rien ne
  soit en cours ; il y figure désormais « interrompu ».

- **La phrase sur la protection des données était coupée.** « … pas de
  cloud, pas de téléversement. Plus dans la confidenti » – à la largeur
  de fenêtre avec laquelle le programme démarre, elle se terminait en
  plein milieu d'un mot. Elle prend désormais toute la largeur.

- **Le service de licence pouvait communiquer quelque chose, et personne
  n'écoutait.** Quand toutes les places de licence sont occupées, la
  licence a expiré, la clé est inconnue ou la gestion de licence est
  désactivée chez le fournisseur, le service envoie exactement pour
  cela une raison – il était prévu dès le début que vous receviez une
  explication **une fois**. Elle n'était jamais montrée. Une indication
  apparaît désormais, disant d'abord que le programme continue de
  fonctionner sans changement, puis de quoi il s'agit. Une fois par
  raison : qui l'a fermée ne la revoit pas lors de la vérification
  quotidienne – mais si, quand la raison change.

- **Une licence multi-postes achetée dans la boutique affichait
  « 1 place ».** La boutique distribue des clés préparées et conserve le
  nombre de places acheté de son côté ; mais le nombre affiché venait
  de la clé elle-même, qui indique une place pour chaque clé de stock.
  Qui avait acheté huit places lisait « 1 place » – et à partir du
  deuxième ordinateur enregistré, l'affichage passait en rouge avec
  « Veuillez contacter votre administration ». C'est désormais le
  nombre dernièrement signalé par le service qui s'applique ; sans
  réponse, on en reste à la clé, et cela ne descend jamais en dessous
  du volume acheté. Il en va de même pour les rachats et les
  prolongations : ils changent le nombre de places chez le
  fournisseur, pas votre clé.

- **Après l'achat figurait « Sous licence pour Maskuro Privatlizenz ».**
  Ce n'est pas un nom, mais l'espace réservé sous lequel les clés sont
  préparées – votre nom ne peut pas s'y trouver, car la clé est signée
  avant même l'achat. Au lieu de vous montrer un nom étranger comme le
  vôtre, il y figure désormais simplement « Licence privée » et le
  nombre de places. Pour une licence établie à votre nom, votre nom y
  figure sans changement.

- **Dans le menu Aide figurait « Aide _FAQ ».** Le signe « & » était
  devenu un trait de soulignement, car Qt le lisait comme marqueur d'un
  raccourci clavier. Il y figure désormais « Aide & FAQ ».

- **La fenêtre des paramètres restait affichée quand le programme
  disparaissait dans l'icône** – et même quand la fenêtre principale
  était fermée. Elle disparaît désormais avec. (Concerne seulement
  cette version ; sa propre fenêtre est nouvelle.)

- **Une demande de licence refusée indique désormais la raison.** Si le
  service de licence rejetait une demande sans en indiquer la raison,
  la fenêtre de licence affichait en rouge « Réponse inconnue. » – une
  phrase avec laquelle ni vous ni le support ne pouvez rien faire et
  qui vous fait chercher l'erreur du côté de votre clé. Il y figure
  désormais ce qui s'est réellement passé : que le service a refusé
  sans le justifier, et à qui vous adresser. Si la gestion de licence
  est temporairement désactivée chez le fournisseur, cela est également
  nommé – avec l'indication que votre clé n'en est pas affectée.

- **Sur le Mac, des langues configurées étaient soudain considérées
  comme manquantes.** Au démarrage, le programme signalait « Aucun
  modèle linguistique n'est installé » et proposait la configuration
  initiale, bien que les langues aient été chargées depuis longtemps –
  qui vérifiait sous « Langues des documents » les y trouvait au
  complet. Le programme les cherchait selon le chemin de démarrage à
  deux endroits différents : lancé depuis le dossier Programmes, il les
  trouvait ; la même construction lancée comme simple dossier, il les
  cherchait à côté de lui, où il n'y en a pas. Désormais, sur le Mac,
  s'applique sans exception le même emplacement dans le profil
  utilisateur, quelle que soit la façon dont le programme est empaqueté.
  Rien ne doit être rechargé.

- **« Quoi de neuf » n'affichait que la moitié de la liste.** La fenêtre
  après une mise à jour s'interrompait en plein milieu d'une phrase, et
  les points restants figuraient comme puces vides. La faute revenait à
  un espace réservé entre chevrons – par exemple `<datei>.docx` – que
  l'affichage prenait pour du balisage et à partir duquel tout le
  reste était rejeté. Justement les nouveautés de sécurité en étaient
  touchées. L'aide affiche de tels espaces réservés correctement depuis
  toujours ; cette fenêtre le fait désormais aussi.

- **Pincer avec deux doigts zoome désormais dans la fenêtre de
  retouche.** Sur le trackpad, c'est *le* geste de zoom – dans l'éditeur,
  il ne faisait jusqu'ici rien, et qui voulait examiner un emplacement
  de plus près devait recourir au curseur ou à Ctrl+molette. La page
  suit désormais le geste immédiatement et redevient nette au
  relâchement.

- **Le zoom se fait sur l'emplacement que l'on regarde.** Pincer agrandit
  autour du point entre les doigts, Ctrl+molette autour du point sous
  le curseur. Les boutons, raccourcis clavier et le curseur de zoom
  maintiennent le centre – aucun emplacement ne leur est associé sur
  lequel on pointe. Auparavant, seule la valeur de défilement restait
  fixe pour tous : depuis une page ajustée, cela maintenait le bord
  supérieur, et tout ce qui se trouvait en dessous sortait de l'image
  en zoomant.

- **« Avant/Après » était un bouton mort dans l'aperçu des pages.** Tant
  que l'aperçu des pages était actif, il pouvait être pressé – et
  signalait à chaque fois que l'original ne pouvait pas être ouvert. Il
  n'y a d'ailleurs rien à comparer là : l'aperçu des pages est une
  image de la version nettoyée, il n'existe pas de pendant à
  l'original. Le bouton est désormais verrouillé et indique au survol
  la raison ainsi que l'issue (la vue texte). Sa description promettait
  en outre explicitement que la comparaison fonctionnait
  « indépendamment du fait que la vue texte ou l'aperçu des pages soit
  actif » – ce qui n'a jamais été vrai.

- **L'aperçu des pages faisait planter LibreOffice.** Si deux aperçus de
  pages étaient générés simultanément – par exemple « Caviarder comme
  PDF » pendant que l'aperçu calculait encore –, le système signalait
  un plantage de LibreOffice, bien que les pages apparaissent finalement
  quand même : les deux passages accédaient au même espace de travail
  de LibreOffice, ce qu'il ne supporte pas. Un seul passage l'obtient
  désormais ; les autres passent sur un espace propre. Cela prend
  quelques secondes de plus, mais plus aucun message d'erreur
  n'apparaît, et aucun des passages ne reste sans résultat. Une
  deuxième tâche de rendu à côté d'une en cours n'est en outre même
  plus acceptée.

- **« Afficher l'original » pouvait terminer le programme.** Si
  l'original ne pouvait pas être ouvert – déplacé, renommé, protégé par
  un mot de passe ou sur un lecteur déconnecté –, la fenêtre de retouche
  s'arrêtait sans avertissement, et les copies de travail ouvertes
  étaient perdues. Une indication apparaît désormais, le commutateur
  revient en arrière, et la version nettoyée reste affichée. Là où
  l'original n'a fondamentalement pas sa place – par exemple pour un
  aperçu de page PDF issu d'un fichier Word –, le commutateur est
  verrouillé d'emblée et indique au survol la raison, au lieu d'afficher
  la même indication à chaque pression.

- **Les rapports d'erreur n'arrivaient jamais.** Qui voulait signaler
  une erreur obtenait « L'interlocuteur a refusé le rapport » – et
  personne ne l'avait jamais vu. Deux causes, toutes deux sur le
  chemin : le programme ne s'identifiait pas auprès du serveur et était
  donc rejeté par la protection contre les accès massifs, et l'adresse
  renvoyait à un second nom que le programme ne suivait pas. Les deux
  sont corrigées ; un rapport repart. **La même chose touchait
  l'activation de licence** : connexion, déconnexion et demande
  n'atteignaient pas non plus le service – là seulement discrètement,
  car une demande sans réponse ne change délibérément rien à votre
  licence. Et si un refus reste malgré tout inexpliqué, son numéro
  technique figure désormais à côté, au lieu que chaque cause se
  ressemble.

- **Un clic sur « Afficher l'original » pouvait terminer le programme.**
  Si l'original ne pouvait pas être ouvert – déplacé, renommé, sur un
  lecteur réseau déconnecté, protégé par un mot de passe ou endommagé
  –, la fenêtre de retouche disparaissait avec toutes les copies de
  travail ouvertes. Le commutateur reste désormais sur la version
  nettoyée, et un cadre indique ce qui se passe ; la raison technique
  figure dans les détails, si vous souhaitez la signaler. Il en va de
  même pour un résultat qui ne peut pas être affiché : la fenêtre
  s'ouvre et le dit, au lieu de disparaître.

- **La question sur un plantage arrivait trop souvent – et effaçait la
  trace sur laquelle elle portait.** Elle apparaissait aussi quand rien
  n'avait planté : la note est créée dès qu'une perturbation inattendue
  survient quelque part, même si le programme la surmonte et se ferme
  ensuite normalement ; elle n'était jamais nettoyée. Et qui répondait
  « Non » détruisait les seuls détails de l'incident – la note
  disparaissait déjà à l'*affichage* de la question. Les deux sont
  corrigés : une fin ordonnée nettoie la note, on ne demande plus qu'en
  cas de véritable arrêt, et la coche n'est posée qu'après votre
  réponse. Les détails figurent de toute façon dans le journal
  d'erreurs sur votre propre ordinateur – qui ne veut rien envoyer ne
  perd donc rien pour autant. N'est envoyé, comme toujours, que ce que
  vous avez vu entièrement au préalable et validé vous-même.

- **« Nettoyer » pouvait rester bloqué silencieusement.** Si les modèles
  linguistiques restaient bloqués au chargement, le bouton restait
  désactivé – sans explication. Un clic dessus ne faisait rien, et la
  barre d'état continuait de dire « Chargement des modèles
  linguistiques … », même après dix minutes. La cause : les
  perturbations dans les processus en arrière-plan allaient vers un
  endroit que personne ne voit au démarrage depuis le gestionnaire de
  fichiers ; il restait une fenêtre qui avait l'air prête au travail et
  ne réagissait à aucun clic. De telles perturbations atterrissent
  désormais dans le journal d'erreurs, le chargement des modèles
  linguistiques signale son échec dans tous les cas au lieu d'abandonner
  silencieusement, et si cela reste quand même silencieux, l'application
  indique après trois quarts de minute que quelque chose ne va pas,
  avec un conseil dans les détails. Le bouton verrouillé indique sa
  raison au survol. Un premier rechargement long ne compte pas comme
  silence : tant qu'une progression est signalée, cela reste calme.
  Rien de tout cela ne compte comme plantage : l'application continue
  de fonctionner, et au prochain démarrage, la question n'est donc pas
  posée non plus.

- **Sur le Mac, le programme ne trouvait plus de mises à jour – et
  disait être à jour.** La version Mac n'apportait pas de répertoire de
  certificats racine ; elle le cherchait à un endroit qui n'existe que
  sur l'ordinateur où elle est construite. Elle ne pouvait donc vérifier
  auprès d'aucun serveur à qui elle parlait et interrompait chaque
  connexion : pas de mises à jour, pas d'activation de licence, pas de
  rechargement de modèles linguistiques, pas de rapport d'erreur. Les
  versions plus anciennes en faisaient silencieusement l'information
  « Vous utilisez la dernière version ». Les certificats se trouvent
  désormais dans le programme lui-même ; s'il n'en trouve pas là, il
  prend ceux du système et sur le Mac en dernier recours ceux du
  trousseau – et s'il n'y en a vraiment aucun, il le dit au lieu
  d'affirmer être la dernière version. La vérification elle-même n'est
  jamais désactivée pour autant.

  Cette seule mise à jour, les utilisateurs Mac doivent encore
  l'installer à la main : une version qui n'atteint pas le serveur ne
  peut pas non plus se mettre à jour elle-même.

### Modifié

- **La fenêtre principale a été rangée.** En bas se trouvaient six
  boutons de même taille côte à côte – « À propos … », « Manuel » et
  « Aide & FAQ » en dessous, bien que ces trois mêmes chemins figurent
  déjà dans le menu Aide au-dessus. Ils sont désormais regroupés en un
  bouton « Aide » qui les déplie ; aucun n'est perdu. Restent en bas les
  deux chemins par lesquels on commence vraiment : « Nettoyer » et
  « Caviarder à la main … ».

- **Ce que le programme fait actuellement figure désormais à un endroit
  fixe.** Le message (« Chargement des modèles linguistiques … »,
  « (3 / 7) brief.pdf », « 5 sur 7 fichier(s) nettoyé(s). ») pendait
  jusqu'ici comme texte gris entre deux rangées de boutons. Il a reçu sa
  propre zone, avec un point coloré devant : gris tant que rien n'est en
  cours, bleu pendant le travail, vert après un passage sans problème et
  jaune quand des indications sont apparues. Le point ne dit rien qui ne
  figure pas à côté – il le dit juste plus vite.

- **Les paramètres sont devenus une fenêtre propre.** Ils se trouvaient
  jusqu'ici dans la fenêtre principale – un cadre avec quatre onglets
  que l'on dépliait sous « Plus de paramètres », et qui était alors trop
  petit pour son contenu : il y avait toujours une barre de défilement
  dedans, et le choix entre anonymiser et pseudonymiser se trouvait à
  moitié hors champ. Le bouton s'appelle désormais « Paramètres … » et
  ouvre une fenêtre avec une barre latérale ; chacune des quatre pages y
  tient entièrement. La fenêtre principale ne s'agrandit plus à
  l'ouverture, et on peut voir la liste de fichiers en même temps.
  Seul l'emplacement des paramètres a changé – ce qui existe et ce
  qu'ils font reste inchangé.

- **« Détails » se déplie au lieu de sauter.** La fenêtre grandissait
  jusqu'ici d'un coup, et il fallait ensuite chercher ce qui avait
  changé. Elle se déplace désormais vers cela.

- **Les tailles de police et les espacements suivent désormais la même
  mesure dans toute la fenêtre.** Les titres étaient de tailles
  différentes à deux endroits, et des lignes de même rang étaient
  espacées différemment. C'est visible comme un calme, pas comme un
  changement isolé.

- **Anonymiser est désormais le réglage par défaut.** Jusqu'ici, la
  pseudonymisation était activée par défaut : les mêmes personnes
  recevaient le même numéro (`[NAME_1]`, `[NAME_2]`), les liens
  restaient lisibles – mais restaient juridiquement des **données
  personnelles**. Qui ne règle rien obtient désormais le procédé qui
  sort les données du champ du RGPD : tous les résultats d'un type
  s'appellent de façon identique (`[NAME]`). La numérotation reste un
  choix, disponible sans changement dans la même fenêtre ; les
  paramètres existants restent tels quels. En ligne de commande,
  `--pseudonymisieren` (aussi `--mit-nummerierung`) rétablit l'ancien
  réglage.

- **Les espaces réservés anonymisés ne peuvent plus être annulés
  individuellement.** Qui anonymise reçoit pour chaque personne le même
  espace réservé – et il n'y a donc plus d'emplacement individuel
  rattaché à un nom précis. La fenêtre de retouche proposait pourtant
  « Annuler le remplacement » : un clic aurait inséré *une* des valeurs
  à *tous* les emplacements. Les lignes sont désormais atténuées comme
  pour les données caviardées, le clic indique la raison, et un
  résultat retracé à la main n'obtient plus de numéro qui ne figure
  nulle part ailleurs dans le document.

  Pour la même raison, il n'existe plus « Retraduire la réponse » après
  un passage anonymisé – auparavant, cela aurait mis un nom étranger à
  la place de chaque personne. Qui a besoin de cette boucle choisit
  « Pseudonymiser » ; l'application le dit désormais aussi de cette
  façon, au lieu de renvoyer à une affectation expirée.

  En ligne de commande, `--zuordnung` échoue désormais lors de
  l'anonymisation, au lieu d'écrire un fichier qui n'est pas une
  retraduction – dans la fenêtre, la case était déjà verrouillée
  depuis longtemps. Soit ajouter `--pseudonymisieren`, soit omettre
  `--zuordnung` ; le message le dit. Le résultat n'est alors même pas
  créé, afin qu'un script ne se retrouve pas avec un travail à moitié
  fait.

- **Le canal de mise à jour est désormais réglé sur « Stable ».** Sans
  choix propre, le canal suivait jusqu'ici la construction d'où venait
  la version en cours – qui avait une fois essayé une version de test
  se voyait dès lors proposer durablement des versions de test. Un
  changement de canal est une décision et doit le rester ; le réglage
  par défaut est donc « Stable ». Les canaux réglés restent inchangés.

### Amélioré

- **« Beschwerdevorgang » ne compte plus comme nom de lieu.** Dans le
  titre « Aktennotiz – Beschwerdevorgang 12 C 345/26 », le programme
  caviardait le dossier avec – le modèle de langage le prenait pour un
  lieu, indépendamment du contexte. Ce n'est pas le mot isolé qui est
  intégré, mais le **mot de base** du composé – « vorgang » et « notiz »
  couvrent ainsi aussi Geschäfts-, Buchungs- et Zahlungsvorgang ou la
  note téléphonique. Sur trente termes administratifs vérifiés, trois
  déclenchaient auparavant un faux positif, désormais plus aucun ; tout
  ce qui se trouve à côté continue d'être trouvé
  (« Beschwerdevorgang: Bernd Meisinger » perd le nom, pas le titre).

- **Anonymiser tient de nouveau un registre – pour le rattrapage et le
  journal.** En mode de fonctionnement anonymisant, le programme ne
  mémorisait pas les valeurs trouvées. Deux choses en devenaient
  muettes : le rattrapage de cohérence à l'échelle du document (un nom
  de famille apparaissant seul plus tard restait en place) et la liste
  des remplacements dans le journal de vérification. Tant qu'anonymiser
  était le choix le plus rare, cela se remarquait à peine – comme
  réglage par défaut, cela serait devenu le cas normal. Dans le
  document, rien ne change : l'espace réservé reste sans numéro.

- **« Kein personenbezogenes Datum » s'appelle désormais « keine
  personenbezogene Angabe ».** Dans la boîte de dialogue de récupération
  et dans l'avertissement sur les visages figurait le terme juridique
  *Datum* – le singulier de « Daten ». Il était lu comme un jour de
  calendrier, d'autant que l'application propose ailleurs « Supprimer
  aussi les dates ». Il s'appelle désormais partout « Angabe », comme
  dans les quatre raisons au-dessus dans la même fenêtre.

- **La ligne d'origine ne figure plus que dans la fenêtre « À
  propos ».** « Made with ♥ in Austria » se trouvait en bas de la
  fenêtre principale, au milieu de la rangée de boutons, et se lisait
  là comme un bouton de plus. Elle se trouve désormais dans la fenêtre
  « À propos » – là où on la cherche.

- **La zone de dépôt a désormais un bord visible.** Sa bordure en
  pointillés était si pâle qu'elle se détachait à peine de la fenêtre –
  cela était indifférent tant que la zone n'était qu'une surface.
  Depuis qu'elle est un bouton que l'on peut atteindre à la touche
  Tabulation, ce trait est la seule chose qui la montre comme élément
  de commande ; il est donc relevé à la valeur que la norme exige pour
  cela.

## 0.10.22-beta.1 – 15 août 2026

### Nouveau

- **Si la surveillance du presse-papiers est désactivée, elle l'est
  vraiment.** Le veilleur garde les derniers contenus en mémoire vive
  afin que l'original puisse être remis en place – jusqu'ici même
  lorsque vous aviez désactivé la surveillance. L'historique est
  désormais oublié à la désactivation. Cela coûte la restauration après
  la désactivation, et c'est exactement voulu ainsi : désactivé signifie
  désactivé.
- **Le journal d'erreurs ne contient plus de chemins de fichier.** Il se
  trouvait uniquement sur votre ordinateur et n'était jamais envoyé de
  lui-même – mais il consignait des chemins en clair, et un nom de
  fichier révèle souvent plus que le contenu. « …/Scheidung_Mueller_
  Vergleich.docx » devient désormais `<datei>.docx` à l'écriture ;
  l'extension reste, car elle compte pour la recherche d'erreurs. Il en
  va de même pour la note laissée après un plantage.
- **La liste des remplacements avertit désormais d'elle-même.** C'est le
  seul fichier où vos données d'origine figurent en clair, et il se
  trouve à côté du résultat – qui transmet un dossier le transmet avec.
  L'avertissement figure désormais comme première ligne **dans** le
  fichier, la zone de sortie indique le chemin complet au lieu du seul
  nom de fichier, et en ligne de commande le fichier est enfin
  mentionné : on ignorait jusqu'ici même qu'il avait été créé.
- **Anonymiser ou pseudonymiser est désormais un choix nommé.** Il y
  avait jusqu'ici une case « Nommer les mêmes noms de la même façon –
  l'IA reconnaît alors encore qui est qui ». Elle décrivait l'avantage et
  taisait la conséquence : des espaces réservés numérotés (`[NAME_1]`,
  `[NAME_2]`) sont une **pseudonymisation**, et des données
  pseudonymisées restent des données personnelles – qui croyait avoir
  ainsi anonymisé se trompait. Les deux procédés figurent désormais côte
  à côte, chacun avec son prix. Le réglage par défaut reste la
  pseudonymisation, car un document encore lu ou traité ensuite par une
  IA a besoin de ses références. Lors de l'anonymisation, la liste des
  remplacements est verrouillée : elle rendrait le résultat de nouveau
  traçable. Le manuel et la FAQ expliquent la différence dans les 18
  langues ; en ligne de commande, l'interrupteur s'appelle désormais
  aussi `--anonymisieren`.
- **La ligne au-dessus de la zone de dépôt dit désormais ce qui est
  vraiment vrai.** Elle promettait « traitement 100 % local – sans
  cloud ni compte, conforme au RGPD ». Pour vos documents, c'est exact,
  pour le programme pas dans cette généralité : il recherche des mises à
  jour, signale des erreurs sur demande, télécharge des modèles et
  enregistre les postes de travail achetés. On y trouve désormais
  l'affirmation plus étroite et fondée : vos documents ne quittent pas
  l'ordinateur.
- **Le résultat indique désormais toujours qu'il doit être vérifié.**
  Jusqu'ici, Maskuro annonçait après un passage sans problème
  « 12 donnée(s) supprimée(s) » en vert et rien d'autre – cela se lit
  comme une assurance d'avoir tout trouvé. Des indications
  n'apparaissaient que si quelque chose de concret n'avait pas pu être
  vérifié (images, pièces jointes inconnues). Désormais figure sous
  chaque résultat, de façon bien visible, que toutes les données
  personnelles ne sont pas systématiquement détectées, que la
  vérification incombe à l'utilisateur et que ce qui manque doit être
  complété à la main – dans la fenêtre, dans la zone de sortie et en
  ligne de commande. Aucune fenêtre de message à fermer d'un clic : la
  phrase reste affichée en permanence. Le guide rapide le dit désormais
  dans les mêmes termes.
- **Après une mise à jour, ce qui a changé s'affiche au démarrage.**
  Jusqu'ici, une mise à jour se déroulait silencieusement et n'était pas
  distinguable d'un simple redémarrage. Désormais apparaît une fois
  « Quoi de neuf » – et qui a sauté une version voit aussi celles entre
  temps. Pas au tout premier démarrage : là, c'est toujours le guide
  rapide qui accueille.
- **Le chinois et le japonais trouvent désormais des noms.** Jusqu'ici,
  ils n'en trouvaient **aucun** – pas peu, aucun. Les deux modèles
  linguistiques manquaient de segmentation de mots, sans laquelle une
  phrase sans espaces compte comme un seul mot ; le programme se rabattait
  silencieusement sur le modèle multilingue de remplacement. Les deux
  langues reconnaissent désormais les personnes et les lieux comme les
  autres. Le dictionnaire japonais est alors chargé avec la langue et ne
  se trouve pas dans le programme – à lui seul il pèserait bien 200 Mo,
  que tout le monde aurait sinon dû porter.
- **La Roumanie est sélectionnable comme pays.** Elle manquait
  entièrement jusqu'ici. Sont ainsi reconnues les adresses roumaines
  (« Strada Victoriei 30 »), les codes postaux avec localité
  (« 010061 București ») et le Cod Numeric Personal – ce dernier
  seulement avec un chiffre de contrôle correct, afin que tout nombre à
  treize chiffres sur une facture ne soit pas marqué. Jusque-là, dans les
  documents roumains, le code postal restait lisible à côté du nom de
  lieu caviardé.
- **« Rastériser la page » dans l'éditeur.** Si le texte d'un PDF ne peut
  pas être supprimé – cela arrive avec des fichiers d'origine tierce –,
  la page peut désormais être remplacée sur demande par son image :
  le texte a ainsi définitivement disparu, la page reste lisible et
  consultable par recherche. L'avertissement qui signale ce cas propose
  directement l'étape sous forme de bouton ; via « Outils → Rastériser la
  page », elle est aussi accessible d'elle-même. Annuler ramène la page.
- **L'interface existe désormais aussi en croate, grec, lituanien,
  slovène, japonais et coréen.** Cela porte à dix-huit le nombre de
  langues. Le manuel, la FAQ et les textes légaux sont complets dans les
  six. Les libellés dans le document nettoyé suivent l'interface – de
  `[NAME_1]` on obtient `[IME_1]`, `[ΟΝΟΜΑ_1]`, `[VARDAS_1]` ou
  `[氏名_1]`. **Pour le grec, le japonais et le coréen, les libellés
  restent en caractères latins** – `[ONOMA_1]`, `[SHIMEI_1]`,
  `[IREUM_1]`. L'interface reste dans sa propre écriture ; seul ce qui
  est écrit dans le document est en latin. La raison est le jeu de
  caractères du PDF : les libellés grecs et japonais y arrivaient
  auparavant sous forme de `[??_1]`, rendant impossible de distinguer un
  nom d'un lieu.
- **Neuf pays s'ajoutent, et sept existants deviennent complets.** Sont
  désormais reconnus les numéros de carte d'identité, fiscaux et de
  sécurité sociale ainsi que les adresses pour la **Croatie, la
  Slovénie, la Grèce, la Lituanie, la Macédoine du Nord, la Russie,
  l'Ukraine, la Chine et le Japon**. Pour les pays déjà pris en charge,
  des lacunes plus importantes sont comblées : pour les **Pays-Bas** et
  le **Portugal**, il n'existait jusqu'ici aucun numéro de personne – le
  BSN néerlandais et le NIF portugais n'étaient pas reconnus, bien
  qu'ils figurent sur pratiquement chaque document de ces pays. La
  Pologne obtient le numéro fiscal NIP, le Danemark, la Norvège et la
  Finlande leurs adresses, le Canada son code postal. Cela porte le
  total à **35 pays**.

### Supprimé

- **Pour Linux, il n'y a provisoirement plus de paquet.** Le code source
  y fonctionne, mais trois éléments promis par ce manuel manquent sous
  Linux : démarrage automatique, raccourcis clavier globaux et – selon
  l'environnement de bureau – l'icône dans la barre. Livrer un paquet
  qui fait moins que ce qui est décrit serait la mauvaise voie. Windows
  et macOS ne sont pas concernés.

### Amélioré

- **Les numéros de dossier sont désormais trouvés dans toutes les
  langues.** « Aktenzeichen 12/2026-AB » était supprimé, « File
  reference 12/2026-AB » ou « Sygnatura 12/2026-AB » restaient en
  place : les mots de champ auxquels Maskuro reconnaît un tel numéro
  n'existaient qu'en allemand. Il connaît désormais les équivalents dans
  douze langues – et comme avant, seul le numéro est remplacé, le
  libellé devant reste en place, afin que l'on puisse voir dans le
  résultat ce qui a été supprimé à cet endroit.
- **Maskuro occupe environ un demi-gigaoctet de moins au repos.** Au
  démarrage, le modèle complémentaire de détection plus précise était
  jusqu'ici aussi chargé, afin que le premier nettoyage n'ait pas à
  l'attendre. Mesuré, cela coûtait 648 Mo de mémoire vive et
  économisait 1,9 seconde – et cela coûtait même lorsque vous ouvriez la
  fenêtre pour la refermer aussitôt. Le modèle est désormais chargé la
  première fois qu'il est nécessaire ; la ligne d'état l'indique. Le
  modèle linguistique continue d'être chargé au démarrage – la
  surveillance du presse-papiers en a besoin immédiatement.
- **La zone de dépôt peut désormais aussi être utilisée sans souris.**
  « Glisser les fichiers ici » était une zone réagissant aux clics – on
  ne pouvait pas y accéder au clavier, et un lecteur d'écran la lisait
  comme un cadre contenant du texte, pas comme ce qu'elle est vraiment.
  C'est désormais un bouton : la touche Tabulation y accède, les
  touches Espace et Entrée ouvrent la sélection de fichiers, et qui y
  est arrivé le voit à la bordure. Via le menu « Fichier → Sélectionner
  des fichiers », c'était déjà possible auparavant, mais il fallait le
  savoir.
- **Le nom du fichier nettoyé est désormais aussi lu à voix haute.** Dans
  la liste des fichiers, il figure comme deuxième ligne, plus petite,
  sous l'original – mais il n'était que dessiné, et un lecteur d'écran
  ne nommait que l'original. C'est justement cette ligne qui est conçue
  contre l'erreur de croire qu'un passage a été sans effet parce que le
  dossier contient l'original intact. La ligne se lit désormais à voix
  haute « rechnung.pdf, résultat : rechnung_bereinigt.pdf ».
- **Les éléments de commande sans libellé disent désormais à quoi ils
  servent.** Les boutons d'icône dans la liste des fichiers, les
  boutons de lettre dans la fenêtre de retouche et tous les champs de
  sélection et de saisie étaient sans nom pour les lecteurs d'écran –
  ils étaient annoncés comme « bouton » et « champ combiné », sans
  préciser quoi. Les boutons d'une ligne nomment désormais aussi le
  fichier : dans une liste de vingt entrées, on entendait sinon vingt
  fois la même phrase.
- **Qui navigue au clavier voit de nouveau où il se trouve.** Le bouton
  « Nettoyer » et les boutons d'icône dans la liste des fichiers sont
  conçus en couleur, ce qui faisait disparaître le cadre que le système
  place normalement autour de l'élément atteint – en tabulant, le regard
  se perdait dans le vide. Les deux disposent désormais d'un cadre
  propre dès qu'ils sont sélectionnés. Les boutons ne changent pas de
  taille pour autant.
- **Sept couleurs de texte étaient trop pâles, dans les deux
  apparences.** Mesurées selon la norme habituelle (WCAG 2.1), les
  lignes d'indication pâles, les textes secondaires sur la zone de
  dépôt, les points du guide et, dans l'apparence sombre en plus, le
  bleu et le rouge se trouvaient sous le seuil de 4,5:1 – lisibles avec
  une bonne lumière et de bons yeux, sinon non. Toutes ont été
  relevées ; la nuance reste, les textes se lisent toujours comme des
  textes secondaires. Trois autres – les couleurs dans lesquelles
  avertissements et succès sont signalés – tenaient le seuil de justesse
  et ont été ajustées en même temps : qui ne les lit pas ne lit pas
  l'information disant si quelque chose s'est mal passé. Seul le bouton
  « Nettoyer » dans l'apparence sombre a visiblement changé : il porte
  désormais une écriture sombre au lieu de blanche, comme les boutons
  d'accentuation de Windows 11 également.
- **Chaque ligne de la liste de fichiers a désormais sa propre croix.**
  Jusqu'ici, il fallait d'abord sélectionner la ligne puis cliquer sur
  « Supprimer » – deux étapes pour un détail. La croix se trouve à
  droite dans la ligne et n'en nécessite qu'une. Le bouton « Supprimer »
  en dessous a de ce fait disparu ; qui veut se débarrasser de plusieurs
  lignes à la fois les sélectionne et prend l'entrée du menu
  contextuel, qui indique aussi combien il y en a. « Tout supprimer »
  reste. Ce qui est retiré de la liste est toujours seulement la ligne –
  jamais un fichier sur le disque.
- **Avant la vérification par IA figure désormais si cet ordinateur y est
  adapté.** Jusqu'ici, la fenêtre indiquait seulement la taille du
  modèle. Qui l'activait sur un ordinateur peu puissant ne remarquait
  qu'au premier document que cela prenait très longtemps – après un
  téléchargement de 5,4 Go. La fenêtre indique désormais **à l'avance**
  la mémoire vive et l'espace libre et explique ce que cela signifie ;
  **après**, la vitesse est mesurée et exprimée dans l'ordre de grandeur
  concerné : « Un document de dix pages prend environ 12 minutes sur cet
  ordinateur. » Si c'est trop lent, le programme le déconseille et
  propose de redésactiver le niveau – il n'interdit rien.
- **La mesure de vitesse fonctionne désormais sur chaque ordinateur.**
  Jusqu'ici, elle n'apparaissait que si l'accélération graphique était
  en plus configurée – ce qui n'existe que sous Windows. Sur tous les
  autres ordinateurs, le programme estimait donc la durée sur la base
  d'un ordinateur étranger, et c'est justement là où c'est lent que
  l'estimation était fausse.
- **Les adresses turques sont désormais trouvées aussi dans le scan.**
  Sur un en-tête de lettre scanné, « 34710 İstanbul » restait lisible,
  tandis que la même indication dans le texte voisin disparaissait : la
  reconnaissance de texte lit le İ turc sans son point, et le modèle
  attendait une majuscule. Il en allait de même pour « Bağdat Caddesi ».
- **Les adresses espagnoles sans nom de rue propre sont désormais
  trouvées.** « Gran Vía 5 » restait en place, car le modèle attendait
  encore un mot de nom après le type de voie – dans « Calle Mayor » il y
  en a un, dans « Gran Vía » le type lui-même est déjà le nom. Il en va
  désormais de même pour « La Rambla » et « Castellana ».
- **Dans la fenêtre « À propos de ce programme » figure désormais une
  mention de transparence** indiquant que l'application a été développée
  avec l'aide de l'intelligence artificielle. Elle concerne la création
  du programme, pas son mode de fonctionnement : le nettoyage continue
  de se faire exclusivement sur l'ordinateur lui-même.
- **« Gérer les langues » affiche désormais d'abord les langues
  utilisables.** Pour la moitié des 48 langues de document, il n'existe
  pas de modèle linguistique propre ; un modèle multilingue de
  remplacement y reconnaît les noms faiblement, et pas du tout dans
  certaines écritures. Côte à côte dans une liste, toutes avaient l'air
  équivalentes. Le réglage par défaut n'affiche donc plus que les
  langues avec modèle propre – via « Affiché », les autres peuvent être
  visualisées à tout moment, avec une phrase sur ce qu'elles peuvent
  faire et ne peuvent pas faire. Rien ne disparaît, et qui a configuré
  une langue limitée la conserve.
- **La question concernant une langue manquante indique désormais la
  solution.** Quand une langue est détectée pour laquelle rien n'est
  encore configuré, le programme ne proposait jusqu'ici que « Charger »
  ou « Continuer sans ». Mais la détection peut se tromper – pour des
  formulaires courts et des listes avec peu de texte continu, peu de
  mots décident. La fenêtre indique donc désormais que l'on peut annuler
  et choisir la bonne langue à la main, au lieu d'utiliser « Détecter
  automatiquement ». Cela évite en cas de doute un téléchargement de
  plusieurs centaines de mégaoctets pour une langue dont on n'a en fait
  pas besoin.
- **Les libellés des espaces réservés parlent désormais la langue de
  l'interface.** « [NAME_1] », « [ADRESSE_2] » et consorts étaient
  jusqu'ici toujours en allemand, quelle que soit la langue réglée ou la
  langue dans laquelle le document est rédigé. Ils suivent désormais la
  langue de l'interface – en anglais donc « [NAME_1] », « [ADDRESS_2] ».
  Pas la langue du document : celle-ci est devinée avec « détecter
  automatiquement » et parfois fausse ; la langue de l'interface ne
  l'est jamais.
- **Moins de questions lors de la retouche.** L'endroit où le résultat
  est enregistré figure désormais en permanence en bas de la barre
  (« → vertrag_bereinigt.pdf », le dossier en infobulle) – un clic
  dessus permet de choisir un autre emplacement sans enregistrer
  aussitôt. La question posée au premier enregistrement disparaît donc.
  La question « déjà traité – recommencer ? » peut être mémorisée pour
  la session, et deux fenêtres d'information qui ne donnaient qu'une
  indication figurent désormais dans la barre d'état. Sont restées les
  questions qui préviennent un dommage irréversible : le travail non
  enregistré à la fermeture et l'avertissement sur le texte non
  supprimé.
- **Le résultat indique désormais où le scan lui-même n'était pas
  lisible.** Sur un document scanné, la reconnaissance de texte de
  l'appareil ne lit pas tout correctement – « Solarstraße 9 » devient
  alors par exemple « Solaret^aß« B ». Ce qui a été ainsi mal lu, aucune
  vérification ne peut plus le trouver : cela ressemble pour chaque
  modèle de recherche à une salade de lettres. Le programme n'y peut
  rien changer, mais nomme désormais de tels endroits avec le numéro de
  page – on y trouve le plus souvent des tampons, en-têtes de lettre ou
  ajouts manuscrits. Une indication, pas un avertissement : sur un
  document composé, elle n'apparaît pas.
- **La liste de fichiers indique désormais le nom du résultat.** Sous le
  nom de fichier figure après le passage le nom du fichier nettoyé
  (« → vertrag_bereinigt.pdf »). Jusqu'ici, il ne figurait que dans le
  journal derrière « Détails », et qui regardait dans le dossier trouvait
  l'original intact. Le nom de la source reste affiché – sinon on ne
  verrait plus de quel fichier provient un résultat.
- **Les boutons d'une ligne terminée sont plus grands et plus nets.**
  Voir, Retoucher et « Afficher dans le dossier » étaient des icônes
  plates sans surface et se perdaient dans la liste – alors qu'ils sont,
  après le passage, la seule chose sur laquelle on clique encore.

### Corrigé

- **Sur une interface en langue étrangère, les règles personnelles de
  caviardage, masquage et hachage étaient ignorées silencieusement.**
  Qui avait défini que les noms devaient être caviardés plutôt que
  remplacés les obtenait quand même remplacés – dès que le programme
  n'était pas utilisé en allemand ou en anglais. Le paramètre était bien
  là, il n'agissait simplement pas, et la différence n'était pas visible
  dans le résultat. Neuf des douze langues d'interface étaient
  concernées.
- **Le paramètre « Langue des libellés » n'avait aucun effet en dehors
  de l'allemand et de l'anglais.** « Allemand » et « Anglais » étaient
  sélectionnables, mais dans le document restait la langue de
  l'interface. Désormais, les trois possibilités agissent ; le réglage
  par défaut « comme l'interface » fournit sans changement le même
  résultat qu'auparavant.
- **Dans de courts extraits de texte, des noms restaient en place – par
  exemple dans une citation de mail copiée.** Qui nettoyait un extrait
  via le presse-papiers n'obtenait souvent que l'adresse e-mail
  caviardée, mais pas le nom en dessous. Le facteur décisif était le
  simple nombre de lignes : à partir de six lignes, le programme
  reconnaissait l'extrait comme une liste et trouvait les noms, en
  dessous non – une citation de mail copiée en a cinq. Une ligne
  supplémentaire quelconque, par exemple un objet, faisait basculer le
  résultat. Désormais, quatre lignes suffisent, et dans la mesure, tous
  les noms vérifiés disparaissent au lieu d'un tiers. Cela n'a aucun
  effet sur les documents plus longs ni sur le texte continu.
- **L'accélération graphique de la vérification par IA était jusqu'ici
  redésactivée dès qu'on l'avait configurée.** Après la configuration,
  le programme mesure si la carte graphique de cet ordinateur est
  vraiment plus rapide que le processeur – cette mesure échouait
  cependant toujours, sans le dire, et le résultat « les deux aussi
  rapides » tranchait en faveur du processeur. Qui avait chargé les
  65 Mo obtenait ensuite moins qu'avant. La mesure fonctionne
  désormais ; si elle échoue, elle ne change plus rien.
- **L'estimation de durée calculait sur chaque ordinateur avec une
  vitesse étrangère.** Elle s'appuie sur la même mesure ; tant que
  celle-ci ne fonctionnait pas, la valeur de l'ordinateur de
  développement s'appliquait. « Environ deux minutes » pouvait ainsi
  signifier une demi-heure sur un ordinateur lent.
- **Le niveau IA travaille avec un nouveau modèle linguistique nettement
  meilleur** (Qwen3.5-9B au lieu de Qwen3-4B) et n'est plus limité à
  l'allemand et à l'anglais, mais fonctionne dans douze langues. Mesuré
  sur le corpus de vérification : autant de données trouvées que sans le
  niveau, mais moins de la moitié de caviardages superflus (75 → 31). Le
  modèle est plus grand (5,4 au lieu de 2,4 Go) et nécessite environ le
  double du temps de calcul ; à l'activation, il est chargé une fois,
  l'ancien étant alors supprimé.
- **Les adresses en français, italien, espagnol, portugais, polonais,
  turc et suédois sont désormais entièrement supprimées.** Jusqu'ici,
  seuls le nom de rue et de lieu disparaissaient – le numéro de maison
  et le code postal restaient lisibles (« [ORT_1] 28, 28013 [ORT_2] »).
  Il n'existait pas de modèles d'adresse propres pour ces langues ; ils
  sont désormais complétés.
- **Le grec et le coréen ne trouvaient aucun nom du tout.** Pour le
  grec, la cause était le modèle de remplacement – avec le modèle
  propre, qui peut désormais être chargé, les noms et lieux sont
  reconnus proprement. Pour le coréen, la cause était le programme : il
  présupposait qu'un nom commence par une majuscule, et le hangeul ne
  connaît pas de majuscules. Étaient surtout concernées les unités
  courtes – cellules de tableau, champs de formulaire, entrées de
  liste.
- **Un modèle linguistique qui ne pouvait pas être chargé interrompait le
  nettoyage.** Au lieu d'un message d'erreur, le modèle multilingue
  prend désormais le relais, et le résultat signale qu'une détection
  plus faible a été utilisée. Concerne actuellement le chinois et le
  japonais, dont les modèles nécessitent une segmentation de mots pas
  encore incluse dans le programme.
- **Une langue avec modèle propre était considérée comme installée dès
  qu'une autre quelconque était chargée.** Qui configurait par exemple le
  turc obtenait ainsi le modèle multilingue de remplacement – et le
  chinois, le japonais, le coréen ou le grec apparaissaient ensuite avec
  une case cochée et « 0 Mo » dans la liste, alors que leur modèle
  propre manquait. Ils ne pouvaient de ce fait jamais être rechargés et
  travaillaient durablement avec le remplacement plus faible. La liste
  affiche désormais l'état réel avec la taille de téléchargement.
- **Un niveau de détection défaillant restait silencieux.** Si
  « Détection avancée » ou « Détection maximale (IA) » était activée
  mais que le modèle ne pouvait pas s'exécuter, le programme continuait
  de fonctionner sans ce niveau – sans un mot à ce sujet. Le résultat
  ressemblait à tout autre, et l'interrupteur restait sur « activé » :
  on prenait donc le résultat du niveau de base pour le meilleur
  possible. Le résultat le dit désormais et indique les deux choses – ce
  qui n'a pas été vérifié et comment recharger le modèle. Le cas n'est
  pas rare : sur certains ordinateurs, le niveau IA échoue au
  chargement quand l'accélération graphique manque.
- **Une erreur lors du chargement du modèle complémentaire interrompait
  tout le nettoyage.** Pour « Détection avancée », seule l'évaluation du
  modèle était sécurisée, pas sa lecture – et c'est justement là que
  cela échoue quand le fichier est endommagé ou ne convient pas à
  l'ordinateur. Au lieu d'un message d'erreur, il y a désormais un
  résultat du niveau de base accompagné d'une indication.
- **Une langue ne pouvait plus être supprimée – et donc plus rechargée
  non plus.** Qui décochait une langue dans « Gérer les langues » et
  validait le changement lisait « Allemand supprimé », mais voyait la
  case aussitôt recochée. La cause était la reprise depuis le dossier du
  programme : pour une installation pour tous les utilisateurs, les
  modèles linguistiques se trouvent en lecture seule dans le dossier du
  programme, et le programme y récupère ceux qui manquent au lieu de
  recharger des centaines de mégaoctets. Cette reprise s'exécutait à
  chaque accès – et recopiait dans le même mouvement la langue qui
  venait d'être supprimée. Elle ne se produit désormais qu'une seule
  fois ; les modèles linguistiques rechargés sont alors conservés. En
  outre, le programme vérifie après la suppression : ce qui n'a pas pu
  être supprimé est désormais signalé comme un échec plutôt que comme
  « supprimé ».
- **Pour une installation destinée à tous les utilisateurs, les éléments
  rechargés ne pouvaient pas être déposés.** Qui installe le programme
  pour tous les utilisateurs l'a dans « Programmes », et rien ne peut y
  être écrit sans droits d'administrateur. Pour les modèles
  linguistiques, un emplacement de repli était depuis longtemps prévu à
  cet effet, pas pour le reste :
  - Le **composant d'aperçu des pages** était décompressé après un
    téléchargement de 290 Mo dans le dossier du programme et y échouait –
    sans en indiquer la raison. Il se trouve désormais avec les modèles
    linguistiques, là où il aurait toujours dû se trouver selon
    l'intention.
  - L'**accélération graphique** ne peut pas se replier : elle échange
    des bibliothèques dans le programme lui-même. Au lieu de charger
    d'abord puis d'échouer sans un mot, le programme indique désormais à
    l'avance que ce n'est pas possible ici et ce que cela signifie – la
    détection maximale continue de fonctionner, seulement via le
    processeur.
  - Une **langue de reconnaissance de texte** fournie ne pouvait pas
    être supprimée : elle était immédiatement restaurée depuis le
    dossier du programme. Même cause que pour les modèles linguistiques,
    même correction.
  - Lors de la suppression d'une langue, des **données linguistiques
    d'une installation Tesseract étrangère** pouvaient être
    supprimées. Seul le dossier propre est désormais touché.
  - L'emplacement de repli ne s'appliquait jusqu'ici que sous Windows.
    Une archive Linux vers `/opt` avait le même problème sans la même
    solution.
- **Lors de la retouche, une ligne entière disparaissait alors qu'un
  seul mot était encadré.** Qui caviardait un espace réservé dans un
  fichier déjà nettoyé perdait la ligne où il se trouvait : de « Sehr
  geehrte Frau Doktor [NAME_1] » il ne restait rien – et le message
  disait « un mot supprimé du document ». Était touché tout fichier déjà
  passé une fois par le programme, donc justement le cas pour lequel la
  retouche existe. Le reste du texte reste désormais en place, à
  l'emplacement inchangé.
- **« EMPLOYEES » au-dessus d'une liste de noms était lui-même
  caviardé.** Même cas que « MITARBEITER » dans la 0.10.19, mais en
  anglais – il y était resté. En majuscules, le modèle de langage
  manque du critère distinctif, et le titre se trouve au-dessus de purs
  vrais noms. Les noms en dessous continuent d'être trouvés. « staff »
  n'a pas été ajouté : c'est un nom de famille attesté, et l'entrée
  emporterait chaque « John Staff » – même arbitrage qu'en son temps
  pour « Arbeiter ».
- **La forme juridique était remplacée une seconde fois.** Sur un
  en-tête de lettre scanné, le modèle de langage lisait « GmbH »,
  l'adresse et le code postal comme **un seul** lieu. L'adresse et le
  code postal découpaient ensuite leurs propres morceaux, et il restait
  la forme juridique comme résultat propre : dans le résultat figurait
  « [ORT_1] [ORT_2] », alors que « [ORT_1] GmbH » était visé. La raison
  sociale continue d'être remplacée – seul le suffixe nu reste
  désormais en place, et le résultat se lit comme un en-tête de lettre
  plutôt que comme un exercice à trous.
- **Un résultat découpé n'était pas revérifié.** La cause du cas
  ci-dessus, et elle va plus loin : les filtres contre les résultats
  devinés fonctionnaient sur ce que les détecteurs **signalent** – pas
  sur ce qui reste après la résolution des chevauchements. Si un long
  résultat est réduit par un détecteur plus fort, le fragment est un
  texte différent de celui évalué, et personne ne le regardait une
  seconde fois. Désormais si.
- **« Vous utilisez la dernière version » – alors qu'il était impossible
  de vérifier.** Qui avait réglé le canal de mise à jour sur « Préversion
  (bêta) » ou « Stable – recommandé » recevait cette information, alors
  que rien n'était jusqu'ici jamais paru sur ces canaux. Le programme le
  dit désormais exactement – et propose de choisir un autre canal dans
  les paramètres.
- **Fermer la fenêtre pendant le chargement faisait planter un fil
  d'exécution.** Qui démarrait Maskuro et refermait aussitôt la fenêtre
  pendant que les modèles linguistiques étaient encore en cours de
  chargement obtenait un rapport d'erreur dans le journal : le
  chargement se signalait auprès d'une fenêtre qui n'existait plus. Cela
  n'avait aucune conséquence visible, mais un plantage figurait dans le
  journal, alors que quelqu'un avait simplement été plus rapide que le
  programme.
- **Le résultat est désormais examiné visuellement, pas seulement relu.**
  Jusqu'ici, une page était considérée comme propre si la valeur ne
  figurait plus dans le texte. Sur un scan, ce n'est pas une preuve –
  le texte visible y est une image. À la fin, on vérifie donc désormais
  si la zone est vraiment caviardée dans le résultat ; s'il reste du
  papier clair à cet endroit, le rapport le dit explicitement, au lieu
  de signaler « remplacé ».
- **Une donnée remplacée restait présente dans l'image.** Si la valeur se
  trouvait sur une image – un en-tête de lettre scanné, un tampon, une
  page entièrement scannée –, elle était certes supprimée du texte du
  document, mais restait **visible** : ce que la personne lit là, ce sont
  des pixels. Le rapport signalait quand même « remplacé ». La zone est
  désormais caviardée dans l'image, quelle que soit la stratégie
  réglée, et l'espace réservé s'affiche en clair sur ce fond – laid,
  mais honnête, et la correspondance reste conservée. Si un format
  d'image ne peut pas être traité, le résultat le dit désormais
  explicitement, au lieu d'avoir l'air propre.
- **Sur un scan, l'espace réservé manquait entièrement.** La couche de
  texte d'une page scannée est dessinée invisible, et un espace réservé
  qui y était inséré héritait de cela : posé, mais invisible. À
  l'emplacement trouvé, il ne restait alors rien.
- **Une reconnaissance de texte qui ne pouvait pas du tout s'exécuter
  était considérée comme réussie.** Si le fichier de langue manquait ou
  que le moteur de reconnaissance échouait, le rapport signalait
  « Image(s) … vérifiée(s) par reconnaissance de texte (0 emplacement(s)
  trouvé(s)) » – donc une vérification qui n'a jamais eu lieu. Sur un
  scan, c'est la seule vérification possible : un contrat avec une
  adresse lisible dans l'image de page était ainsi considéré comme
  terminé. Le rapport indique désormais que rien n'a été vérifié, et
  pourquoi.
- **Le fichier de langue était recherché dans le mauvais dossier.** Si
  d'autres langues que celle du document se trouvaient dans le répertoire
  linguistique propre, le moteur de reconnaissance recevait exactement
  ce répertoire et échouait – bien que la langue adéquate se trouve à
  côté. C'est désormais la **langue** qui est recherchée, pas le
  dossier.
- **L'avertissement sur le texte non supprimé conseillait quelque chose
  qui n'existe pas.** Il renvoyait à « Caviarder en tant que PDF » – mais
  cela génère une vue PDF de fichiers *Office* et n'est même pas
  disponible pour un PDF. Qui voulait suivre l'avertissement cherchait
  en vain. Le bouton qui règle la question s'y trouve désormais.
- **Dans l'éditeur, des barres et espaces réservés atterrissaient à côté
  de l'emplacement marqué.** Était concerné tout PDF où une ligne se
  termine par un trait d'union et où le mot continue à la ligne
  suivante – sur les scans, cela se remarque particulièrement, car les
  textes contractuels sont composés en continu avec césures. Les deux
  moitiés de ligne comptaient comme *un* mot s'étendant sur toute la
  justification, et chaque cadre à proximité reprenait cette étendue. La
  détection elle-même n'en change pas pour autant : le corpus de mesure
  fournit le même résultat qu'auparavant.
- **L'éditeur avertissait que le texte « figurait toujours dans le
  document », alors qu'il avait été supprimé.** Si le même mot
  apparaissait plusieurs fois sur une page – la règle dans les
  contrats –, la vérification automatique signalait un échec après
  chaque intervention. Elle compte désormais les occurrences, au lieu
  de simplement vérifier si le mot se trouve encore quelque part. Pour
  un véritable échec, elle avertit sans changement.
- **Le fichier de résultat s'appelait « _bereinigt » dans chaque
  langue.** L'intention était toujours que le suffixe du nom suive la
  langue de l'interface – en anglais c'était bien le cas
  (« _cleaned »), dans les seize autres langues non. Qui utilisait le
  programme en finnois obtenait « asiakirja_bereinigt.pdf ». Le fichier
  s'appelle désormais « asiakirja_puhdistettu.pdf », en japonais
  « 書類_除去済み.pdf » et ainsi de suite – chaque fois avec le mot que
  cette même interface utilise dans son message de fin. Qui a réglé un
  suffixe propre le conserve.
- **« Gérer les langues » s'affichait toujours en allemand.** Dans la
  liste des 48 langues de document figuraient les noms allemands, quelle
  que soit l'interface réglée : un utilisateur finlandais lisait
  « Chinesisch ». Le nom figure désormais dans sa langue, suivi du nom
  propre – « Kiina (中文) ». Le nom propre est intentionnel : qui
  reconnaît la langue à son propre nom la retrouve aussi quand le mot
  finnois ne lui dit rien.

## 0.10.19 – 12 août 2026

### Amélioré

- **L'entrée du menu contextuel parle désormais votre langue.** Jusqu'ici,
  le libellé allemand y figurait sur tous les systèmes – même sur un
  Windows anglais. Elle suit désormais la langue d'interface définie, et
  qui change de langue voit l'entrée renommée immédiatement, sans
  réinstaller. (Windows ; sous macOS et Linux, le nom du menu est en même
  temps un nom de fichier – cela viendra plus tard.)
- **L'éditeur se souvient de la vue dans laquelle vous avez travaillé en
  dernier.** Qui utilise l'aperçu des pages le retrouve automatiquement au
  prochain document – sans devoir l'activer à chaque fois. Qui ne l'a
  jamais utilisé ne remarque rien : il n'est restauré que si le module
  nécessaire est déjà chargé, rien n'est jamais rechargé exprès pour cela.

### Corrigé

- **« MITARBEITER » au-dessus d'une liste de noms était lui-même
  caviardé.** Dans les annuaires du personnel et les organigrammes, le
  titre disparaissait comme un nom présumé – il se trouve au-dessus de
  purs vrais noms, et en majuscules le modèle de langage manque du
  critère distinctif. Les noms en dessous continuent d'être trouvés.
- **Des indications de quantité étaient prises pour des adresses.** Dans
  les factures, bons de livraison et listes de stock, des indications
  comme « 3390 Protokoll », « 1030 Betrag » ou « 3390 Lager »
  disparaissaient comme prétendu code postal avec localité – tout nombre à
  quatre chiffres ressemble à un code postal autrichien. Si le nombre est
  suivi d'un mot que l'application connaît comme nom commun, service,
  activité ou libellé de champ, il reste désormais en place. Les vraies
  indications de localité ne sont pas touchées, y compris celles qui sont
  en même temps un tel mot (« 4692 Ort »). Le cas où un mot tout à fait
  ordinaire suit le nombre (« 3390 Regal ») n'est en revanche pas résolu –
  cela nécessiterait un répertoire des codes postaux.
- **L'aide mentionnait une entrée de menu qui n'existe pas.** Le manuel,
  une image et le message final de l'installation parlaient de
  « Nettoyer le document pour l'IA » ; mais l'entrée du menu contextuel
  s'appelle « Supprimer les données personnelles ». Qui suivait l'aide
  cherchait en vain. Les trois endroits nomment désormais l'entrée de
  menu comme elle s'appelle réellement.
- **« Démarrer avec le système » ne pouvait pas être désactivé.** Qui
  avait coché « Démarrer avec Windows » lors de l'installation voyait
  malgré tout une case vide dans les paramètres – et plus grave : activer
  et désactiver dans l'application restait sans effet, le programme
  continuait à démarrer avec Windows. La cause était deux emplacements où
  Windows recherche les programmes de démarrage ; l'application n'en
  connaissait qu'un seul. Désormais, les deux comptent, l'interrupteur
  affiche l'état réel et agit dans les deux sens. Est également pris en
  compte : qui désactive l'entrée dans le gestionnaire des tâches le voit
  désormais dans l'application – et qui la réactive là-bas annule ainsi
  la désactivation.
- **Des titres au-dessus de listes de noms étaient caviardés.**
  « TEILNEHMERLISTE WERKSTATTGESPRÄCH » ou « MITARBEITERÜBERSICHT
  INNENDIENST » au-dessus d'une liste de personnes disparaissaient comme
  prétendu nom. En majuscules, le modèle de langage manque de son
  meilleur signe de reconnaissance, et en allemand chaque substantif
  s'écrit avec une majuscule – « Teilnehmerliste Werkstattgespräch »
  ressemble alors à « Anna Huber ». Les mots composés en `-liste`,
  `-dienst`, `-gespräch`, `-sitzung` et `-besprechung` restent désormais en
  place. Les mots de base seuls continuent de valoir comme noms : *Liste*
  et *Dienst* sont des noms de famille attestés, *Teilnehmerliste* n'en
  est pas un.
- **Les indications posées à la verticale recevaient un espace réservé
  illisible.** Numéros de dossier en marge de page, initiales du
  responsable près de la reliure, en-têtes de tableau à la verticale : ces
  indications étaient certes trouvées et supprimées, mais l'espace
  réservé sortait de travers sur le texte, compressé à un ou deux points
  et parfois au-delà du bord du papier. Il suit désormais le texte – à la
  verticale, dans une taille lisible et dans le même sens que
  l'indication d'origine. Il en allait de même pour les pages tournées a
  posteriori (texte écrit horizontalement avec rotation de page inscrite,
  comme le livrent certains programmes de sortie) ; là aussi, l'espace
  réservé s'affiche désormais comme on regarde la page. « Sehr geehrte
  Frau Doktor Anneliese Berger » ne donnait que « Anneliese » comme nom –
  « Berger » restait dans le document. Il en allait de même pour tout nom
  avec deuxième prénom (« Frau Anna Maria Berger »). La cause était la
  règle du nom placé après une formule d'appel : elle avait deux
  emplacements de mot, et un titre ou un deuxième prénom consommait le
  premier. Avec « Dr. » cela ne se remarquait jamais – le point brise la
  règle, et le modèle de langage saisissait le nom entier. Désormais les
  titres sont ignorés sans coûter d'emplacement, et le nom peut se
  composer de trois parties. Un rôle placé **après** le nom ne fonctionne
  toujours pas : « Frau Anna Huber Geschäftsführerin » remplace le nom,
  pas le rôle.
