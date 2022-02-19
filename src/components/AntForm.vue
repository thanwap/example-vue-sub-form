<template>
  <form @submit.prevent="onSubmit">
    <a-input v-model:value="person.name" placeholder="Enter name" />
    <a-input v-model:value="person.email" placeholder="Enter email" />
    <AntAddress v-model="person.address" />
    <button type="submit">Submit</button>
  </form>
  <div style="margin-top: 20px">
    <div>{{ person.name }}</div>
    <div>{{ person.email }}</div>
    <div>{{ person.address.street }}</div>
    <div>{{ person.address.city }}</div>
    <div>{{ person.address.state }}</div>
    <div>{{ person.address.zip }}</div>
  </div>
</template>

<script setup>
import { reactive } from 'vue';
import AntAddress from './AntAddress.vue';

const person = reactive({
  name: '',
  email: '',
  address: {
    street: 'a',
    city: 'b',
    state: 'c',
    zip: 'd',
  },
});

const onSubmit = () => {
  console.log({ ...person.address });
};
</script>

<style scoped></style>
