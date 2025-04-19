<script setup>
import Shapes from '@/assets/imgs/cool.jpg'
import RotatingHead from '@/assets/imgs/rotatehead.webm'

import { IconBrandLinkedin, IconMailOpened, IconBrandGithub, IconBrandInstagram } from '@tabler/icons-vue';
</script>

<template>
    <header class="grid" :style="{ backgroundImage: `url(${Shapes})` }">
        <div class="intro">
            <p>Come va? Mi chiamo Gloria Saija</p>
            <h1>FRONT-END DEV & <br>
                3D ARTIST</h1>
            <div class="icons">
                <a href="mailto:gloriasaija2000@gmail.com">
                    <IconMailOpened class="icon" />
                </a>
                <a href="https://www.linkedin.com/in/gloria-saija-a3816b217">
                    <IconBrandLinkedin class="icon" />
                </a>
                <a href="https://github.com/GwijaCodes">
                    <IconBrandGithub class="icon" />
                </a>
                <a href="https://www.instagram.com/gwija.js/">
                    <IconBrandInstagram class="icon" />
                </a>
            </div>
            <video class="img-res rotating-head" :src="RotatingHead" autoplay loop playsinline muted></video>
        </div>
    </header>
</template>

<style scoped>
h1 {
    font-family: 'Raleway', sans-serif;
    font-weight: 900;
}
</style>