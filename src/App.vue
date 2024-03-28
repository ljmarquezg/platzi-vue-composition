<template>
  <img
    alt="Vue logo"
    src="./assets/logo.png"
  />
  <button @click="show = !show">Menu</button>
  <transition name="fade">
    <MenuComponent v-show="show" />
  </transition>
</template>

<script>
import MenuComponent from "./components/Menu.vue";

export default {
  name: "App",
  components: {
    MenuComponent
  },
  data() {
    return {
      show: false
    };
  }
};
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.5s ease;
}

.fade-enter-from,
.fade-leave-to {
  opacity: 0;
}
</style>
