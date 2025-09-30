# Level 7

![level7](https://github.com/Melodycherry/NetPractice/blob/main/img/level7.png)  

### Explications:  

Pour la destination des routes on peut mettre default partout.  
Meme mask partout MAIS attention, on doit changer pour 240 pour eviter overlap. En effet, l'adresse IP d'un reseau ne peut pas overlap avec un autre reseau. Ici ils sont separes par le routeur. 

On a donc 3 network distinct : 
A1 avec route R11 et un range de 1 a 14 
R12 avec R21 et un range de 241 a 254
Et C1 avec route R22 et un range de 65 a 78

Donc on remplit les IP manquantes en fonction des IP donnees et du range dispo. Puis on remplit les routes avec les prochains hop. 