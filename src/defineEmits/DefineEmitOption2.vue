al parecer un Emit siempre retorna undefined, aun que explicitamente retornes un
dato

<script setup lang="ts">
const emit = defineEmits<{
  (e: 'myEmitDefine', arg1: number, arg2: string): void; // string
}>();

const saludar = () => {
  const myNumber: number = 25;
  const myString: string = 'hola';
  const res = emit('myEmitDefine', myNumber, myString);
  alert(res);
};
</script>

<template>
  <br />
  <button @click="saludar">define emit op2</button>
</template>

<style scoped>
button {
  display: block;
}
</style>
