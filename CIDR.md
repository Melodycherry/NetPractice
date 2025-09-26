# Explication CIDR  

## 1️⃣ Notation CIDR : `/n`

- Le `/n` indique **combien de bits sont utilisés pour le réseau** dans une adresse IP.  
- Une adresse IPv4 = **32 bits** → divisée en 4 octets (8 bits chacun).  
- Exemple : `192.168.1.0/24`  
  - `/24` → **24 bits pour le réseau**, 8 bits pour les hôtes.  

**Formule générale** :  
- Nombre d’adresses totales dans le sous-réseau = `2^(32 - n)`  
- Plage d’hôtes utilisables = total - 2 (réseau + broadcast)

  
## 2️⃣ Exemple `/25`

- `/25` → 25 bits réseau → 32 - 25 = 7 bits pour les hôtes  
- Nombre total d’adresses = 2^7 = 128  
- Plage utilisable : 128 - 2 = 126 hôtes  
- Masque : `255.255.255.128`  


**Exemple pratique :**

Réseau : `79.229.133.128/25`  

| Type                     | Adresse           |
|---------------------------|-----------------|
| Réseau                    | 79.229.133.128  |
| Première IP utilisable    | 79.229.133.129  |
| Dernière IP utilisable    | 79.229.133.254  |
| Broadcast                 | 79.229.133.255  |



## 3️⃣ Exemple `/28`

- `/28` → 28 bits réseau → 32 - 28 = 4 bits pour les hôtes  
- Nombre total d’adresses = 2^4 = 16  
- Plage utilisable = 16 - 2 = 14 hôtes  
- Masque : `255.255.255.240`  


**Exemple pratique :**

Réseau : `163.172.250.0/28`  

| Type                     | Adresse           |
|---------------------------|-----------------|
| Réseau                    | 163.172.250.0   |
| Première IP utilisable    | 163.172.250.1   |
| Dernière IP utilisable    | 163.172.250.14  |
| Broadcast                 | 163.172.250.15  |



## 4️⃣ Résumé

| CIDR   | Masque           | Nombre total IP | Plage utilisable |
|--------|-----------------|----------------|----------------|
| /25    | 255.255.255.128 | 128            | 126            |
| /28    | 255.255.255.240 | 16             | 14             |
| /24    | 255.255.255.0   | 256            | 254            |



### à retenir

1. Ne jamais assigner l’**adresse réseau** ou **broadcast** à une machine.  
2. La **passerelle** (gateway) doit être une adresse **dans la plage utilisable**.  
3. CIDR plus grand (`/28`) → réseau plus petit, moins d’hôtes.  
4. CIDR plus petit (`/25`) → réseau plus grand, plus d’hôtes.  

