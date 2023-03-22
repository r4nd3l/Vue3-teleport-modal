<template>
  <div>
    <h2>{{ title }}</h2>
    <p>{{ msg }}</p>
    <button @click="$emit('close')">Close Modal 2</button>
  </div>
</template>

<script setup>
defineProps({
  title: String,
  msg: String
})

defineEmits('close')
</script>
