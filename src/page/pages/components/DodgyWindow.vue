<script setup lang="ts">
defineProps<{
    videoSrc?: string
    imageSrc?: string
    poster?: string
}>()
</script>

<template>
    <div class="windows-container" id="dodgyWindow">
        <div class="windows-header">
            <span class="close-btn">X</span>
        </div>
        <div class="windows-content">
            <video v-if="videoSrc" data-aos="fade-up" class="gif" :src="videoSrc" autoplay loop playsinline muted
                :poster="poster" />
            <img v-else-if="imageSrc" data-aos="fade-up" class="image" :src="imageSrc" alt="window content" />
            <p v-else>Nessun contenuto disponibile.</p>
        </div>
    </div>
</template>

<style scoped>
.windows-container {
    border: 2px solid var(--blu);
    width: 300px;
    background: var(--scurissimo);
    margin: auto;
    transition: top 0.1s ease, left 0.1s ease;
}

.windows-header {
    background-color: var(--blu);
    color: white;
    padding: 0.3rem 0.6rem;
    display: flex;
    justify-content: space-between;
    align-items: center;
    font-size: 0.9rem;
}

.windows-header .close-btn {
    cursor: pointer;
    font-weight: bold;
    margin-right: auto;
    margin-left: 0.2rem;
    color: var(--scurissimo);
}

.windows-content {
    padding: 1rem;
}

.gif,
.image {
    width: 100%;
    display: block;
}
</style>
