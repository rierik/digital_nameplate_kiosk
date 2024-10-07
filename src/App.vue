<script setup>
import { io } from 'socket.io-client';
import { ref, reactive } from 'vue';

const name = ref('');

const URL = process.env.NODE_ENV === 'production' ? undefined : 'http://localhost:3000';

const socket = io(URL);

socket.on('nameUpdated', (newName) => {
  name.value = newName;
});
</script>

<template>{{ name }}</template>

<style scoped></style>
