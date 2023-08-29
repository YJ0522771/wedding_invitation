<template>
  <div id="app">
    브라우저 화면 크기 : <span>{{ windowWidth }}</span> * <span>{{ windowHeight }}</span>
  </div>
</template>

<script>

export default {
  name: 'App',
  components: {
  },
  data: function() {
    return {
      windowWidth: window.innerWidth,
      windowHeight: window.innerHeight
    }
  },
  mounted() {
    window.addEventListener('resize', () => {
      this.windowWidth = window.innerWidth
      this.windowHeight = window.innerHeight
      console.log(this.isMobile)
    })
  },
  computed: {
    isMobile() {
      return this.windowWidth <= 768
    }
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
