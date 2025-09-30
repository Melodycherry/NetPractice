# Level 2

![level2](https://github.com/Melodycherry/NetPractice/blob/main/img/level2.png)  

### Explications:  

Pour A et B, ils doivent avoir le meme mask.  
Ici le mask donne est de 255.255.255.224, donc le range pour l'adresse IP est de 192 - 223 ( sauf 222 deja utilisee).  

Pour C et D la notation /30 est egale a 255.255.255.252   

Attention : l'adresse 127.0.0 ... deja donnee est reservee au local host donc on ne peut pas l'utiliser.   
Si on garde 127 on empeche la communication entre elle. Donc on doit remplacer par une adresse non loop-back et utiliser le meme sous reseau.  
On peut utiliser n'importe quelle adresse qui ne cree pas de conflit avec un sous reseau existant. Donc le sous reseau suivant par exemple.  