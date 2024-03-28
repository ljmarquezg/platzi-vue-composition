<template>
<div>
  <button @click="toggle">Abrir Modal</button>
  <teleport to="body">
    <div v-show="show" class="modal">
      <h1>Titulo</h1>
      <p>lorem</p>
      <button @click="toggle">Cerrar</button>
    </div>
  </teleport>
</div>
</template>

<script>
export default {
  name: "ModalComponent",
  methods: {
    toggle() {
      this.show = !this.show;
    },
  },
  data() {
    return {
      show: false,
    };
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
