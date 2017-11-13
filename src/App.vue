<template>
  <div id="app">

    <!--
      Vue Component of a responsive magazine mock-up
      ===
      Available props:
      - img -> source of a image
      - alt -> alt text of the image - default set to ''
      - width -> a value in any css units
     -->
    <magazine :img="'/static/magazine-cover.png'"></magazine>

  </div>
</template>

<script>
import Magazine from './components/Magazine';
export default {
  name: 'app',
  components: {
    Magazine
  }
}
</script>


<style lang="sass">

body
  margin: 0
  padding: 0
  font-size: 16px
  background-color: #fafafa

#app
  display: flex
  justify-content: center // centering content horizontally
  align-items: center // centering content vertically
  height: 100vh

</style>
