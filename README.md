# CSS Vuurwerkshow Tim de Roller

Om deze show mogelijk te maken ben ik aan de slag gegaan met css variabelen, keyframes en selectoren.

![Please turn off javascript](https://user-images.githubusercontent.com/30145681/157458917-77b46121-0025-4145-915b-05bbf50dd10e.png)

Om de applicatie te kunnen zien moet je Javascript uit hebben staan. Lukt dit niet? Haal dan de `<noscript>` tags weg.


![Vuurwerk Show](https://user-images.githubusercontent.com/30145681/157459123-2a306208-4f05-49c4-a0e9-e52fcc77a30a.png)


## Wat heb ik nieuw geleerd?

- Ik ben wat gaan experimenteren met `3d transform`, dit wilde ik gebruiken om een doos te maken. Vind het echt leuk om hier mee te experimenteren maar met de tijd die ik had heb ik in week 2 ervoor gekozen om mij meer te focussen op var's.

- Ik ben een fan geworden van `variabelen` in css, deze zijn echt super handig om animaties en wat complexere code css te schijven. Ze gaan ook super fijn samen met `calc`.

- css op splitten maakt werken met veel stijling erg overzichtelijk. Dit valt ook super goed samen met WAFS & met modules werken. 

- Werken met checkboxes en labels om elementen te stylen

- Keyframes chainen & animaties maken

- Je kan `<noscript>` gebruiken om een bericht te laten zien als javascript uit staat. Of juist de volledige pagina alleen te laten als javascript uit staat.

- Je kan met `prefers-color-scheme` darkmode of lightmode toepassen op je website. Dit heb ik zelf niet gebruikt maar als ik meer tijd heb zou ik dit wel toevoegen.

- Je kan met `prefers-reduced-motion` in je css animaties minder intens maken voor mensen die dit hebben aangevinkt. Dit heb ik zelf niet gebruikt maar als ik meer tijd heb zou ik dit wel toevoegen.


## Week 1

Ik wil een kijkdoos maken waar je in het klein een show ziet. Je drukt op een punt en een mannetje loopt dan naar dat punt om vuurwerk aan te steken. Het gaat er een beetje uitzien als paper mario, witte uitsnedes en 2d items die op een 3d plane lopen.

Ik heb de binnenkant van de doos gemaakt, dit door middel van `transform-style: preserve-3d;` en `perspective: 25vh;`
Dan via `transform-origin: center bottom;` & `transform: rotateX(90deg);` op de zijkanten om de rotatie op de juiste plek te zetten en 3d te draaien.

Ook ben ik met `@keyframes` gaan spelen voor het grote mannen vuurwerk. Ik wil hier animaties achter elkaar laten spelen om zo een wat complexere show op te zetten. Hier ga ik later ook interactie aan toevoegen.

![V1 BOX](https://user-images.githubusercontent.com/30145681/156364272-d9c6b363-339c-4295-b7d0-ccd544c56289.png)


## Week 2

Ik ga 3 vuurwerk pijlen maken met css variabelen om hiermee te experimenteren. Ik heb een soort template gemaakt voor elke pijl, waar ik alleen de translated verander per pijl.
```css
/* Firework arrow template */
.vuurwerkContainer ul {
  padding: 0;
  margin: 0;
  height: 0.4em;
  width: 0.4em;
  position: fixed;
  list-style: none;
  transform-origin: bottom;
  bottom: var(--vuurwerkPijlPositieBottom);
  left: var(--vuurwerkPijlPositieLeft);
  z-index: var(--vuurwerkPijlzIndex);
  background-color: var(--vuurwerkPijlColor);
  animation: vuurwerkPad var(--vuurwerkPijlAnimatie) forwards ease-in;
}
```

En geef ik per pijl de positie, kleur enzv.
```css
/* Firework arrow variations */
.vuurwerkContainer ul:first-of-type {
  --vuurwerkPijlPositieLeft: 20%;
  --vuurwerkPijlPositieBottom: 13%;
  --vuurwerkPijlzIndex: 11;
  --vuurwerkPijlColor: black;
  --vuurwerkPijlAnimatie: 2s;
  --ColorFirework: blue;
}
```
## Week 3

Ik ben begonnen met het opschonen van mijn code en het op te delen in verschillende css files. 

![css opgedeelt](https://user-images.githubusercontent.com/30145681/157451134-f0ef14fd-2ad8-4543-a576-9cab0ecf41b7.png)


Ook was mijn vuurwerk niet responsive, hier heb ik deze week veel aan gewerkt. Ik heb de nuke en vuurwerk opnieuw gemaakt voor mobiel. Bij mobiel is de show alleen te zien als je je mobiel op landscape heb.

Om de nuke snelheid te besturen ben ik met var gaan werken:
```css 
  --airplaneFlyingTime: 7s;
  --airplaneAtCityTimer: calc(var(--airplaneFlyingTime) / 5 * 4);
  --nukeDrop: 3s;
  --nukeExplitionTime: 4s;
  --nukeExplitionDelay: calc(var(--airplaneAtCityTimer) + var(--nukeDrop));
  --cityShakeDelay: calc(var(--nukeExplitionDelay) + 0.7s);

  position: fixed;
  width: 100vw;
  height: 100vh;
  top: 0;
  z-index: 10;
  pointer-events: none;
```
Zo zitten de animaties goed in elkaar, ook als je de tijd veranderd. Je kan nu ook de stad een naam geven. 

![Stad foto](https://user-images.githubusercontent.com/30145681/157453613-8ce31a59-5a06-4a94-ad4c-e5ba53320da7.png)



## Week 4

De lucht was nog wat leeg dus ik heb de deathstar toegevoegd

![deathStar](https://user-images.githubusercontent.com/30145681/157460338-3b0873d6-77d0-466a-a656-a21b94d3d400.png)

En natuurijk kan deze ook schieten

![deathstar blast](https://user-images.githubusercontent.com/30145681/157460461-9e85eef8-6ba5-4bb2-8237-2ffcbcb1dd6c.png)

Ik heb verder nog de code opgeschoont en wilde wat meer werken met `::before` en `::after` dus dit heb ik toegepast op de vuurpijlen & wolkjes.

Ook wilde ik graag met geluid werken, alleen kan je niet met css geluid inladen. Het is gelukt om muziek af te spelen als je op het midden van de death star drukt, dit door `pointer-event: none;` te gebruiken. Zo kan je door een div heen klikken.

## Bronnen

Lessen

https://cssgradient.io/

https://github.com/cmda-minor-web/css-to-the-rescue-2122

https://www.w3schools.com/

https://www.colorzilla.com/gradient-editor/

https://projects.verou.me/css3patterns/

https://www.sinds1971.nl/

https://bennettfeely.com/clippy/
