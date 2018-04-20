<template>
  <div id="app">
    <p>
      <button @click="increment">+</button>
    </p>
    <counter></counter>
  </div>
</template>

<script>
import Vue from 'vue'
import Vuex from 'vuex'
Vue.use(Vuex)
const store = new Vuex.Store ({
  state: {
    count: 0
  },
  mutations:{
    increment ( state ){
      state.count++;
    }
  }
});

import counter from "./counter.vue"

export default {
  name: 'app',
  store,
  data () {
    return {
      msg: 'Welcome to Your Vue.js App'
    }
  },
  components:{
    counter
  },
  computed: {
    count () {
	    return store.state.count
    }
  },
  methods: {
    increment () {
      store.commit('increment')
    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

h1, h2 {
  font-weight: normal;
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
