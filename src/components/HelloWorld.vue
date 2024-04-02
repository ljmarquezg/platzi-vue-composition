<template>
  <div class="hello">
    <h1>{{ fullName }}</h1>
  </div>
</template>

<script>
import { computed, toRefs } from 'vue';

export default {
  props: {
    firstName: String,
    lastName: String
  },
  setup(props, context) {
    const {firstName, lastName} = toRefs(props);
    const fullName = computed(() => `${firstName.value} ${lastName.value}`);

    console.log(context.attrs); // all attributes passed to the component that are not props
    context.emit('update:firstName', 'John') // emit an event to parent component to update firstName prop
    context.expose({fullName}) // expose fullName to parent component
    context.slots() // get all slots passed to the component
    return {
      fullName
    };
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
