layout: true
# Sortir de Google

---
class: middle, center
De la réappropriation de ses données.

---
## Léo Peltier
<img class="float-left" src="./avatar.png" alt="avatar" height="100" />
<img class="float-right" src="./boaterfly.png" alt="logo Boaterfly" height="100" />

- CTO @ Boaterfly, location de bateau en p2p
- Rockstar ninja artisan code crafter .lowcontrast[/s]
- Libriste modéré
- **Paranoïaque pragmatique**

---
## Pourquoi&nbsp;?
.half[<img alt='"There is no cloud."' src="./cloud.png" height="200" />]

* Centralisation == <abbr title="Single Point of Failure">SPOF</abbr>
* Cloud == <q>someone else's computer</q>
* Retour à la vie privée
* Contrôle absolu sur les données
* <abbr title="Free and open-source software">FOSS</abbr> ≥ le reste

???
"There is no cloud" sticker &copy; Chris Watterston
https://www.stickermule.com/marketplace/3442-there-is-no-cloud

---
## Les services

* Agenda
* Contacts
* Drive
* Google Play Services (Android)
* Google+
* Hangouts
* Mail
* Map
* Play Music
* Recherche

---
background-image: url("radicale_back.png")
class: background-image-bottom-right
## Agenda/Contacts &rightarrow; Radicale

- Serveur CardDAV/CalDAV (vCard/iCal)
- Dans debian ≥ oldstable (wheezy)
- Excellente documentation
- Compatible avec Android, iOS, Windows Phone, Thunderbird, etc.


.cons[
- .con[Pas d'interface web]
]
.pros[
- .pro[Multi-utilisateur, hautement configurable]
- .pro[Possibilité de tout versionner dans git]  
.lowcontrast[(Ça remplace pas une sauvegarde.)]
]

???
Un serveur \*DAV n'est pas quelque chose vous avez envie d'implémenter vous-même.

> The Radicale Server does not and will not support the CalDAV and CardDAV
> standards. It supports the CalDAV and CardDAV implementations of different
> clients (Lightning, Evolution, Android, iPhone, iCal, and more).
>
> http://radicale.org/technical_choices/

---
background-image: url("radicale_back.png")
class: background-image-bottom-right
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
