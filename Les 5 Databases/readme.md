# Hello world

# TL;DR
* Ga naar ma-hosts
* Maak daar een nieuwe database aan
* Maak een table met de volgende columns:
    * id: INT UNIQUE
    * name: VARCHAR(20)
    * score: INT
    * time: TIMESTAMP DEFAULT CURRENT_TIMESTAMP
# Step by step
Log in op jouw ma-host account. Dat doe je via https://hosts.ma-cloud.nl
![alt text](https://raw.githubusercontent.com/MediacollegeAmsterdam/GPR2-2019/Les-5/Les%205%20Databases/images/db1.png)
Klik op Databases    

![alt text](https://github.com/MediacollegeAmsterdam/GPR2-2019/blob/Les-5/Les%205%20Databases/images/%2011.35.37.png?raw=true)
Voeg een nieuwe database toe. Ik heb mijn database 'hers_TD1' genoemd. Voor jullie zou dat jullie studentennummer zijn.    

![alt text](https://github.com/MediacollegeAmsterdam/GPR2-2019/blob/Les-5/Les%205%20Databases/images/%2011.36.21.png?raw=true)

![alt text](https://github.com/MediacollegeAmsterdam/GPR2-2019/blob/Les-5/Les%205%20Databases/images/%2011.36.30.png?raw=true)
De eerste stap is een nieuwe gebruiker toevoegen. Zorg ervoor dat je het wachtwoord niet vergeet. Ik heb zelf 'admin' als wachtwoord gebruikt.    
![alt text](https://github.com/MediacollegeAmsterdam/GPR2-2019/blob/Les-5/Les%205%20Databases/images/%2011.36.52.png?raw=true)

![alt text](https://github.com/MediacollegeAmsterdam/GPR2-2019/blob/Les-5/Les%205%20Databases/images/%2011.40.14.png?raw=true)

Open Webadmin en klik op 'Create Table'
![alt text](https://github.com/MediacollegeAmsterdam/GPR2-2019/blob/Les-5/Les%205%20Databases/images/%2011.40.32.png?raw=true)
Maak een table aan met de volgende columns:
* id:INT, Index UNIQUE
* name:VARCHAR(12)
* score:INT
* time:TIMESTAMP Default: CURRENT_TIME
![alt text](https://github.com/MediacollegeAmsterdam/GPR2-2019/blob/Les-5/Les%205%20Databases/images/%2011.59.41.png?raw=true)

![alt text](https://raw.githubusercontent.com/MediacollegeAmsterdam/GPR2-2019/Les-5/Les%205%20Databases/images/%2012.00.00.png?raw=true)