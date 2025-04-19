<script setup>
import { computed } from 'vue';

const props = defineProps({
    text: {
        type: String,
        required: true
    },
    repeat: {
        type: Number,
        default: 8
    }
});

const repeatedText = computed(() => `${props.text} `.repeat(props.repeat).trim());
</script>

<template>
    <div class="title-wrapper">
        <div class="title">
            <h2 class="title-h2">
                {{ repeatedText }}
            </h2>
        </div>
    </div>
</template>

<style>
.title-wrapper {
    height: 180px;
    position: relative;
}

.title {
    border-top: 1px solid var(--giallo);
    border-bottom: 1px solid var(--giallo);
    width: 100vw;
    height: min-content;
    padding: 10px 0;
    transform: rotate(-5deg) scale(1.1);
    background-color: #171717;
    display: block;
    line-height: 1;
}

.title-wrapper::before {
    content: "";
    width: 100vw;
    height: 80%;
    position: absolute;
    bottom: 0;
    left: 0;
    background-color: #171717;

}

.title-h2 {
    margin: 0;
    font-size: 64px;
    white-space: nowrap;
    color: transparent;
    -webkit-text-stroke: 1px var(--giallo);
    animation: section-title 10s linear infinite;
}


@keyframes section-title {
    0% {
        transform: translateX(-50%)
    }

    100% {
        transform: translateX(0%)
    }
}
</style>