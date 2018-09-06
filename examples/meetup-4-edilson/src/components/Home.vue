<template>
  <div class="home">
    <p>{{ body }}</p>
  </div>
</template>

<script>
export default {
    name: 'home',

    data () {
        return {
            body: 'body content home...'
        }
    }
}
</script>

<style>
h3 {
  margin: 40px 0 0;
}
</style>
