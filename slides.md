layout: true
# Sortir de Google

---
class: middle, center
De la réappropriation de ses données.

---
## Léo Peltier
<img class="float-left" src="./avatar.png" alt="avatar" height="100" />

- Rockstar ninja artisan code crafter .lowcontrast[/s]
- Libriste modéré
- **Paranoïaque pragmatique**

---
## Pourquoi&nbsp;?
.half[<img alt='"There is no cloud."' src="./cloud.png" height="200" />]

* Centralisation == <abbr title="Single Point of Failure">SPOF</abbr>
* Cloud == <q>someone else's computer</q>
* <abbr title="Free and open-source software">FOSS</abbr> ≥ le reste
* Retour à la vie privée
* Contrôle absolu sur les données

???
"There is no cloud" sticker &copy; Chris Watterston
https://www.stickermule.com/marketplace/3442-there-is-no-cloud

---
## Les services

* Agenda
* Android (Google Play{, Services})
* Contacts
* Drive
* ~~Google+~~
* Hangouts
* Mail
* Map
* Play Music
* Recherche

---
background-image: url("./radicale_back.png")
class: background-image-right
## Agenda/Contacts &rightarrow; Radicale

- Serveur CardDAV/CalDAV (vCard/iCal)
- Dans debian ≥ oldstable (wheezy)
- Excellente documentation
- Compatible avec Android, iOS, Windows Phone, Thunderbird, etc.

.pros[
- Multi-utilisateur, hautement configurable
- Possibilité de tout versionner dans git  
.lowcontrast[(Ça ne remplace pas une sauvegarde.)]
]
&nbsp;
.cons[
- Pas d'interface web
]

???
Un serveur \*DAV n'est pas quelque chose vous avez envie d'implémenter vous-même.

> The Radicale Server does not and will not support the CalDAV and CardDAV
> standards. It supports the CalDAV and CardDAV implementations of different
> clients (Lightning, Evolution, Android, iPhone, iCal, and more).
>
> http://radicale.org/technical_choices/

DAVdroid est nécessaire sous Android.

---
background-image: url("./radicale_back.png")
class: background-image-right
## Configurer Radicale
```bash
sudo apt install radicale
```

```bash
# /etc/default/radicale
ENABLE_RADICALE=yes
```

```ini
# /etc/radicale/config
[server]
base_prefix = /
hosts = 127.0.0.1:5232

[storage]
# Value: filesystem | database
#type =

# Example: postgresql://user:password@localhost/radicale
#database_url =
```

???
`proxy_pass` à faire ensuite dans nginx auquel on délèguera la gestion du
chiffrement TLS et de l'authentification HTTP.

---
background-image: url("./syncthing.png")
class: background-image-right, hide-count
## Drive &rightarrow; Syncthing
<img src="./syncthing_screen.png" alt="capture d'écran syncthing" class="bottom-half" />

???
Drive mais pas que, Dropbox même combat.

---
background-image: url("./syncthing.png")
class: background-image-right
## Syncthing
.pros[
- Distribué (à la BitTorrent)
- Chiffré
- Disponible sur GNU/Linux, Windows, Mac OS X, Android, \*BSD, etc.
- Qualité du code, de la documentation et des spécifications
- Juste ça marche.&trade;
]
&nbsp;
.cons[
- J'en ai pas trouvé
]

???
Versionnement (_trashcan_, outil externe), association bidirectionelle, mode
_introducer_.

---
background-image: url("./fdroid.png")
class: background-image-right
## Google Play &rightarrow; F-Droid
<img src="./fdroid_screen2.png" alt="capture d'écran fdroid" class="float-left" />
<img src="./fdroid_screen.png" alt="capture d'écran fdroid" class="float-left" />

---
## Google Play Services &rightarrow; microG
<blockquote cite="https://microg.org">A free-as-in-freedom re-implementation of Google’s proprietary Android user space apps and libraries.</blockquote>

???
GMS est le trojan officiel d'Android. Se met à jour silencieusement, a toutes les
permissions sur le device.

---
background-image: url("./cyanogen.png")
class: background-image-right
## Android &rightarrow; CyanogenMod

.pros[
- Compatible avec **beaucoup** de téléphones
- Seul moyen d'avoir un système à jour
- FOSS en majorité
]
&nbsp;
.cons[
- Nightlies instables (duh)
- Pas installable par madame Michu
- Installation des _Google Play Services_ un peu pénible
]

???
Basé sur <abbr title="Android Open Source Project">AOSP</abbr>

Voir aussi Replicant (basé sur CyanogenMod, approuvé par la <abbr title="Free
Software Foundation">FSF</abbr>)

---
## Maps &rightarrow; OsmAnd~
<img src="./osmand_screen.png" alt="capture d'écran OsmAnd" class="float-left" />
<img src="./osmand_screen2.png" alt="capture d'écran OsmAnd" class="float-left" />

---
background-image: url("./osm.png")
class: background-image-right
## Maps &rightarrow; OsmAnd~
.pros[
- Utilisable sans connexion
- Exhaustif
]
&nbsp;
.cons[
- Nécessite un téléphone puissant
- Recherche et navigation pas optimales
]

---
## Le reste 1/2
1. ### Google Play Music
    Sortir du streaming sans entrer dans l'illégalité est difficile.

    Mopidy pourra être utilisé quand il pourra être utilisé en tant que serveur de
    streaming.

2. ### Hangouts
    Certainement pas Skype.

---
## Le reste 2/2
1. ### Recherche
    Probablement DuckDuckGo, Google reste ancré dans mes habitudes.

2. ### Gmail
    Vaste choix.

---
## … c'est fait

Pour aller plus loin&nbsp;:
- CHATONS, Framasoft, Dégooglisons Internet  
  https://degooglisons-internet.org/

- Les slides&nbsp;: https://l-p.github.io/out-of-google/

- <img src="./google.png" alt="google search" class="middle" />

???
Collectif d’Hébergeurs Alternatifs, Transparents, Ouverts, Neutres et Solidaires
