<script setup lang="ts"></script>

<template>
  
  <input  @keyup.enter="$emit('myEmitPropertiesArgs', $event,  'soy un args')"></input>
  <span>escriba y de enter</span>
</template>

<style scoped></style>
