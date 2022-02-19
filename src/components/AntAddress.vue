<template>
  <div>
    <a-input v-model:value="formValue.street" placeholder="Enter street" />
    <a-input v-model:value="formValue.city" placeholder="Enter city" />
    <a-input v-model:value="formValue.state" placeholder="Enter state" />
    <a-input v-model:value="formValue.zip" placeholder="Enter zip" />
  </div>
</template>

<script setup>
import { defineProps, defineEmits, computed } from 'vue';
const props = defineProps({
  modelValue: {
    type: Object,
    required: true,
  },
});
const emit = defineEmits(['update:modelValue']);

const formValue = computed({
  get() {
    return props.modelValue;
  },
  set(value) {
    emit('update:modelValue', value);
  },
});
</script>

<style scoped></style>
