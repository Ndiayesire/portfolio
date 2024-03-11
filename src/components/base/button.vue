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
    <button @click="todo" class="bg-black text-white font-bold uppercase text-sm px-6 py-3 rounded shadow outline-none focus:outline-none ease-linear transition-all duration-150">
        {{ name }}
        <i :class="icon"></i>
    </button>
</template>