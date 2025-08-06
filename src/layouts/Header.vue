<script setup>
import Avatar from '@/Avatar.vue';
import MenuButton from '@/MenuButton.vue';

const props = defineProps({
    // 'isAsideOpen': Boolean,
    'toggleAside': Function
})

</script>

<template>

    <header class="p-4">

        <nav class="flex justify-between items-center">
            <MenuButton @toggle="toggleAside" class="sm:hidden" />
            <a href="#" class="font-[Crimson_Pro] text-gray-500 text-lg tracking-wider font-semibold">Matrisi</a>
            <Avatar />
        </nav>

    </header>

</template>