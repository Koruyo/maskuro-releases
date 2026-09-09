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
