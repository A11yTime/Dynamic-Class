<template>
  <input ref="email" />
</template>

<script>
export default {
  methods: {
    focusInput() {
      this.$refs.email.focus();
    }
  }
}
</script>