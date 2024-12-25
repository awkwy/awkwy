<script>
    import { onMount } from 'svelte';

    // Liste des mots et définitions
    const mots = [
        { mot: "ordinateur", definition: "Machine électronique capable de traiter des données." },
        { mot: "MAOYUN", definition: "UN EXEMPLE DE QUELQU'UN QUI EST BIG SHABI" },
        { mot: "svelte", definition: "Framework JavaScript pour construire des interfaces utilisateur." },
    ];

    let motCourant = "";
    let definitionCourante = "";
    let motDevine = "";
    let lettresDevinees = [];
    let lettresCorrectes = [];
    let lettresIncorrectes = [];
    let tentativesRestantes = 6;
    let message = "";
    let showModal = false;
    let canvas;
    let ctx;

    onMount(() => {
        resetGame();
        ctx = canvas.getContext('2d');
        dessinerPendu();
    });

    function resetGame() {
        const index = Math.floor(Math.random() * mots.length);
        motCourant = mots[index].mot.toUpperCase();
        definitionCourante = mots[index].definition;
        lettresDevinees = [];
        lettresCorrectes = [];
        lettresIncorrectes = [];
        tentativesRestantes = 6;
        message = "";
        showModal = false;
        initialiserMotDevine();
        if (ctx) {
            ctx.clearRect(0, 0, canvas.width, canvas.height);
            dessinerPendu();
        }
        document.querySelectorAll('button.letter').forEach(button => button.disabled = false);
    }

    function initialiserMotDevine() {
        motDevine = motCourant.replace(/./g, '_');
    }

    function devinerLettre(lettre) {
        lettre = lettre.toUpperCase();
        if (lettre.match(/^[A-Z]$/) && !lettresDevinees.includes(lettre)) {
            lettresDevinees = [...lettresDevinees, lettre];
            if (motCourant.includes(lettre)) {
                lettresCorrectes = [...lettresCorrectes, lettre];
                mettreAJourMotDevine(lettre);
            } else {
                lettresIncorrectes = [...lettresIncorrectes, lettre];
                tentativesRestantes -= 1;
                dessinerPendu();
            }
        }
        verifierFinDeJeu();
    }

    function mettreAJourMotDevine(lettre) {
        motDevine = motCourant.split('').map((l, i) => lettresDevinees.includes(l) ? l : '_').join('');
    }

    function verifierFinDeJeu() {
        if (!motDevine.includes('_')) {
            message = "Félicitations ! Vous avez gagné !";
            showModal = true;
            document.querySelectorAll('button.letter').forEach(button => button.disabled = true);
        } else if (tentativesRestantes <= 0) {
            message = `Désolé, vous avez perdu. Le mot était : ${motCourant}`;
            showModal = true;
            document.querySelectorAll('button.letter').forEach(button => button.disabled = true);
        }
    }

    function dessinerPendu() {
        ctx.clearRect(0, 0, canvas.width, canvas.height);

        ctx.strokeStyle = '#000';
        ctx.lineWidth = 2;

        // Base
        ctx.beginPath();
        ctx.moveTo(10, 190);
        ctx.lineTo(140, 190);
        ctx.stroke();

        // Poteau vertical
        ctx.beginPath();
        ctx.moveTo(30, 190);
        ctx.lineTo(30, 20);
        ctx.stroke();

        // Poteau horizontal
        ctx.beginPath();
        ctx.moveTo(30, 20);
        ctx.lineTo(100, 20);
        ctx.stroke();

        // Corde
        ctx.beginPath();
        ctx.moveTo(100, 20);
        ctx.lineTo(100, 40);
        ctx.stroke();

        if (tentativesRestantes <= 5) {
            // Tête
            ctx.beginPath();
            ctx.arc(100, 50, 10, 0, Math.PI * 2, true);
            ctx.stroke();
        }
        if (tentativesRestantes <= 4) {
            // Corps
            ctx.beginPath();
            ctx.moveTo(100, 60);
            ctx.lineTo(100, 100);
            ctx.stroke();
        }
        if (tentativesRestantes <= 3) {
            // Bras gauche
            ctx.beginPath();
            ctx.moveTo(100, 70);
            ctx.lineTo(80, 90);
            ctx.stroke();
        }
        if (tentativesRestantes <= 2) {
            // Bras droit
            ctx.beginPath();
            ctx.moveTo(100, 70);
            ctx.lineTo(120, 90);
            ctx.stroke();
        }
        if (tentativesRestantes <= 1) {
            // Jambe gauche
            ctx.beginPath();
            ctx.moveTo(100, 100);
            ctx.lineTo(80, 130);
            ctx.stroke();
        }
        if (tentativesRestantes <= 0) {
            // Jambe droite
            ctx.beginPath();
            ctx.moveTo(100, 100);
            ctx.lineTo(120, 130);
            ctx.stroke();
        }
    }

    const azerty = [
        "A", "Z", "E", "R", "T", "Y", "U", "I", "O", "P",
        "Q", "S", "D", "F", "G", "H", "J", "K", "L", "M",
        "W", "X", "C", "V", "B", "N"
    ];
</script>

<svelte:head>
    <title>Pendu</title>
    <meta name="description" content="Pendu, construction d'un vocabulaire mentale" />
</svelte:head>

<main>
    <h1>Jeu du Pendu</h1>
    <p>Définition : {definitionCourante}</p>
    <canvas bind:this={canvas} width="200" height="200"></canvas>
    <h3>{motDevine.split('').join(' ')}</h3>
    <div class="keyboard">
        {#each azerty as lettre}
            <button 
                class="letter {lettresCorrectes.includes(lettre) ? 'correct' : ''} {lettresIncorrectes.includes(lettre) ? 'incorrect' : ''}" 
                on:click={() => devinerLettre(lettre)} 
                disabled={lettresDevinees.includes(lettre)}>
                <kbd>{lettre}</kbd>
            </button>
        {/each}
    </div>
    <p>Tentatives restantes : {tentativesRestantes}</p>

    <!-- Modal -->
    {#if showModal}
    <div class="modal-backdrop">
        <div class="modal">
            <h2>{message}</h2>
            <button class="modal-button" on:click={resetGame}>Recommencer</button>
        </div>
    </div>
    {/if}
</main>

<style>
    main {
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
        font-family: Arial, sans-serif;
        padding: 1em;
        box-sizing: border-box;
    }

    h1 {
        font-size: 2em;
        margin-bottom: 1em;
        text-align: center;
    }

    p {
        font-size: 1.5em;
        text-align: center;
    }

    h3 {
        font-size: 2em;
        letter-spacing: 0.2em;
        text-align: center;
        margin: 1em 0;
    }

    canvas {
        border: 1px solid #000;
        margin: 1em 0;
    }

    .keyboard {
        display: flex;
        flex-wrap: wrap;
        justify-content: center;
        gap: 0.5em;
        max-width: 600px;
    }

    .letter {
        padding: 0.75em 1em;
        font-size: 1.5em;
        cursor: pointer;
        text-align: center;
        flex: 1 0 9%;
        max-width: 9%;
        box-sizing: border-box;
    }

    .letter.correct {
        background-color: #4caf50; /* green */
        color: white;
    }

    .letter.incorrect {
        background-color: #f44336; /* red */
        color: white;
    }

    .letter:disabled {
        cursor: not-allowed;
    }

    button {
        margin-top: 1em;
        padding: 0.5em 1em;
        font-size: 1em;
    }

    .modal-backdrop {
        position: fixed;
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;
        background: rgba(0, 0, 0, 0.5);
        display: flex;
        align-items: center;    justify-content: center;
}

.modal {
    background: white;
    padding: 2em;
    border-radius: 8px;
    text-align: center;
}

.modal-button {
    margin-top: 1em;
    padding: 0.5em 1em;
    font-size: 1em;
    background-color: #007bff;
    color: white;
    border: none;
    cursor: pointer;
}

.modal-button:hover {
    background-color: #0056b3;
}

@media (max-width: 768px) {
    .letter {
        font-size: 1.2em;
        padding: 0.5em 0.75em;
        flex: 1 0 18%;
        max-width: 18%;
    }
}
</style>