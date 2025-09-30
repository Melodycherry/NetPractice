# Level 8

![level8](https://github.com/Melodycherry/NetPractice/blob/main/img/level8.png)  

### Explications:  

Ici aussi on a 3 reseaux donc on doit eviter les overlap.  
On va garder 240 partout comme il est deja donne en R12 et D1. 

La destination internet est donnee donc on va utiliser celle la pour le premier champs du routeur 1, puis pour tout le reste. 
Mais attention, tout doit etre dans le meme range sans overlap

routeur 1 avec routeur 2  
routeur 2 avec D1  
routeur 2 avec C1  

donc plusieurs IP possible:  
0-15  
16-31  
32-47  
48-63  

Car mask 255.255.255.240 donc /28 donc bloc de 16 