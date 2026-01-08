<template>
    <div class="relative max-w-7xl mx-auto px-4 sm:px-6 z-10">
        <h3 class="text-lg font-semibold">{{ greeting }}! 🍷</h3>
        <button class="mt-2 px-3 py-2 rounded-lg border" @click="pickRandom">
            Nuovo saluto
        </button>
    </div>
</template>

<script setup lang="ts">
    import { ref } from "vue";

    const props = defineProps<{ messages: string[] }>();
    const greeting = ref(props.messages[0]);

    function pickRandom() {    
        const i = Math.floor(Math.random() * props.messages.length);
        greeting.value = props.messages[i];
    }
</script>
