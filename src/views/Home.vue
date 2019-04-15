<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png">
    <renderless-toggle />
    <!-- <HelloWorld msg="Welcome to Your Vue.js App"/> -->
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue'
import RenderlessToggle from '@/components/RenderlessToggle'

export default {
  name: 'home',
  components: {
    HelloWorld,
    RenderlessToggle,
  }
}
</script>
