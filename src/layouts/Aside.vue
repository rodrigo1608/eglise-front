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
        'h-dvh', 'bg-elight', 'transition-all', 'duration-300',
        'hidden sm:block',
        props.isAsideOpen ? 'sm:w-60' : 'sm:w-0',
        props.isAsideOpen ? 'sm:overflow-auto' : 'sm:overflow-hidden'
    ]
})
</script>

<template>
    <!-- Versão Mobile (com animação de deslizar) -->
    <Transition name="slide">
        <aside v-if="isAsideOpen" class="sm:hidden h-dvh bg-elight w-full transition-transform duration-300 transform">
            <!-- <MenuButton @toggle="toggleAside" /> -->
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
