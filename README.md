# WriteUp de l'Hexa CTF v2 2023
# Haagrahppe moi si tu peux

[hagraah]: ./images/hagraah.jpg
![hagraah]

# Généralités
## Portée du WU
Notre équipe n'ayant pas réussis tous les challenges, ce writeup ne couvrira pas l'intégralité des challenges proposés (notamment ceux de fin, et **ALIAS**). Des pistes de réflexion et la solution proposée par d'autres participants seront quand même décrites.

## Schéma de dépendance des challenges
Voici le graph donné par les admin après la fin du ctf. Il résumé les dépendances des différents challenges :

[obsi]: ./images/obsidian.png
![obsi]

# Action Man

[actionman]: ./images/actionman.png
![actionman]

## Hijacking - 100pt

[hijacking]: ./images/hijacking.png
![hijacking]

[hijacking2]: ./images/Hijacking.JPG
![hijacking2]

Nous devons retrouver le lieu qui est pris en photo. Une recherche inversée sur google image nous donne la réponse : Le tribunal judiciaire de Versailles. 

Le flag : HEXA{tribunal judiciaire de versailles}

## Fast and Furious - 100pt

[fastf]: ./images/fastandfurious.png
![fastf]

[fastf2]: ./images/FastandFurious.JPG
![fastf2]

Avec le panneau en premier plan, on retrouve facilement le lieu ou a été pris la photo : Avenue du Capitaine Tarron.

Le flag : HEXA{avenue du capitaine tarron}

## Fly me to the moon - 100pt

[flymeto]: ./images/flymeto.png
![flymeto]

[flymeto2]: ./images/Flymetothemoon.jpg
![flymeto2]

Avec le numéro de vol sur le papier dans l'image fournie, on retrouve le vol sur un site de flight tracking et avec le code IATA, on retrouve que la destination est l'aéroport de Payerne.

Le flag : HEXA{payerne}

## Chocolate - 200pt

[chocolate2]: ./images/chocolate2.png
![chocolate2]

Une photo est fournie, nous devons retrouver ou celle-ci a été prise :

[chocolate]: ./images/Chocolate.png
![chocolate]

Après de longues (très longues) recherches dans différentes villes d'Europe, nous remettons l'énoncé dans son contexte. A ce moment du CTF, les membres de notre équipe sont capables d'identifier d'importe quel lampadaire présent dans une ville européenne et de lister l'intégralité des villes ayant eu un tramway depuis le début du 19ème siècle.

Le titre étant chocolate et la personne que nous cherchons travaillant à Zurich, nous parcourons google image dans cette ville jusqu'à trouver la réponse : Limmatquai

Une méthode plus rapide était apparemment possible en utilisant Yandex, à creuser.

[ocryandex]: ./images/ocryandex.png
![ocryandex]

Le flag : HEXA{limmatquai}

## Tank Engine - 200pt

[tankengine]: ./images/tankengigne.png
![tankengine]

Nous devons trouver une ville qui se situe à 3h07 de la gare de Zurich en prenant un train direct.

Après des recherches sur google (beaucoup) et sur les sites des différentes compagnies de train en europe (énormément), nous remettons en question notre méthode de recherche. Ainsi nous cherchons un outil qui pourrait répondre à notre besoin. 

On tombe très vite sur l'outil Chronotrains, et notamment vers le projet original : https://direkt.bahn.guru/?origin=8503000 qui permet de donner le temps de trajet en train depuis Zurich vers toutes les gares desservies. 
En cherchant sur la carte, on trouve rapidemment la ville de Cadenazzo.

[cadenazzo]: ./images/cadenazzo.png
![cadenazzo] 

Le flag : HEXA{cadenazzo}

## Bonbon - 300pt

[bonbon]: ./images/bonbon.png
![bonbon]

Après la ville de cadenazzo, on apprend que les personnes recherchées ont pris la voiture et le train vers le sud. Nous cherchons un aéroport situé à 142km en voiture de leur cachette actuelle. Une photo nous est fournie avec le challenge. 

[safehouse]: ./images/safehouse.jpg
![safehouse]

Google image nous apprend que cette photo est tirée d'une banque d'image, cette piste de nous avance pas. Par contre, en examinant les métadonnées de la photo, on trouve des coordonnées gps : 35°31'01.8"N 24°01'03.1"E
https://www.google.fr/maps/place/35%C2%B031'01.8%22N+24%C2%B001'03.1%22E/@35.5171667,24.0175278,17z/data=!3m1!4b1!4m5!3m4!1s0x0:0x55acd771075dd3f5!8m2!3d35.5171722!4d24.0175306 

Sur cette ile, on trouve 2 aéroports, l'aéroport d'Héraklion est la bonne distance.

[aeroportgrece]: ./images/aeroportgrece.png
![aeroportgrece]

Le flag : HEXA{nikos_kazantzakis}

## Sovereign city - 300pt

[sovereign]: ./images/sovereign.png
![sovereign]

On reconnait rapidemment dans le texte proposé des identifiants OpenStreetMap. 
On peut directement les chercher en utilisant les endpoint :
- https://www.openstreetmap.org/node/
- https://www.openstreetmap.org/way/
- https://www.openstreetmap.org/relation/

On trouve la première cachette dans le quartier de Hougang. 

[hougang]: ./images/hougang.png
![hougang]

Pour la deuxième partie, la relation nous donne un croisement sur l'autoroute. Le point d'avant étant à l'est, on arrive sur ce croisement par la droite, et en suivant à chaque fois la voie de gauche on sort de Singapour par le nord et on arrive dans la ville de Johor Bahru.

[johor]: ./images/johor.png
![johor]

Le flag : HEXA{hougang_johorbahru}

## Original - 300pt

[original]: ./images/original.png
![original]

Challenge assez spécial, car nous n'avons qu'une seule tentative. La méthode que nous avons utilisé à été de comparer les fichiers manuellement, d'analyser les différences entre les 12 fichiers et d'estimer lequel aurait pu être écrit par un humain. Une image résume bien le temps passé à faire cela :

[boubou]: ./images/boubou.png
![boubou]

Notre méthode ne nous à pas permis de réussir ce challenge. 

Deux méthodes ont été proposées après la fin du CTF :
- utiliser un détecteur de ChatGPT : https://detector.dng.ai/
- le bon fichier était le seul encodé en ASCII

## Final Countdown - 400pt

[finalcount]: ./images/finalcount.png
![finalcount]

Dernière étape de la branche Action Man. On peut extraire les informations suivantes de la description :
Nous cherchons une "zone 4", située surement en Malaisie.
Dans cette zone 4, nous cherchons un building situé à plus de 3km de la mer, à 5 minutes à pied d'un terrain de foot et proche d'un lieu de culte. 
Le flag à soumettre est l'identifiant d'un noeud OpenStreetMap. Nous n'avons que 3 tentatives pour réussir

Après quelques heures de recherche (et 2 essais loupés), nous nous rappelons que le challenge xxxxx sur la branche The Lawyer nous a fourni un fichier kmz, qui peut s'ouvrir avec google earth. Dans ce fichier, 10 zones numérotées de 1 à 10. La zone 4 est celle ci :

[zone 4]: ./images/zone4.png
![zone 4]

On peut donc restreindre la zone de recherche à cette région de la Malaisie.
Pour effectuer la recherche, on utilise https://overpass-turbo.eu, qui permet de faire des queries sur la base de donnée OSM.

Après plusieurs essais infructeux, la requête suivante permet de trouver un noeud unique : 

[ot 1]: ./images/OT.png
![ot 1]

Cette query cherche les noeuds OSM ayant un tag "building", les terrains de football et les côtes maritimes. Ensuite, on ne garde que les noeuds qui sont à moins de 500m d'un terrain de football. Puis on cherche les batiments qui sont à moins de 3km des côtes. Enfin, on récupère les buildings proches d'un terrain de foot en excluant ceux proches des côtes.

Et nous trouvons le building suivant :

[flag]: ./images/mosquee.png
![flag]

Le flag final est donc : HEXA{3975813161}

# The Intruder

[intruder]: ./images/intruder.png
![intruder]

## The Intruder - 100pt
[theintruder]: ./images/theintruder.png
![theintruder]

Première grosse difficulté du CTF pour notre équipe, et premier exemple de la phrase : "lisez l'énoncé"

Nous trouvons vite sur google le nom du détective : Allan Pinkerton.

Après de nombreux dorks google & youtube, avoir parcouru et testé les IDs de toutes les chaines mentionnant notre cher Allan, un membre de l'équipe relis l'énoncé et nous dis : "he could be among you", quelqu'un a regardé sur le discord ? Fausse piste, mais il n'était pas très loin, car on trouve un Mr Allan Pinkerton sur le site de l'HEXA :

[pinkerton]: ./images/pinkerton.png
![pinkerton]

On peut donc valider le challenge avec le flag : HEXA{UCjyLqrOsjkpsMhczlbHJoFA}

## Infiltration - 100pt

[infiltration]: ./images/Infiltration.png
![infiltration]

En parcourant la chaine youtube trouvée précédemment, on trouve un identifiant tiktok dans la vidéo : https://www.youtube.com/shorts/nhh7Z8gnDmA

Sur ce tiktok, un identifiant de serveur discord :

[discordpink]: ./images/discordpink.png
![discordpink]

Pour avoir une invitation, on clique sur le lien : https://discord.gg/unsb62pMc7

Le flag est présent sur le channel d'arrivée :

[flaginfil]: ./images/flaginfilt.png
![flaginfil]

Le flag : HEXA{P1nk3Rt0n_solV1n9_C4s3}

## Sneak Beak - 200pt

[sneakbeak]: ./images/sneakbeak.png
![sneakbeak]

La première étape en arrivant sur le discord est d'obtenir le rôle Cheveche. On comprend que les noms de rôle sont liés aux chouettes, donc on clique sur l'émoji chouette.

Cela nous donne accès à un nouveau channel, qui décrit de nouveau challenges : 

[cheveche]: ./images/cheveche.png
![cheveche]

### Challenge 1
Pour le Challenge 1, nous disposons d'un enregistrement ou on entend une personne chantonner. Nous pouvons faire écouter cet enregistrement à google Assistant qui nous permet de trouver la musique : Lemonade du groupe Bonobos.

### Challenge 2
Pour le challenge 2, on retrouve l'article du code pénal français concernant le vol d'identité.

A chaque fois, on envoie les réponses à un bon qui nous renvoie des morceaux de commandes afin d'obtenir le rôle suivant

Le flag est : HEXA{!yxmdvbn5jvwnnjy3htfe}

## Grow Owlder - 300pt

[growowlder]: ./images/growowlder.png
![growowlder]

Nous avons accès à un nouveau channel discord :

[hulotte]: ./images/hulotte.png
![hulotte]

### Challenge 3
Pour le challenge 3, on doit trouver l'article du rgpd concernant le droit à l'oubli.

### Challenge 4
Pour le challenge 4, on doit trouver le pourcentage d'inflation sur le prix des oeufs entre Octobre et Novembre 2022. On trouve la réponse sur ce site : https://www.bls.gov/news.release/cpi.t02.htm 

### Challenge 5
Enfin pour le challenge 5, nous avons passé une bonne partie de la nuit à cherches des webcam dans la région du Veneto sans succès. Un indice a été rajouté samedi matin, ce qui nous a permis de rappidemment trouver la caméra concernant à travers les résultats de google image : https://www.youtube.com/watch?v=rcm6kmLUggg

Le flag : HEXA{!z7i2vj2ger6vfpjje2dd}

## Tell me owl your secrets - 600pt

[tellmeowl]: ./images/tellmeowl.png
![tellmeowl]

Nous avons accès à un nouveau channel discord :

[effraie]: ./images/effraie.png
![effraie]

### Challenge 7
Pour le challenge 7, il suffit d'activer le mode développeur de discord et de faire un clic droit sur le compte de J. pinkerton ce qui nous donne son ID Discord.

### Challenge 8
Pour le challenge 8, nous avons accès à une vidéo qui nous donne 2 indices :
- La suite de caractères 9E:A9:75
- Le site web d'une société s'appelant Draytec

Nous cherchons le SSID d'une société de l'industrie médicale.

La chaîne de caractère fait penser à la moitié d'une adresse MAC.
Grâce au writeup de l'HEXAv1, nous avons connaissance d'un outil qui permet de trouver des SSID en fonction d'adresses MAC : Wigle. 
Mais nous ne pouvons pas faire de recherches avec une adresse MAC partielle, il faut donc trouver la première partie.

Pour cela, on utilise le site web de Draytec. Cette société fabrique notamment des routeurs wifi. Après quelques recherches, on apprend que les 3 premiers blocs de l'adresse MAC d'un routeur est fixe au constructeur. 
Il y en a 3 pour Draytec, ce qui nous permet de trouver la réponse avec Wigle avec l'adresse : 00:1D:AA:9E:A9:75

### Challenge 6
Pour le challenge 6, Tsuzune Yokoyama aura eu raison de nous. Malgré une trentaine d'heures de recherche, nous n'avons pas réussi à trouver son profil. Nos différentes pistes : dorks google, twitter, recherches sur des réseaux connus, recherches sur des moteurs de recherches asiatique, recherches en katakana et kanji, etc

Nous apprendrons qu'il fallait le chercher sur Line, réseau le plus utilisé au Japon. Piste que nous avons essayée, mais abandonnée trop vite.

Cette branche s'arrête donc la pour nous.

# The Lawyer

[thelawyer]: ./images/thelawyer.png
![thelawyer]

## The law firm - 100pt

[lawfirm]: ./images/lawfirm.png
![lawfirm]

On trouve rapidemment le site web du cabinet d'avocats Nelexat à l'url : https://nelexat.ch

Dans le footer de la page, on trouve le flag : HEXA{N3l3x4t_w1ll_M4ke_You_R1ch}

Valider ce challenger débloque la branche [The Developer](#the-developer)

## The lawyer - 200pt

[lawyer]: ./images/thelawyer2.png
![lawyer]

En lisant l'intégralité de la page des termes et conditions du site Nelexat, on trouve le nom du propriétaire du cabinet : Lian Nussbaumer. Comme on cherche une information concernant ses études, on peut regarder sur LinkedIN. On trouve son profil et on récupère le flag : HEXA{neuchatel}

## Alias - 100pt

[alias]: ./images/alias.png
![alias]

Ce challenge nous aura tenu en haleine tout le week end, et nous n'avons jamais trouvé la réponse. 
Pour commencer, il fallait trouver un alias utilisé par notre avocat. En parcourant ses posts LinkedIN, on trouve une photo pour une prochaine conférence avec son nom et le pseudo Nelexlian

Malgré de nombreuses recherches avec whatsmyname.app ou d'autres outils, avec son nom et/ou son pseudo, rien n'a porté ses fruits.

Nous apprendrons après la fin qu'il fallait trouver son compte sur la plateforme etoro. Pas de méthode magique, il fallait parcourir les plateformes de trading les plus connues.

## Trustworthy - 200pt

[trust]: ./images/trustworthy.png
![trust]

En cherchant un peu, et en s'aidant du nom du challenge, on remarque que la connection au site de Nelexat n'est pas sécurisée. Une adresse mail est présente dans le certificat.

Le flag : HEXA{mastermind_mastermind@proton.me}

## Herbaceous - 200pt

[herba]: ./images/Herbaceous.png
![herba]

Le point de départ est l'adresse mail trouvée auparavant. Nous avons utilisé l'outil ghunt qui permet de trouver des informations sur un compte google. Lorsqu'on lance ghunt sur l'adresse mail, on trouve un calendrier public avec un événement :

[cal]: ./images/cal.png
![cal]

A l'intérieur de ce calendrier, un lien vers un site en .onion. Lorsqu'on visite ce site, on peut trouver le flag en inspectant le code source de la page.

Le flag : HEXA{N3l3x4t_is_L1nk3d_to_M4stermind}

En cliquant sur l'image, on trouve une autre page donnant un fichier qui nous sera utile pour le challenge [Final countdown](#final-countdown---400pt)

## Good time - 100pt

[goodtime]: ./images/goodtime.png
![goodtime]

Pour cette partie, nous avons découvert qu'en ouvrant l'invitation trouvée précédemment sur la page web google calendar puis en cliquant sur plus d'infos, on obtenait aussi la liste des adresses mail qui avaient été invitées. 

En recherchant notamment mincah_mm dans whatsmyname, on trouve un compte tripadvisor, ayant un unique avis. 

Le flag : HEXA{kaufleuten}

## Experts - 200pt

[expert]: ./images/experts.png
![expert]

Sur le site web de Nelexat, on peut trouver un lien écrit en blanc sur blanc qui concerne une route API FastAPI. Deux endpoints sont disponibles, dont le premier qui demande un nom de client. En utilisant le nom de famille de Lucilhe Dumarquais qui est donné au début du CTF, on récupère le flag : HEXA{s3cure_y0ur_d4mn_4p1}

## Decentralized - 200pt

[decentra]: ./images/decentralized.png
![decentra]

Sur le site de mastermind trouvé précédemment, on peut voir une adresse ETH. En la cherchant sur un site d'exploration de blockchain (etherscan.io par exemple), on trouve une transaction datant d'il y a un mois. Quand suit les informations sur cette transactions, on voit des datas associées :

[bruised]: ./images/bruised.png
![bruised]

En utf-8, on trouve le nom de la mission recherchée.

Le flag : HEXA{bruised_rogue}

## Kanagawa - 300pt

[kanagawa]: ./images/kanagawa.png
![kanagawa]

En cherchant l'adresse ETH du challenge précédent sur la plateform Opensea, on trouve un profil associé avec le flag dans sa description : HEXA{n1ce_L0g0_br0}

# The Developer

[developer]: ./images/developper.png
![developer]

## Programming - 100pt

[programming]: ./images/programming.png
![programming]

Pour résoudre ce challenge, il faut trouver le .git sur le site web de Nelexat. Dans /config on trouve le profil github du développeur : https://github.com/ovokolska.

Le flag : HEXA{https://github.com/ovokolska}

## Listen to your heart - 200pt

[listentoyour]: ./images/listentoyour.png
![listentoyour]

On voit sur le github trouvé précédemment une unique star vers un projet Mastodon. Dans la description du profil, on voit un autre pseudo potentiel : littlesparr0w. On cherche le nom d'utilisateur dans Mastodon, et on trouve le profil suivant : https://cyberplace.social/@littlesparr0w. 

On pouvait aussi utiliser whatsmyname.app avec le pseudo littlesparr0w.


En descendant les posts, on trouve le flag : HEXA{mY_H34R7_i5_pURp13}

# The associate

[theassociate]: ./images/theassociate.png
![theassociate]

## Contract - 200pt

[contract]: ./images/contract.png
![contract]

Nous avons une image associée :

[contract2]: ./images/Contract.jpg
![contract2]

Avec google image, on peut retrouver la compagnie aérienne grace au couleur des ailes : corsaire airlines. 
Puis nous avons survolé les différents aéroports pour retrouver la marque rouge au sol. Après un passage à la réunion qui ne convenait pas, on trouve juste à côté mauritius, dont l'aéroport rempli tous les critères.

Le flag : HEXA{mauritius}

## Impersonator - 200pt

[imperso]: ./images/impersonnator.png
![imperso]

Ce challenge a été résolu plutôt rapidemment avec les informations fournies dans l'énoncé.
On trouve le flag : HEXA{chelsea}

## Setup - 300pt

[setup]: ./images/setup.png
![setup]

On nous donne une photo : 

[setup2]: ./images/setup.jpeg
![setup2]

Une recherche inversée dans google image nous donne directement le modèle de la montre.

Le flag : HEXA{F20286/3}

# Sidequest

[sidequest]: ./images/sidequest.png
![sidequest]

## He is back - 300pt

[heisback]: ./images/heisback.png
![heisback]

On trouve rapidemment la page wikipédia de https://en.wikipedia.org/wiki/Kermit_Roosevelt_III en cherchant les mot clés sur google. On trouve sur sa page le nom de sa deuxième nouvelle. 
On utilise de nouveau des dorks google pour trouver une interview ou il parle de cette nouvelle et ou notamement il cite un acteur qu'il verrait bien jouer le rôle de son personnage au cinéma. 

Le flag : HEXA{joseph gordon-levitt}

## He is back 2 - 300pt

[heisback2]: ./images/heisback2.png
![heisback2]

Nous n'avons pas réussi ce challenge. La méthode était d'utiliser des dorks google pour tomber sur le bon nom scientifique.