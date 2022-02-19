<template>
  <div>
    <input name="street" v-model="formValue.street" />
    <input name="city" v-model="formValue.city" />
    <input name="state" v-model="formValue.state" />
    <input name="zip" v-model="formValue.zip" />
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

// const formValue = reactive({
//   ...props.modelValue,
// });

// watch(formValue, async (newValue) => {
//   emit('update:modelValue', newValue);
// });
</script>

<style scoped></style>
