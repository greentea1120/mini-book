<template>
  <div id="app">
    <Welcome />
    <Guide />
    <router-view></router-view>
  </div>
</template>
<script>
import Welcome from './components/Welcome'
import Guide from './components/Guide'
export default {
  components: {
    Welcome,
    Guide
  }
}
// rem config
document.addEventListener('DOMContentLoaded', () => {
  const html = document.querySelector('html')
  let fontSize = window.innerWidth / 10
  fontSize = fontSize > 50 ? 50 : fontSize
  html.style.fontSize = fontSize + 'px'
})
</script>
<style>
</style>
