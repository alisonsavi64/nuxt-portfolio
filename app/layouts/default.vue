<template>
    <div class="container mx-auto max-w-2xl">
        <header class="flex justify-between items-center mt-5">
            <div class="flex items-center space-x-12">
                <div>
                    <NuxLink class="text-xl font-semibold p-2 hover:bg-gray-200" to="/">Alison Savi</NuxLink>
                </div>
                <Menu/>
            </div>
            <ClientOnly>
                <ColorModeSelector/>
            </ClientOnly>
        </header>
        <main class="mt-10 p-2">
            <slot/>
        </main>    
    </div>
</template> 

<style>

body{
    @apply bg-white dark:bg-gray-900 text-gray-700 dark:text-gray-200
}    

</style>

<script setup>
    definePageMeta({
        colorMode: 'dark'
    })
</script>