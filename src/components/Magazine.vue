<template>
  
  <div v-if="img" class="magazine" :style="`width: ${width}`">
    <div class="magazine-cover">
      <img :src="img" :alt="alt">
    </div>
  </div>

</template>

<script>
export default {
  name: 'Magazine',
  props: {
    img: {
      type: String
    },
    alt: {
      type: String,
      default: ''
    },
    width: {
      type: String,
      default: '360px'
    }
  }
}
</script>

<style lang="sass" scoped>

// CONFIG 
// ==================================================

$black: #000000
$white: #ffffff
  
// THE MAGIC - rounded borders give realistic look
// ==================================================
=magazine-border-radius()
  border-top-left-radius: 2em
  border-top-right-radius: 2em
  border-bottom-right-radius: 2em
  border-bottom-left-radius: 3em


// MAGAZINE MOCKUP 
// ==================================================

.magazine
  position: relative
  font-size: 1px

  // THE MAGIC - shadows give depth
  // ==================================================
  box-shadow: -2em 2em 3em rgba($black, .06), 0 0 3em rgba($black, .08)

  &::after
    content: ""
    position: absolute
    top: 0
    left: 0
    width: 90%
    height: 100%
    +magazine-border-radius()
    // THE MAGIC - This shadow simulates the light source
    // ==================================================
    box-shadow: -3em 4em 16em 2em rgba($black, .2)
    z-index: 0

.magazine-cover
  position: relative
  +magazine-border-radius()
  overflow: hidden
  z-index: 1
  
  &::before
    content: ""
    position: absolute
    top: 0
    left: 0
    width: 100%
    height: 100%
    // THE MAGIC - the magazine look
    // ==================================================
    background: linear-gradient(to right, rgba($black,.06) 0%, rgba($white,0) 1%, rgba($white,.09) 3%, rgba($black,.05) 3%, rgba($white,.5) 3.6%, rgba($black,.06) 3%, rgba($white,.1) 26%, rgba($white,.1) 60%)

  img
    width: 100%

</style>


