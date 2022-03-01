<script setup>
defineEmits(['onClick'])
const prop = defineProps({
    buttonName: {
        type: String,
        require: true
    }
})
console.log('['+prop.buttonName+']' + ' from \'BaseButton.vue\'');
</script>
 
<template>
<button class="button-color" @click="$emit('onClick')">{{ buttonName }}</button>
</template>
 
<style scoped>
.button-color{
    background-color: salmon;
}
</style>