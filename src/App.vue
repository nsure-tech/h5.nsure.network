<template>
  <div id="app">
    <Header />
    <router-view/>
  </div>
</template>

<script>
import Header from '@/components/Header'
export default {
  components: {
    Header
  }
}
</script>


<style lang="less">
@font-face {
  font-family: Open Sans;
  src:url('./assets/font/OpenSans-Regular.ttf')
}
@font-face {
  font-family: ArialMT;
  src:url('./assets/font/ArialMT.ttf')
}
@font-face {
  font-family: Arial BoldMT;
  src:url('./assets/font/Arial-BoldMT.otf')
}
#app {
  font-family: Open Sans,Avenir,Helvetica,Arial,sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #000;
}
</style>

