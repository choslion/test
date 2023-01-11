<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <h2>{{ test }}</h2>
    <h2>{{ login.id }}</h2>
    <!-- <h2>{{ name1 }}</h2>
    <h2>{{ fuckVue }}</h2> -->
    <!-- <button v-on:click="rename">Click!</button> -->
    <button v-on:click="reacti">Click!</button>
  </div>
</template>

<script>
import { reactive } from 'vue';
export default {
  name: 'HelloDefaluts',
  props: {
    msg: String,
  },
  setup() {
    const test = 'Test Vue';
    const login = reactive({
      id: 'eddy',
    });
    const reacti = () => {
      login.id = 'eden';
    };
    // 바뀔대상에 ref() 써줌
    // let name1 = ref('eddy');
    // const fuckingVue = function () {
    //   return '안녕' + name1;
    // };
    // const fuckingVue = (name1) => {
    //   name1 = 'eden';
    //   console.dir(name1);
    //   return '안녕' + name1;
    // };
    // const fuckVue = fuckingVue(name1);

    // const rename = function () {
    //   name1.value = 'potato';
    // };
    return {
      // 위 아래는 같다.
      test,
      // name1,
      // fuckingVue,
      // fuckVue,
      login,
      reacti,
      // rename,
    };
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
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
