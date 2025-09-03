# NETPRACTICE

## Sources :   
GITHUB:  
https://github.com/lpaube/NetPractice  
https://github.com/tblaase/Net_Practice?tab=readme-ov-file  

Medium:   
https://medium.com/@imyzf/netpractice-2d2b39b6cf0a  
https://toufa7.medium.com/netpractice-guidelines-6341b8309f38  
https://toufa7.medium.com/new-subnetting-34fadfb86c70  

GITBOOK:  
https://42-cursus.gitbook.io/guide/4-rank-04/netpractice/theory  

Video:  
https://www.youtube.com/watch?app=desktop&v=HQUw0CfQWAM&t=0s  
https://www.youtube.com/watch?v=OTwp3xtd4dg  

Other:  
https://www.codequoi.com/architecture-du-reseau-internet/  
https://www.codequoi.com/adresses-ipv4-routage-et-masques-de-sous-reseau/  
http://sdz.tdct.org/sdz/apprenez-le-fonctionnement-des-reseaux-tcp-ip.html  


## Résumé de prise de note   
### *Compte rendu : Internet, Réseaux et Protocoles*

## 1. Internet et son architecture
- Internet est **un réseau de réseaux** : il relie des milliers de réseaux publics et privés à l’échelle mondiale.  
- Les **Fournisseurs d’Accès à Internet (FAI/ISP)** sont eux-mêmes des réseaux interconnectés.  
- Le rôle principal d’Internet est de permettre à des **hôtes** (hosts) — ordinateurs, smartphones, serveurs, etc. — de communiquer entre eux.

### Les hôtes
- Un **hôte** est tout système connecté au réseau.  
- Deux grandes catégories :
  - **Clients** : terminaux (PC, smartphone, console, etc.).  
  - **Serveurs** : machines qui stockent et distribuent du contenu (pages web, vidéos, emails…).  

---

## 2. Transmission des données
- Lorsqu’un hôte envoie des données à un autre :  
  1 Les données sont **découpées** en petits morceaux.  
  2. Chaque morceau est encapsulé avec des **en-têtes** (headers) → on obtient un **paquet**.  
  3. Les paquets circulent via différents supports physiques (câbles cuivre, fibre optique, ondes radio…).  
  4. Le destinataire **réassemble** les paquets pour reconstruire le message.  

---

## 3. Composants physiques du réseau

### Switch (commutateur réseau)
- Relie plusieurs appareils dans un même **LAN** (Local Area Network).  
- Reçoit un paquet et l’envoie uniquement à l’appareil destinataire.  
- Plus intelligent qu’un hub, car il apprend les adresses (MAC) des machines connectées à ses ports.  
Exemple : dans une salle avec 10 ordinateurs, si PC1 envoie un fichier à PC3, seuls ces deux ordinateurs échangent les données.

### Router (routeur)
- Relie différents réseaux (par exemple, ton réseau domestique au réseau de ton FAI).  
- Détermine le **meilleur chemin** pour envoyer les données entre réseaux.  
- Un routeur possède souvent plusieurs interfaces réseau (une par connexion).  
Exemple : ta box Internet chez toi est un routeur.

### Gateway
- Sert de **point d’entrée et de sortie** d’un réseau.  
- Différence :
  - **Router** : choisit la route entre plusieurs réseaux.  
  - **Gateway** : permet la communication entre réseaux qui utilisent des protocoles différents.  

### Network Node (nœud de réseau)
- Tout appareil connecté au réseau capable d’envoyer, recevoir ou transférer des données.  
- Exemples : PC, smartphone, imprimante, switch, routeur…

---

## 4. Routage
- Le **routage** est le processus de sélection du chemin que les données empruntent pour aller de la source à la destination.  
- Réalisé par les **routeurs** grâce à leurs **tables de routage** et à des algorithmes.  
- Exemple : un email envoyé de Genève à Tokyo traverse plusieurs routeurs intermédiaires, chacun choisissant le prochain saut optimal.

---

## 5. Adressage IP et sous-réseaux

### IPv4
- Adresse sur **32 bits**, représentée par 4 octets (ex : 192.168.1.1).  
- Constituée de deux parties :
  - **Network portion** : identifie le réseau.  
  - **Host portion** : identifie l’hôte dans ce réseau.  

### Plages spéciales
- **Private networks** (réservés pour usage interne) :
  - 10.0.0.0 – 10.255.255.255  
  - 172.16.0.0 – 172.31.255.255  
  - 192.168.0.0 – 192.168.255.255  
- **Loopback** : 127.0.0.1 → "localhost", pour tester sur soi-même.  
- **0.0.0.0** = absence d’adresse.  
- **255.255.255.255** = broadcast global.  

### Subnet & Subnet mask
- Un **subnet** est une division logique d’un réseau plus grand.  
- Le **subnet mask** (ex : 255.255.255.0 ou /24 en notation CIDR) définit quelle partie de l’adresse IP correspond au réseau et laquelle correspond à l’hôte.  
- Deux adresses sont toujours réservées :
  - Première adresse = **adresse réseau**.  
  - Dernière adresse = **broadcast**.  
- Les adresses utilisables se situent entre ces deux bornes.  

### CIDR (Classless Inter-Domain Routing)
- Permet un **découpage flexible** des adresses IP, contrairement aux anciennes classes (A, B, C).  
- Exemple : 192.168.42.0/26 → plage utilisable 192.168.42.1 à 192.168.42.62.  

---

## 6. TCP/IP et les protocoles

### IP (Internet Protocol)
- Assure l’**adressage** et le **routage** des paquets.  
- Fonctionne comme une **adresse postale**.  
- Ne garantit pas la livraison.

### TCP (Transmission Control Protocol)
- Assure la **fiabilité** des transmissions :
  - Découpe en segments.  
  - Numérote les morceaux.  
  - Vérifie l’intégrité et redemande les paquets perdus.  
- Résultat : données reçues **complètes et dans l’ordre**.  

Ensemble, **TCP/IP** est la fondation d’Internet.  

### UDP (User Datagram Protocol) (à connaître aussi)
- Moins fiable que TCP (pas de vérification ni de retransmission).  
- Plus rapide → utilisé pour la vidéo en streaming, le gaming, la voix sur IP.

---

## 7. Modèle en couches

### TCP/IP Model
1. **Physical** : transmission physique (câbles, radio…).  
2. **Data Link** : communication locale (Ethernet, switch).  
3. **Network** : adressage et routage (IP, routeur).  
4. **Transport** : ports et fiabilité (TCP, UDP).  
5. **Application** : logiciels de l’utilisateur (HTTP, FTP, email…).  

### Encapsulation / Décapsulation
- Chaque couche ajoute son en-tête → encapsulation (Message → Segment → Packet → Frame → Bits).  
- À la réception, chaque couche retire son en-tête → décapsulation.  

---

## 8. Autres éléments matériels
- **Modem** : convertit le signal analogique (ligne téléphonique, fibre, câble coaxial) en signal numérique compréhensible par le réseau.  
- **Différence modem / router** :
  - Modem : connecte un seul appareil à Internet.  
  - Router : connecte plusieurs appareils entre eux (LAN).  
  - Une **box Internet** combine généralement modem + routeur.  

---

## 9. Synthèse rapide
- **Switch** : connecte plusieurs appareils dans un même réseau local (LAN).  
- **Router** : connecte plusieurs réseaux entre eux.  
- **Gateway** : point d’entrée/sortie entre réseaux.  
- **Node** : tout appareil connecté au réseau.  
- **IP** : adresse de communication unique pour chaque interface réseau.  
- **Subnet mask** : délimite la partie réseau et la partie hôte d’une IP.  
- **TCP/IP** : protocole de base d’Internet (IP = acheminement, TCP = fiabilité).  
- **Modem** : connexion physique à Internet.  
- **Encapsulation** : ajout d’en-têtes successifs par les couches réseau.  
