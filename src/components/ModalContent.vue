<template>
  <div>
    <h2>{{ title }}</h2>
    <p>{{ msg }}</p>
    <button @click="$emit('close')">Close</button>
  </div>
</template>

<script setup>
defineProps({
  title: String,
  msg: String
})

defineEmits('close')
</script>
