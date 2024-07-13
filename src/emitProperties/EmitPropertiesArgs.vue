<script setup lang="ts"></script>

<template>
  <input @keyup.enter="$emit('myEmitPropertiesArgs', $event, 'soy un args')" />
  <span>escriba y de enter</span>
</template>

<style scoped></style>
