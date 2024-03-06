<script setup> 
    const emit = defineEmits(['onClick'])
    const props = defineProps({
        name: String,
        icon: String
    })

    const todo = () => {
        emit('onClick')
    }
</script>

<template>
    <button @click="todo" class="text-white bg-gray-800 hover:bg-gray-600 focus:outline-none font-medium rounded-lg text-sm px-4 py-2 text-center">
        {{ name }}
        <i :class="icon"></i>
    </button>
</template>