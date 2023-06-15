<template>
  <img alt="Vue logo" src="./assets/logo.png">
  <HelloWorld msg="Welcome to Your Vue.js App"/>
  {{ test }}
  {{ data[0] }}
  <p class="w-96 bg-green-300">
    Lorem ipsum dolor sit amet, consectetur adipisicing elit. Veritatis laborum distinctio est corrupti voluptatem, perferendis saepe nesciunt explicabo aliquid, fuga accusamus provident tempore reiciendis amet eveniet rem voluptatibus enim! Rem.
  </p>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'App',
  components: {
    HelloWorld
  },

  data(){
    return {
      test:"sds",
      data:[]
    }
  },

  // fetch this api https://restcountries.com/v3.1/all
  mounted(){
    fetch('https://restcountries.com/v3.1/all')
    .then(res => res.json())
    .then(res => {
      this.data = res;
      console.log(res);
    })
    .catch(err => console.log(err))
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
