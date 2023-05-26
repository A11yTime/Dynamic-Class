<template>
  <div>
    <ButtonSend @btn-click="showInput" text="Send Focus"/>
  </div>
  <div v-if="inputIsVisible">
    <CustomInput ref="email" />
  </div>
</template>

<script>
import CustomInput from './components/CustomInput.vue'
import ButtonSend from './components/ButtonSend.vue'

export default {
  name: 'App',
  components: {
    CustomInput,
    ButtonSend,
  },
  data() {
    return {
      inputIsVisible: false,
    };
  },
  mounted() {
    this.focusInput();
  },
  methods: {
    showInput() {
      // Show the input component
      this.inputIsVisible = true;

      // Focus the component, but we have to wait
      // so that it will be showing first.
      this.nextTick(() => {
        this.focusInput();
      });
    },
    focusInput() {
      this.$refs.email.$el.focus();
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
