<script setup>
import { ref } from 'vue';
defineProps({
  greet: String
})
</script>
 
<template>
<h1>{{greet}}</h1>
</template>
 
<style>

</style>