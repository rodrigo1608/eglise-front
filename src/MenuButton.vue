<script setup>
const emit = defineEmits('toggle')
</script>

<template>

    <button @click="emit('toggle')" class="rounded-full p-4 flex items-center justify-center
             hover:bg-egray cursor-pointer active:scale-90 active:bg-edark-gray active:text-elight">
        <i class="fa-solid fa-bars text-lg  leading-none"></i>
    </button>

</template>