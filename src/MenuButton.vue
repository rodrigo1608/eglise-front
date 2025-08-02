<script setup>
const emit = defineEmits('toggle')
</script>

<template>

    <button @click="emit('toggle')" class="rounded-full w-8 h-8 flex items-center justify-center
             hover:bg-egray cursor-pointer active:scale-90 transition-all duration-300">
        <i class="fa-solid fa-bars text-sm inline-flex leading-none"></i>
    </button>

</template>