# CSS Vuurwerkshow

Om deze show mogelijk te maken ben ik aan de slag gegaan met css variabelen, keyframes en selectoren.

![Please turn off javascript](https://user-images.githubusercontent.com/30145681/157458917-77b46121-0025-4145-915b-05bbf50dd10e.png)
![Vuurwerk Show](https://user-images.githubusercontent.com/30145681/157459123-2a306208-4f05-49c4-a0e9-e52fcc77a30a.png)

## Mijn uitwerking

Vuurwerkshow met een kleine puzzel die je kan doen om het “grote mannen vuurwerk” te kunnen zien.

Je ziet knoppen voor je waarmee je de show kunt activeren, maar dat is niet het enige wat je kunt doen. Als je specifieke items indrukt kan je het grote “grote mannen vuurwerk” activeren, wat een wat permanentere show geeft.

### Idee week 1

Ik wil een kijkdoos maken waar je in het klein een show ziet. Je drukt op een punt en een mannetje loopt dan naar dat punt om vuurwerk aan te steken. Het gaat er een beetje uitzien als paper mario, witte uitsnedes en 2d items die op een 3d plane lopen.

Ik heb de binnenkant van de doos gemaakt, dit door middel van `transform-style: preserve-3d;` en `perspective: 25vh;`
Dan via `transform-origin: center bottom;` & `transform: rotateX(90deg);` op de zijkanten om de rotatie op de juiste plek te zetten en 3d te draaien.

Ook ben ik met `@keyframes` gaan spelen voor het grote mannen vuurwerk. Ik wil hier animaties achter elkaar laten spelen om zo een wat complexere show op te zetten. Hier ga ik later ook interactie aan toevoegen.

![V1 BOX](https://user-images.githubusercontent.com/30145681/156364272-d9c6b363-339c-4295-b7d0-ccd544c56289.png)


### Idee week 2

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
### Week 3

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



### Week 4




