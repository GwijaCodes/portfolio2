<script setup>
import ScrollingTitle from './components/ScrollingTitle.vue';
import DodgyWindow from './components/DodgyWindow.vue';
import DanceDance from '@/assets/imgs/dancedance.webm'
import MyPic from '@/assets/imgs/pic.png'
</script>

<template>
    <ScrollingTitle :text="'ABOUT ME'" />
    <div class="about-me section">
        <div class="section-title-container">
            <h2 class="section-title">DIMMI QUALCOSA CHE NON SO</h2>
            <p class="subtitle">
                Dato che non hai skippato questa sezione, e’ arrivato il momento di parlarti un po’ di me.
            </p>
        </div>
        <div class="grid">
            <div class="col-50">
                <p>
                    Sono una developer con un background in Arti Tecnologiche, laureata all’
                    <a href="https://www.abacatania.it/">Accademia di Belle Arti di Catania</a>. Vivo ad Acireale e
                    lavoro nel mondo del web, dove unisco creatività e tecnica.
                    Ho sempre avuto un debole per la grafica 3D (soprattutto quella retrò!) e, da quando ho iniziato a
                    sviluppare, ho ampliato le mie competenze affrontando sfide sempre nuove.
                    Se c’è una cosa che ho capito, è che conoscere strumenti e linguaggi è fondamentale, ma lo è
                    altrettanto sapersi orientare tra ostacoli inaspettati, collaborare con gli altri e rimanere
                    curiosi. Ah, e naturalmente… saper cercare su Google! <br />
                    Non ci credi?
                    <a href="./imgs/SaijaGloria_CV.pdf">Scarica il mio curriculum</a>
                </p>
            </div>
            <div class="col-50">
                <div class="windows-stack">
                    <DodgyWindow id="danceDance" :video-src="DanceDance" class="window-video" />
                    <DodgyWindow id="myPic" :imageSrc="MyPic" class="window-pic" />
                </div>
            </div>
        </div>
    </div>
</template>

<style scoped>
.about-me {
    padding-top: 1px;
    overflow: hidden;
    color: var(--chiaro);
}

.about-me .grid {
    margin: auto;
    width: 80vw;
    padding: 0;
}

.about-me .col-50 {
    padding-top: 0;
}

.windows-stack {
    width: 100%;
    height: auto;
    position: relative;
    margin-top: 30px;
}

.window-pic {
    position: absolute;
    top: 120px;
    left: 0;
    z-index: 2;
    transform: scale(0.7);
}

.window-video {
    position: absolute;
    top: 40px;
    right: 0;
    left: 50px;
    z-index: 1;
}
</style>
