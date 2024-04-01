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
  setup(props) {
    const {firstName, lastName} = toRefs(props);
    const fullName = computed(() => `${firstName.value} ${lastName.value}`);

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
