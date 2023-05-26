
import { text } from 'body-parser';

<template>
    <button @click="onClick()" class="btn">
      {{ text }}
    </button>
  </template>
  
  <script>
  export default {
    name: 'Button',
    props: {
      text: String,
    },
    methods: {
      onClick() {
        this.$emit('btn-click')
      },
    },
  }
  </script>
  <style>
.btn {
    margin-bottom: 1rem;
}
</style>