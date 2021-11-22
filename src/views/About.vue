<template>
  <div class="header">
    <Header title = "RoDev Market"/>
  </div>

  <br>
  
  <div class="about">
    <p>
      This site was designed to provide a safe 
      marketplace for developers and clients to quickly 
      create new projects together.
      </p>
  </div>
</template>

<script>
// @ is an alias to /src
// import HelloWorld from '@/components/HelloWorld.vue'
import Header from "../components/Header.vue"

export default {
  name: 'About',
  components: {
    Header
  }
}
</script>
