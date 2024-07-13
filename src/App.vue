<script setup lang="ts">
import HelloWorld from "./components/HelloWorld.vue";
import EmitPropertiesBasic from "./emitProperties/EmitPropertiesBasic.vue";
import EmitPropertiesArgs from "./emitProperties/EmitPropertiesArgs.vue";
import DefineEmitOption1 from "./defineEmits/DefineEmitOption1.vue";
import DefineEmitOption2 from "./defineEmits/DefineEmitOption2.vue";

const emitPropertiesBasic = () => {
  alert("emit properties basic");
};

const emitPropertiesArgs = (e: Event, saludo: string) => {
  const inputKeyup = e.currentTarget as HTMLInputElement;
  const msj = `${saludo} ${inputKeyup.value}`;
  alert(msj);
};

const myEmitDefine = (num: number, saludo: string) => {
  const msj = `arg1: ${num} arg2: ${saludo}`;
  alert(msj);
  return msj;
  // esta funcion que se pasa como el emit siempre retorna undefined
  // un que explicitamente retornes un dato
};

const myDefineEmitEvent = (msj: string) => {
  alert(msj);
};
</script>

<template>
  <HelloWorld msg="Vite + Vue" />
  <h2>Emit properties</h2>
  <EmitPropertiesBasic @my-emit-properties="emitPropertiesBasic" />
  <EmitPropertiesArgs @my-emit-properties-args="emitPropertiesArgs" />
  <h2>Define Emits</h2>
  <DefineEmitOption1
    @my-emit-define="myEmitDefine"
    @my-emit-define-event="myDefineEmitEvent"
  />
  <DefineEmitOption2 @my-emit-define="myEmitDefine" />
</template>

<style scoped></style>
