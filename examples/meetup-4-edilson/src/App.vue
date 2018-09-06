<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">

    <ul>
      <li>
        <a href="#" v-on:click="page = 'home'">Home</a>
      </li>
      <li>
        <a href="#" v-on:click="page = 'news'">News</a>
      </li>
      <li>
        <a href="#" v-on:click="page = 'contact'">Contact</a>
      </li>
    </ul>

    <h1>{{ page }}</h1>

    <component v-bind:is="page"></component>
  </div>
</template>

<script>
import Home from './components/Home'
import News from './components/News'
import Contact from './components/Contact'
export default {
  name: 'app',

  data () {
    return {
      page: ''
    }
  },

  components: { Home, News, Contact }
}
</script>
