# Level 5

![level5](https://github.com/Melodycherry/NetPractice/blob/main/img/level5.png)  

### Explications:  

Dans cet exemple on a une route qui a deux champs :  
- la premiere est la destination
- la deuxieme est le prochain "hop" ( saut de paquet ? )  


Destination par defaut : 0.0.0.0/0 est la meme chose que "default"  

Quand c'est default, il envoie a la premiere adresse reseau qu'il rencontre.  
Le "prochain saut" est l'adress IP du prochain routeur ( ou internet ), donc la ou on doit envoyer le paquet.  
Ici cela signifique que c'est la meme adresse que interface R1  

Pour le reste a remplir, meme regles : meme mask et meme sous reseau dans le range dispo. 