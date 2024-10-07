<script setup>
import HelloWorld from './components/HelloWorld.vue';
import { io } from 'socket.io-client';

const socket = io('http://localhost:3000'); // WebSocket 연결

// 서버에서 'nameUpdated' 이벤트 수신
socket.on('nameUpdated', (newName) => {
  this.name = newName; // 화면에 새로운 이름 반영
});
</script>

<template></template>

<style scoped></style>
