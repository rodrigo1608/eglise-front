<script setup>
import { computed } from 'vue'
import MenuButton from '@/MenuButton.vue'

const props = defineProps({
    'isAsideOpen': Boolean,
    'toggleAside': Function
})

// Define as classes para a versão desktop, que empurra o conteúdo
const asideDesktopClasses = computed(() => {
    return [
        'h-dvh', 'bg-elight', 'transition-all', 'duration-300', 'p-4',
        'hidden md:block',
        props.isAsideOpen ? 'md:w-60' : 'md:w-16',
        props.isAsideOpen ? 'md:overflow-auto' : 'md:overflow-hidden'
    ]
})
</script>

<template>
    <!-- Versão Mobile (com animação de deslizar) -->
    <Transition name="slide">
        <aside v-if="isAsideOpen" class="md:hidden h-dvh bg-elight w-full transition-transform duration-300 transform">
        </aside>
    </Transition>

    <!-- Versão Desktop (com animação de largura) -->
    <aside :class="asideDesktopClasses">
        <MenuButton @toggle="toggleAside" />
    </aside>

</template>

<style scoped>
/* Transição de deslizar para mobile */
.slide-enter-from,
.slide-leave-to {
    transform: translateX(-100%);
}

.slide-enter-to,
.slide-leave-from {
    transform: translateX(0);
}

.slide-enter-active,
.slide-leave-active {
    transition: transform 0.3s ease-in-out;
}
</style>
