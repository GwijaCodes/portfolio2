<template>

    <div class="contacts section">
        <img src="./imgs/skillset.svg" alt="" class="contacts-bg">
        <div class="title">
            <h2 class="title-h2">CONTATTAMI CONTATTAMI CONTATTAMI CONTATTAMI CONTATTAMI CONTATTAMI </h2>
        </div>
        <div class="grid">
            <div class="col-50">
                <form action="https://api.web3forms.com/submit" method="POST">
                    <div class="contact-form">
                        <input type="hidden" name="access_key" value="ec0b52d6-ec0d-4a16-941f-d17c2f37b73f">
                        <input type="text" name="name" placeholder="Il tuo Nome" class="contact-inputs" required>
                        <input type="email" name="email" placeholder="La tua Email" class="contact-inputs" required>
                        <textarea name="message" placeholder="Il tuo Messaggio" class="contact-inputs"
                            required></textarea>
                        <button class="button" type="submit">INVIA</button>
                    </div>
                </form>
            </div>
        </div>
        <div class="col-50">
            <img data-aos="fade-right" data-aos-delay="300" class="img-res" loading="lazy" src="./imgs/ohno.png" alt="">
        </div>
        <div class="final">
            <div>
                <a href="https://www.iubenda.com/privacy-policy/89294495"
                    class="iubenda-black iubenda-noiframe iubenda-embed iubenda-noiframe "
                    title="Privacy Policy ">Privacy Policy</a>

            </div>
            <div class="final-icons">
                <a href="mailto:gloriasaija2000@gmail.com">
                    <img src="./imgs/icons/email.svg" fill="currentColor" style="width: 50px;" alt="">
                </a>
                <a href="https://www.linkedin.com/in/gloria-saija-a3816b217">
                    <img src="./imgs/icons/linkedin.svg" style="width: 40px;" alt="">
                </a>
                <a href="https://github.com/GwijaCodes">
                    <img src="./imgs/icons/github.svg" fill="currentColor" style="width: 40px;" alt="">
                </a>
                <a href="https://www.instagram.com/gwija.js/">
                    <img src="./imgs/icons/instagram.svg" fill="currentColor" style="width: 40px;" alt="">
                </a>
            </div>
        </div>
    </div>
</template>