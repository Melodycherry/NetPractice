# Level 6

![level6](https://github.com/Melodycherry/NetPractice/blob/main/img/level6.png)  

### Explications:  

Ici on a internet. Internet fonctionne comme un routeur. Mais attention aux adresses privees :
- 10.0.0.0 - 10.255.255.255  
- 172.16.0.0 - 172.31.255.255 
- 192.168.0.0 - 192.168.255.255

Internet doit communiquer avec interface A1, donc le premier champs (internet destination) doit etre adresse IP de l'interface A1. 
On doit egalement mettre le meme mask, donc ici 128 en CIDR est equivalent a /25  