PHP Hello world

# PHP TL;DR
* Ga naar ma-hosts
* Maak daar een nieuwe database aan
* Maak een table met de volgende columns:
    * id: INT UNIQUE, A_I 
    * name: VARCHAR(20)
    * score: INT
    * time: TIMESTAMP DEFAULT CURRENT_TIMESTAMP
* Test of je iets kan toevoegen met SQL.
```SQL
INSERT INTO TD_Score(`name`, `score`) VALUES ('SILVAN', 23756756723);
```
* Maak een PHP script waarmee je:
    * Verbinding maakt met de database
    * Een SQL query uit kan voeren.
    * Waardes uit de URL

## Stap 1: Aanmaken van database en table.
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
* id:INT, Index UNIQUE, **DE CHECKBOX *A_I* AANSKRUISEN**
* name:VARCHAR(12)
* score:INT
* time:TIMESTAMP Default: CURRENT_TIME
Elke table heeft een unieke ID nodig. Met A_I zet je deze op AUTO_INCREMENT, dat betekent dat deze automatisch iedere keer 1tje meer wordt.
![alt text](https://github.com/MediacollegeAmsterdam/GPR2-2019/blob/Les-5/Les%205%20Databases/images/%2011.59.41.png?raw=true)

![alt text](https://raw.githubusercontent.com/MediacollegeAmsterdam/GPR2-2019/Les-5/Les%205%20Databases/images/%2012.00.00.png?raw=true)

*Gefeliciteerd, je hebt nu je eigen database en table aangemaakt*
 

## Stap 2: Vullen van de array
### Stap 2.1: Vullen met een SQL Query
Een SQL Query is eigenlijk de basistaal van databases. Je kan er in een database alles mee doen. Wij gaan enkel INSERT gebruiken. 

Open de table die je net hebt aangemaakt, en klik op de knop SQL.
![alt text](https://raw.githubusercontent.com/MediacollegeAmsterdam/GPR2-2019/Les-5/Les%205%20Databases/images/sql/09.22.18.png?raw=true)

![alt text](https://github.com/MediacollegeAmsterdam/GPR2-2019/blob/Les-5/Les%205%20Databases/images/%2011.40.32.png?raw=true)
```SQL
INSERT INTO TD_Score(`name`, `score`) VALUES ('SILVAN', 23756756723);
```
Voer deze query uit. Als het gelukt is, heb je nu items toe gevoegd aan de Array. Controlleer goed op spellingsfouten en of 'id' en 'time' goed ingesteld zijn.

### Stap 2.2
Je wilt niet dat de speler op z'n eigen (lokale) computer de database kan aanpassen. Je wilt altijd dat alle aanpassingen aan de databae uitgevoerd worden aan de kant van de server waar de database zelf op staat. 

# NodeJS TL;DR
* Installeer NodeJS en ExpressJS
* Installeer MongoDB en Mongoose
* Maak een model voor de scores:
```Javascript
var scores = new mongoose.Schema({
    name: String,
    score: Number,
    date: Date
})
```
* Maak verbinding met de MongoDB database (met behulp van Mongoose)
* Sla een score op.