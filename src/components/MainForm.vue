<template>
  <form @submit.prevent="onSubmit">
    <input name="name" v-model="person.name" />
    <input name="email" v-model="person.email" />
    <Address v-model="person.address" />
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
import { reactive } from '@vue/reactivity';
import Address from './Address.vue';

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

// const onAddressChange = (newAddress) => {
//   person.address = { ...newAddress };
// };

const onSubmit = () => {
  console.log({ ...person.address });
};
</script>

<style lang="scss" scoped></style>
