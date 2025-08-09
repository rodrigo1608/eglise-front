<script setup>

import Organizations from '@/Organizations.vue'
import Users from '@/Users.vue'


const componentMap = {
    'Users': Users,
    'Organizations': Organizations
}

defineProps({
    'currentEntity': String
})



</script>

<template>
    <main class="w-full">
        <keep-alive>
            <component :is="componentMap[currentEntity]" />
        </keep-alive>
    </main>
</template>