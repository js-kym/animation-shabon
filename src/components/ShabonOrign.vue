<template>
  <div id="shabon-orign">
    <!-- <img :src="require('../assets/svg/shabon_orign.svg')"> -->
    <svg id="shabon_orign" image-rendering="auto" baseProfile="basic" version="1.1" x="0px" y="0px" width="200" height="200" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink"><g id=".__E3.__82.__B7.__E3.__83.__BC.__E3.__83.__B3-1f0r1" overflow="visible"><path :fill="color" stroke="none" d="M142.4,57.55 Q124.85,40 100,40 75.2,40 57.55,57.55 40,75.15 40,100 40,124.8 57.55,142.4 75.2,160 100,160 124.85,160 142.4,142.4 160,124.8 160,100 160,75.15 142.4,57.55Z"/></g></svg>
  </div>
</template>

<script>
export default {
  name: 'shabon-orign',
  props: {
    color: {
      type: String,
      default: '#9F9'
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
#shabon-orign {
  position: absolute;
  top: 0;
  left: 0;
  width: 200px;
  height: 200px;
}
</style>
