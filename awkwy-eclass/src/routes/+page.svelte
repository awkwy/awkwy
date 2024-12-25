<script>

</script>

<svelte:head>
<title>Accueil</title>
<meta name="description" content="cours de l'année 2024" />
</svelte:head>

<main class="wrapper">
<div class="element1 grid-box">
 
    <h5 class="mb-2 text-2xl font-bold tracking-tight text-gray-900">Noteworthy technology acquisitions 2021</h5>
    <p class="font-normal text-gray-700 dark:text-gray-400 leading-tight">Here are the biggest technology acquisitions of 2021 in reverse chronological order.</p>

</div>
<div class="element2 grid-box">2</div>
<div class="element3 grid-box">3</div>
<div class="element4 grid-box">4</div>
<div class="element5 grid-box">5</div>
</main>

<style>
html,
body {
width: 100%;
height: 100%;
margin: 0;
padding: 0;
font-size: 10px;
background: #1b2431;
}

.wrapper {
width: 90vw;
height: 96.2vh;
margin: 5vh auto;
display: grid;
grid-template-rows: 1fr 1fr 1fr 1fr;
grid-template-columns: 1fr 1fr 1fr 1fr;
grid-gap: 1rem;
grid-template-areas:
  "box1 box1 box1 box2"
  "box1 box1 box1 box3"
  "box1 box1 box1 box4"
  "box1 box1 box1 box5";
}

.wrapper .grid-box {
border-radius: 10px;
transition: all 250ms;
font-size: 2rem;
color: white;
font-family: sans-serif;
box-shadow: 0 0 0.3rem rgba(0, 0, 0, 0.12), 0 1px 2px rgba(0, 0, 0, 0.24);
animation: fadein 1s ease-out normal backwards;
}

.wrapper .grid-box:hover {
z-index: 2;
position: relative;
box-shadow: 0 1.5rem 2.8rem rgba(0, 0, 0, 0.15),
  0 1rem 1rem rgba(0, 0, 0, 0.15);
transform: translate(0, -0.5rem) scale(1.01);
}

.wrapper .element1 {
grid-area: box1;
animation-delay: 0;
}
.wrapper .element2 {
grid-area: box2;
animation-delay: 100ms;
}
.wrapper .element3 {
grid-area: box3;
animation-delay: 200ms;
}
.wrapper .element4 {
grid-area: box4;
animation-delay: 300ms;
}
.wrapper .element5 {
grid-area: box5;
animation-delay: 300ms;
}
@keyframes fadein {
0% {
  transform: scale(0);
}
70% {
  transform: scale(1.05);
}
100% {
  transform: scale(1);
}
}

/* Media Queries for Responsiveness */
@media (max-width: 1200px) {
.wrapper {
  grid-template-rows: 1fr 1fr 1fr 1fr;
  grid-template-columns: 1fr 1fr;
  grid-template-areas:
    "box1 box1"
    "box1 box1"
    "box2 box3"
    "box4 box5";
}

.wrapper .grid-box {
  font-size: 1.5rem;
}
}

@media (max-width: 768px) {
.wrapper {
  grid-template-rows: repeat(4, 1fr);
  grid-template-columns: 1fr;
  grid-template-areas:
    "box1"
    "box2"
    "box3"
    "box4"
    "box5";
}

.wrapper .grid-box {
  font-size: 1.2rem;
}
}
</style>