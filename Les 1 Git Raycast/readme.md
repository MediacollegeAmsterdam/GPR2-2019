# Git en Unity

## Git
Git is een veelgebruikte Source Version control.

### Werken met Git
* Git shell
* Gitkraken
* Sourcetree
* GitExtensions

## Unity
Unity is een populaire game engine.

## Probleem 1: Scenes worden leeg gemaakt.
Een Unity Level wordt opgeslagen in een Scene. Als je een .scene bestand opent in een tekst editor zie je helebool JSON achtige code waarin alle gameobjecten worden bijgehouden. Wanneer verschillende mensen in dezelfde Unity Scene werken wordt de text in een .scene aangepast. Wanneer deze scene is aangepast kan Unity deze scene niet meer herkennen en uitlezen.     
Wat er uiteindelijk gebeurt is vergelijkbaar met als je een haakje of ';' vergeet in C# of Java.

### Oplossing:
* Maak de laatste verandering ongedaan. Gebruik een van de velen
* Haal de scene uit een vorige versie en vervang de kapote versie van de scene. *(Deze is het makkelijkst)*
* Maak alles opnieuw
    
### Tips
* Werk nooit met meerdere mensen in dezelfde scene.
* Met mensen in dezelfde script werken kan wel, maar laat 1 persoon aan de main scene werken. De rest kan werken aan gameobjects, prefabs en scripts.

## Library merge errors 
In de Library folder vind je heel veel bestanden en informatie die door Unity gegenereerd zijn die een heleboel instellingen bewaren van Unity. Ook staan hier de assets in die gecompiled zijn naar formats waarmee Unity makkelijker kan werken en rekenen. Op deze manier werkt Unity onder andere met gecompilde code, wat efficienter is.
Dat is allemaal leuk en aardig, totdat je met andere mensen gaat samenwerken die bijvoorbeeld een andere compiler hebben (macbook) of andere .net framework of andere settings. Aangezien alles wat in de Library folder staat door Unity aangemaakt wordt, hoeft deze helemaal niet gedeelt te worden.

### Oplossing: 
Om te zorgen dat deze niet gedeeld wordt, maak je bij de eerste commit van een project een .gitignore bestand aan.
Een .gitignore bestand verteld Git welke bestanden allemaal genegeerd moeten worden. De .gitignore kan je gewoon openen in een text bestand en er wordt gebruik gemaakt van 'regular expressions'.
Wanneer je bijvoorbeeld `*.cs` in de .gitignore plaatst worden alle bestanden die eindigen op '.cs' genegeerd.


### Tips:

### Te laat bij het aanmaken van .gitignore
Wanneer je te laat de .gitignore in je project stopt, dan wordt de Library folder iedere keer meegenomen. En dan gaat alles alsnog fout want hij blijft de oude Libary folder de hele tijd mee te committen. Om dit te verhelpen;
* Verwijder de verwijzing naar de Libary folder in de .gitignore. Commit deze wijziging. 
* Verwijder de Library folder en commit opnieuw. Op deze manier weet en onthoud git dat de Library folder is verwijdert.
* Voeg de verwijzing naar de Library folder terug in de .gitignore.


## Unity en Git TL;DR
* Fix je .gitignore als eerste
* Ga nooit met teamgenoten in dezelfde scene werken


# Raycasts

## Raycasts
De basisvormen voor collisions zijn:
* Sphere
* Cube
* Plane
* Ray *(!)*

Met een raycast maak je een *ray* aan en kijk je of deze ergens mee botst. In Unity heb je tegenwoordig ook Sphere cast die iets vergelijkbaars doet.

## Waarom gebruik je een raycast?
### Voorbeeld 1:
Wanneer je een schietspel speelt wil je vijanden raken wanneer je schiet. 

* Een AK-47, een veelgebruik wapen in videogames shiet kogels met een snelheid van 715 meters per secode.
* Unity kijkt iedere frame of er collisions zijn.
* Een kogel van een AK zou 11 units afleggen per frame in een game. Dat is in de meeste games 11 meter per seconde. 

Deze 11 meter bots de kogel nergens mee. De kogel zou door muren en vijanden heen bewegen zonder iets te merken of zonder dat er iets gebeurt. Door gebruik te maken van Raycasts kan je razendsnel kijken of bijvoorbeeld een kogel iets raakt.

### Voorbeeld 2:
Je wilt weten of de speler ergens op staat. De makkelijkste manier om dat te doen is een ray naar beneden te sturen en kijken of de ray ergens mee botst.

### Voorbeeld 3:
Je maakt bijvoorbeeld een stealth game en je wilt kijken of de speler gezien is. Je trekt een lijn tussen de bewaker en de speler, en je ziet dan of er een object tussen de speler en bewaker staat.

### Voorbeeld 4:
In een 3D spel wil je dat wanneer de speler objecten op een plat vlak kunnen plaatsen met gebruik van een muis. Omdat een muis alleen over 2 assen beweegt, is de diepte bepalen onmogelijk. Ook komen de coordinaten van de muis totaal niet overeen met waar naar gewezen wordt.

## Hoe werkt een Raycast?
3D:
```C#
    void Update()
    {
        RaycastHit hit;
        Ray ray = new Ray(transform.position, transform.forward);

        if(Physics.Raycast(ray, out hit))
        {
            Debug.Log(hit.collider.gameObject.name);
            if(hit.collider.gameObject.tag == "Floor")
            {
                isGrounded = true;
            }
        }
    }
```
2D:
```C#
void Update()
    {
        RaycastHit2D hit = Physics2D.Raycast(transform.position, transform.forward);
        if (hit.collider != null)
        {
            //logic
        }
    }
```

## Tips
* Bij het debuggen van raycasts kan je ```Debug.DrawRay``` of ```Debug.DrawLine``` gebruiken.
* De raycast functies hebben nog veel meer argumenten dan hierboven in de voorbeelden staan. Je kan meer vinden op:
    * https://docs.unity3d.com/ScriptReference/Physics.Raycast.html
    * https://docs.unity3d.com/ScriptReference/Physics2D.Raycast.html