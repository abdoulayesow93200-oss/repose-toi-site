# repose-toi-site

Page vitrine statique de Repose Toi, servie par GitHub Pages.

Elle remplace l'ancien site Base44 (`repose-toi.com`), suspendu pour defaut de
paiement et qui repondait `HTTP 402 Repose Toi is currently unavailable`.

## Raison d'etre

Le QR code des flyers imprimes pointe sur `https://repose-toi.com/Download`.
Cette adresse ne peut pas changer : le site doit donc la servir telle quelle.

## Structure

| Chemin | Role |
| --- | --- |
| `index.html` | Accueil : logo, boutons des deux stores, contact support, politique de confidentialite |
| `Download/index.html` | L'URL exacte du flyer. Redirige iPhone vers l'App Store, Android vers le Play Store ; sur ordinateur, affiche les deux boutons |
| `telecharger/index.html` | Copie de la precedente |
| `404.html` | Aiguilleur : rattrape `/download` et `/telecharger` en minuscules, et renvoie toute autre ancienne URL vers l'accueil |
| `assets/logo.png` | Icone de l'application, reduite a 256 px |
| `.nojekyll` | Desactive Jekyll |

## Pourquoi /download en minuscules passe par 404.html

GitHub Pages distingue les majuscules des minuscules dans les chemins, mais le
disque de travail (macOS, APFS insensible a la casse) ne permet pas d'avoir
`Download/` et `download/` cote a cote dans le meme depot. `404.html` couvre donc
toutes les variantes de casse, en JavaScript. L'URL du flyer, `/Download`, reste
servie en 200 par un vrai fichier.

## Fichier CNAME

Volontairement absent pour l'instant. Il sera ajoute (`repose-toi.com`) juste
avant le basculement DNS chez Namecheap : tant qu'il est la, GitHub cherche a
emettre un certificat pour un domaine qui ne pointe pas encore ici.

## Test sans partir sur le store

Ajouter `?noredirect=1` a l'URL desactive la redirection automatique.

## Contact

support.reposetoi@gmail.com
