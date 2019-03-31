<template>
  <div id="shabon" @click="animation">
    <transition>
      <ShabonOrign
        v-if="!isClick"
        :color="color"/>
    </transition>
    <ShabonAnimation
      v-if="isClick"
      :color="color"/>
  </div>
</template>

<script>
import ShabonOrign from './ShabonOrign'
import ShabonAnimation from './ShabonAnimation'

export default {
  name: 'shabon',
  components: {
    ShabonOrign,
    ShabonAnimation
  },
  props: {
    color: {
      type: String,
      default: '#9F9'
    }
  },
  data () {
    return {
      isClick: false
    }
  },
  methods: {
    animation: function () {
      if (!this.isClick) {
        this.isClick = true
        let id = setTimeout(() => {
          clearTimeout(id)
          this.isClick = false
        }, 2000)
      }
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
#shabon {
  position: relative;
  width: 200px;
  height: 200px;
}
.v-enter-active {
  transition: opacity .5s;
}
.v-enter {
  opacity: 0
}
</style>
