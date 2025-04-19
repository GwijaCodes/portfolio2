<script>
import ScrollingTitle from './components/ScrollingTitle.vue';
</script>

<template>
    <ScrollingTitle :text="'ABOUT ME'" />
    <div class="projects section">

        <div class="section-title-container">
            <h2 class="section-title">DIMMI QUALCOSA CHE NON SO...</h2>
            <p class="subtitle">Dato che non hai skippato questa sezione, e’ arrivato il momento di parlarti un po’ di
                me.</p>
        </div>
        <div class="card grid reversed" data-aos="fade-right" data-aos-offset="100">

            <div class="col-50 des">
                <h3>Oh My Gin (in corso)</h3>
                <span class="chips">
                    <span class="chip">UI/UX</span> <span class="chip">FRONT-END</span>
                    <p>Applicazione <b>Next.js</b> per accedere a un vasto archivio di drink e le loro ricette, tramite
                        <a href="https://www.thecocktaildb.com/api.php">API</a>. Ancora in corso, ma puoi dare
                        un'occhiata al repository!
                    </p>
                </span>
            </div>
            <div class="col-50 img">
                <a href="https://github.com/GwijaCodes/mydrink" target="_blank">
                    <img src="./imgs/ohmygin.jpg" alt="" loading="lazy">
                </a>
            </div>
        </div>
        <div class="card grid" data-aos="fade-left" data-aos-offset="500">

            <div class="col-50 img">
                <a class="project" href="https://gwijacodes.github.io/myspazza/" target="_blank">
                    <img src="./imgs/spazza-ad.jpg" alt="">
                </a>
            </div>
            <div class="col-50 des">
                <h3>Spazza!</h3>
                <span class="chips">
                    <span class="chip">UI/UX</span> <span class="chip">FRONT-END</span><span class="chip">MODELLAZIONE
                        3D</span>
                </span>
                <p>Questa applicazione web nasce da una domanda che, se
                    vivi in un comune dove
                    viene ritirata la
                    raccolta differenziata porta a porta, ti ha tormentato almeno una volta: "Quale bidone bisogna
                    uscire stasera?" <br>
                    Spazza te lo ricorderà ogni giorno, e sarà anche felice di ricordarti cosa puoi (e cosa non)
                    conferire in ogni singolo bidone.</p>
            </div>
        </div>
        <div class="card grid reversed" data-aos="fade-right" data-aos-offset="500">

            <div class="col-50 des">
                <h3>Lucchesisucchi.it</h3>
                <span class="chips">
                    <span class="chip">FRONT-END</span>

                </span>
                <p>Sito vetrina one-page che racconta la storia e i prodotti dell'azienda Lucchesi, produttrice di
                    spremute surgelate e olii essenziali estratti da agrumi completamente <i>made in Sicily, based in
                        Aci Catena.</i></p>
            </div>
            <div class="col-50 img">
                <a href="https://www.lucchesisucchi.it/" target="_blank">
                    <img src="./imgs/progetto-lucchesi.jpg" alt="" loading="lazy">
                </a>
            </div>
        </div>
        <div class="card grid" data-aos="fade-left" data-aos-offset="500">
            <div class="col-50 img">
                <a href="https://computermaniacireale.it/" target="_blank">
                    <img src="./imgs/progetto-computermania.jpg" alt="" loading="lazy">
                </a>
            </div>
            <div class="col-50 des">
                <h3>Computermaniacireale.it</h3>
                <span class="chips">
                    <span class="chip">FRONT-END</span>

                </span>
                <p>Biglietto da visita elettronico ed essenziale per negozio di elettronica e riparazioni, one-page,
                    animato.</p>
            </div>
        </div>
    </div>
</template>