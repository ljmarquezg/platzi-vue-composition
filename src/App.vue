<template>
  <img alt="Vue logo" src="./assets/logo.png" />
  <component :is="currentComponent" />
</template>

<script>
import HelloWorld from "./components/HelloWorld.vue";

export default {
  name: "App",
  components: {
    HelloWorld,
  },
  data() {
    return {
      currentComponent: "HelloWorld",
    };
  },
  beforeCreate() {
    console.log("beforeCreate", this.$data, this.$el);
  },
  created() {
    console.log("created", this.$data, this.$el);
  },
  beforeMount() {
    console.log("beforeMount", this.$data, this.$el);
  },
  mounted() {
    console.log("mounted", this.$data, this.$el);
  },
  beforeUpdate() {
    console.log("beforeUpdate", this.$data, this.$el);
  },
  updated() {
    console.log("updated", this.$data, this.$el);
  },
  beforeUnmount() {
    console.log("beforeDestroy", this, this.data$);
  },
  unmounted() {
    console.log("destroyed", this, this.data$);
  },
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
</style>
