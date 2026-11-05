# Sprint 2
Voor de immersive lab moeten we een exposure scanario bouwen. Het idee is eigenlijk, hoe kunnen we dit doen?

Ik heb nagedacht over de mogelijkheden, en om een virtuele omgeving te maken zijn 3 mogelijkheden:
1. 2D afbeeldingen die bewegen
2. 3D omgeving
3. TouchDesigner

## Verschillende visuele vormgeving

### 2D afbeeldingen
Ik heb on

### 3D omgeving
Ik heb dit onderzocht en gekeken wat de leukste maar ook meest simpele optie is.

Als we 




### TouchDesigner
Van de docent die de immersive room had uitgelegd was touchdesigner iets wat veel studenten gebruikte om reactiviteit te bouwen. Touchdesigner is een programma waarbij je "live" beelden geneerd. Het is eigenlijk een super coole programma. Je kan een AI tracking systeem koppelen aan touchdesigner en op basis van handsignalen bepaalde effecten triggeren. Het probleem is, er is best wel een diepe learning curve om het te begrijpen. Omdat ik niet van plan ben ooit touchdesigner te gebruiken buiten dit project, valt dit voor mij af. 


# 3D scene maken
Mijn eerste idee was enkel om blender te gebruiken om videos af te spelen van de immersive environment, om te zien hoe dat er virtueel uit ziet zonder dat we die kamer in hoeven te huren. Want we kunnen gewoon videos opnemen en de videos projecteren op blender. Het coole hiervan is, we kunnen simpele 3D scenarios bouwen met kant en klare 3D modellen, deze direct opnemen in het programma, en zo een omgeving creeren. Doordat het 3D is krijgt het systeem automatisch een gevoel van diepte. En omdat het videos zijn zou het makkelijker zijn om voor de opdrachtgever om te runnen. 

Daarnaast, omdat je kan scripten in blender, kan je een soort van demo omgeving creeren.

## Immersive room nabouwen

De immersive lab heeft een poster voor de deur met de volgende dimensies:
![image](../images/sprint2/IR_dimensions.jpg)

- front: 1058x799px
- back: 1058x799px
- left: 1361x799px
- right: 361x799px
- floor: 1058x1361px

Ik had geen werkelijke dimenties van de muur in meters, maar gelukkig is dat niet nodig. Het belangrijkste deel is de aspect ratio. Dus in blender heb ik de immersive room nageboud op basis van de aspect ratio van de pixel formaten. Ik heb gewoon de pixel formaten genomen: 100 en dat is de oppervlakte. Dan kwam ik neer op

- Front: 10.58 x 7.99 meter
- Back: 10.58 x 7.99 meter
- Left: 13.61 x 7.99 meter
- Right: 13.61 x 7.99 meter

Dat komt niet overeen met de werkelijkheid, maar is ook niet nodig. Het is enkel een test omgeving. Dus nu hebben we dit in blender:

![image](../images/sprint2/IR_roombuild.png)

### Test omgeving creeren voor een video / afbeelding
Van onze opdrachtgever hebben we een video gekrgen, maar die zijn 3gb en elke keer faalt de teams download...

Op de website van blender hebben ze prachtige demo omgevingen gebouwd. Dus ik heb gewoon 1 van deze omgevingen gedownload zodat ik kan testen. Ik heb de volgende gekozen: 

Blender 4.5 LTS – DOGWALK
https://www.blender.org/download/demo-files/

![image](../images/sprint2/default_demo_environment.png)

De omgeving is cool, maar er is geen lucht aanwezig. Het is een eentonige kleur.
Dus ik heb gezocht naar een skybox. Want ik wil in de video dat het wel voelt alsof je in een ruimte staat met wolken etc

Ik heb de volgende skybox gebruikt hiervoor:  
https://polyhaven.com/hdris/pure-skies 



Ik heb ook wat extra primitieve formen toegevoegd zodat de omgeving niet enkel platte land is. Niet super indrukwekkend maar het helpt om de ruimte wat op te vullen

![image](../images/sprint2/skybox_n_ground.png)


### Crappy animatie

Kheb een kleine animatie gemaakt en de bestaande animatie wat aangepast zodat er een beetje beweging is, om te kijken hoe de overgang naar muren klopt.

![image](../images/sprint2/animation.gif)



### Hoe iets opnemen dan..?
Origineel had ik de cameras met een FOV van 90 graden. Alleen het probleem hierbij is dat het een video opneemt alsof de kamer een doos is..
De immersive room is eigenlijk een rechthoek. De linker en rechter muur zijn breder dan de voor en achterkant van de kamer. Het probleem is hierbij dat als je een rechthoek opneemt (zoals ik dat had...) dat je dan op de linker en rechter muur een uitgestrek beeld hebt omdat je een kleiner beeld op een bredere muur toont.

Je kan zien dat mijn cameras ook in een doos positie stonden:

![image](../images/sprint2/camera%20box.png)

Ik heb met behulp van AI de camera's FOV berekend.. ik weet niks van cameras af en laat die maar lekker de aspect ratios berekenen. 

Voor elke camera heb ik dan de output van de camera (pixel hoogte en breedte) gezet naar de exacte dimenties van de immersive room vlakken.





### Godot
Ik dacht dat het eigenlijk cool zou zijn als je een kleine level kan hebben waarin je gewoon letterlijk kan rondkijken. Dit zou voor de opdrachtgever ook makkelijker te runnen zijn. godot is super kleinschalig. En met godot is het makkelijker scripten dan in blender imo. 

Ik ben van plan on nog buttons toe te voegen om special effects uit te testen. 

het is niet perfect, maar het geeft een beetje een idee hoe je van 3D naar geprojecteerde videos kan gaan en hoe dat er dan uit ziet. Laat ons een klein beetje testen. 

![image](../images/sprint2/godot_scene.png)


<details>
<summary>Click to reveal spoiler</summary>

![image](../images/sprint2/godot_immersive%20room.png)

</details>