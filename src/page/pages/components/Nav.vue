<script setup>
import NavIco from '@/assets/imgs/icons/nav-ico.png'
</script>

<template>
    <nav>
        <h3>
            <a href="#"><img style="width: 22px;" :src="NavIco" alt=""></a>
        </h3>
        <div class="navigation">
            <ul>
                <li id="aboutme">About me</li>
                <li id="progetti">Progetti</li>
                <li id="contatti">Contatti</li>
            </ul>
        </div>
    </nav>
</template>