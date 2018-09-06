<template>
  <div class="home">
    <p>{{ body }}</p>
  </div>
</template>

<script>
export default {
    name: 'news',

    data () {
        return {
            body: 'body content news...'
        }
    }
}
</script>

<style>
h3 {
  margin: 40px 0 0;
}
</style>
