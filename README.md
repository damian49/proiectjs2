# proiectjs2
A simple web application for learning something... In fact, anything!

## Introducere
Navigând prin Internet poate ați dat peste niște prezentări ale unei metode mai speciale de învățare a unei limbi străine. Sau, mai exact, de extindere a vocabularului cunoscut. Metoda se bazează pe utilizarea unor cartonașe conținând cuvintele care trebuie învățate, dar care nu sunt parcurse la întâmplare sau unul după altul, ci după niște reguli. La baza sistemului sunt cercetăti științifice privind modul în care funcționează creierul uman.

https://www.youtube.com/watch?v=ldkUEfkJX_8 sau https://www.youtube.com/watch?v=eVajQPuRmk8

Există și variante informatice ale metodei, una dintre cele mai utilizate fiind [Anki](https://apps.ankiweb.net/). Fiind și gratuită, o putem instala pentru a vedea dacă este ceea ce ne trebuie. 

Proiectul propus rezolvă o parte a unei aplicații de acest fel, respectiv componenta de *front-end*.

![Img. 1](/imagini/app.png)

## Resurse necesare

Pentru a începe dezvoltarea proiectului, un prim pas este găsirea unei soluții pentru crearea de carduri care se întorc cu 180 grade dacă se pune cursorul mausului deasupra. Există mai multe soluții. O simplă căutare (folosind cuvintele *html5 create flip card*) returnează însă ca primă variantă o soluție bazată pe HTML5 și CSS prezentată în cunoscutul site - [w3schools](https://www.w3schools.com/howto/howto_css_flip_card.asp).

Codul HTML5 folosit este:

```
<div class="flip-card">
  <div class="flip-card-inner">
    <div class="flip-card-front">
      <img src="imagini/img_avatar.png" alt="Avatar" style="width:300px;height:300px;">
    </div>
    <div class="flip-card-back">
      <h1>John Doe</h1> 
      <p>Architect & Engineer</p> 
      <p>We love that guy</p>
    </div>
  </div>
</div>
```

Pentru stilizare s-a folosit următorul ansamblu de reguli:
```
/* The flip card container - set the width and height to whatever you want. We have added the border property to demonstrate that the flip itself goes out of the box on hover (remove perspective if you don't want the 3D effect */
.flip-card {
  background-color: transparent;
  width: 300px;
  height: 200px;
  border: 1px solid #f1f1f1;
  perspective: 1000px; /* Remove this if you don't want the 3D effect */
}

/* This container is needed to position the front and back side */
.flip-card-inner {
  position: relative;
  width: 100%;
  height: 100%;
  text-align: center;
  transition: transform 0.8s;
  transform-style: preserve-3d;
}

/* Do an horizontal flip when you move the mouse over the flip box container */
.flip-card:hover .flip-card-inner {
  transform: rotateY(180deg);
}

/* Position the front and back side */
.flip-card-front, .flip-card-back {
  position: absolute;
  width: 100%;
  height: 100%;
  backface-visibility: hidden;
}

/* Style the front side (fallback if image is missing) */
.flip-card-front {
  background-color: #bbb;
  color: black;
}

/* Style the back side */
.flip-card-back {
  background-color: dodgerblue;
  color: white;
  transform: rotateY(180deg);
}
```

Din ele s-a asamblat prima versiune a aplicației, *card1.html*. Rezultat:





