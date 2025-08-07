<template>
    <div class="flex space-x-2 items-center">
        <div v-if="showNextNodeLabel" class="text-gray-500 text-xs">Change to {{ nextNode }}</div>
        <button @click="toggleMode" @mouseenter="showNextNodeLabel = true" @mouseleave="showNextNodeLabel = false" class="hover:bg-gray-100 dark:hover:bg-gray-400 px-2 py-1 text-gray-500">{{ nextNode }}</button>
    </div>
</template>

<script setup>
    const colorMode = useColorMode()

    const showNextNodeLabel = ref(false);

    const mode = [
        'system',
        'light',
        'dark'
    ]

    const nextNode = computed(() => {
        const currentNodeIndex = mode.indexOf(colorMode.preference)
        let nextNodeIndex = null;
        if(currentNodeIndex + 1 == mode.length){
            nextNodeIndex = 0;
        }else{
            nextNodeIndex = currentNodeIndex + 1 
        }
        return mode[nextNodeIndex]
    })

    const toggleMode = () => colorMode.preference = nextNode.value

</script>