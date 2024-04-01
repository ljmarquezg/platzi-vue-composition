<template>
  <div class="hello">
    <h1>{{ counterRef }}</h1>

    <h1>{{ reactiveObject }}</h1>
  </div>
</template>

<script>
import { reactive, ref, watch } from 'vue';

export default {
  setup() {
    const counterRef = ref(0); // Crea referencia reactiva
    const reactiveObject = reactive({ // crea ubicación reactivo
      counter: 0
    });

    setInterval(() => {
      counterRef.value++;
      reactiveObject.counter++;
    }, 1000);

    // watchers para una variable reactive
    watch(() => reactiveObject, (newValue, oldValue) => {
      console.log('reactiveObject', newValue, oldValue);
    });

    // watchers para una sola propiedad de reactive
    watch(() => reactiveObject.counter, (newValue, oldValue) => {
      console.log('counter', newValue, oldValue);
    });

    // Watchers para ref
    watch(counterRef, (newValue, oldValue) => {
      console.log('counterRef', newValue, oldValue);
    });
    return {
      counterRef,
      reactiveObject
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style
    scoped
    lang="scss"
>
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
