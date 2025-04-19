<script setup lang="ts">
import ScrollingTitle from './components/ScrollingTitle.vue';

</script>

<template>
    <ScrollingTitle :text="'ABOUT ME'" />
    <div class="about-me section">
        <div class="section-title-container">
            <h2 class="section-title">DIMMI QUALCOSA CHE NON SO...</h2>
            <p class="subtitle">Dato che non hai skippato questa sezione, e’ arrivato il momento di parlarti un po’ di
                me.</p>
        </div>
        <div class="grid">
            <div class="col-50">
                <p>Sono una developer con un background in Arti Tecnologiche, laureata all’<a
                        href="https://www.abacatania.it/">Accademia di Belle Arti di Catania</a>. Vivo ad Acireale e
                    lavoro nel mondo del web, dove unisco creatività e tecnica.
                    Ho sempre avuto un debole per la grafica 3D (soprattutto quella retrò!) e, da quando ho iniziato a
                    sviluppare, ho ampliato le mie competenze affrontando sfide sempre nuove.
                    Se c’è una cosa che ho capito, è che conoscere strumenti e linguaggi è fondamentale, ma lo è
                    altrettanto sapersi orientare tra ostacoli inaspettati, collaborare con gli altri e rimanere
                    curiosi. Ah, e naturalmente… saper cercare su Google! <br>
                    Non ci credi? <a href="./imgs/SaijaGloria_CV.pdf">Scarica il mio curriculum</a></p>

                <img data-aos="fade-left" src="./imgs/pic.png" alt="gs">
            </div>
            <div class="col-50">
                <div style="position: relative">
                    <div class="windows-container" id="dodgyWindow">
                        <div class="windows-header">
                            <span class="close-btn">X</span>
                        </div>
                        <div class="windows-content">
                            <video data-aos="fade-up" class="gif" src="./imgs/dancedance.webm" autoplay loop playsinline
                                muted poster="./imgs/poster.jpg"></video>
                        </div>
                    </div>
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

.animated {
    overflow: hidden;
}

.gif {
    width: 100%;
}
</style>