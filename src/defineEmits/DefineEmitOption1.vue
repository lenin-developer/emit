<script setup lang="ts">
// esta opcion es la mas nueva 3.3+
const emit = defineEmits<{
  myEmitDefine: [arg1: number, arg2: string];
  myEmitDefineEvent: [event: Event, mensaje: string]
}>();

const saludar = () => {
  const myNumber: number = 25;
  const myString: string = 'hola';
  const res = emit('myEmitDefine', myNumber, myString);
  alert(res);
};


const saludarEvent = (e) => {
  const msj = e?.target?.value
  const res = emit('myEmitDefineEvent', msj);
};


const funWhintArgs = (arg1: number, arg2: string) => {
  emit('myEmitDefine', arg1, arg2);
};
</script>

<template>
  <button @click="saludar">define emit op1</button>
  <input @keyup.enter="saludarEvent">escriba y de enter</input>
  <button @click="() => funWhintArgs(2, 'itemmmm')">define emit op1</button>


</template>

<style scoped>
button {
  display: block;
}
</style>
