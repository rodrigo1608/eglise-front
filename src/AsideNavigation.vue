<script setup>


const props = defineProps({

    'navigationItems': Array,

    'isAsideOpen': Boolean

})

</script>

<template>
    <nav class="mt-4">
        <ul>
            <li v-for="item in props.navigationItems" :key="item.name" class="border-b-1 md:border-none border-egray">
                <a :href="item.href"
                    class="flex items-center p-4 md:rounded-full hover:bg-egray  active:scale-99 active:bg-elighter ">
                    <i :class="item.icon" class="w-8 text-center text-sm leading-none"></i>
                    <span class="overflow-hidden whitespace-nowrap transition-[max-width,opacity] duration-300"
                        :class="isAsideOpen ? 'max-w-[150px] ml-2 opacity-100' : 'max-w-0 opacity-0'">
                        {{ item.name }}
                    </span>
                </a>
            </li>
        </ul>
    </nav>
</template>