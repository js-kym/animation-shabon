<template>
  <div class="shabon float" @click="animation" :style="setShabonPos">
    <div :style="setShabonScale">
      <transition>
        <ShabonOrign
          v-if="!isClick"
          :color="color"/>
      </transition>
      <ShabonAnimation
        v-if="isClick"
        :color="color"/>
    </div>
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
    },
    shabonInfo: {
      type: Object,
      default: function () {
        return {}
      }
    }
  },
  data () {
    return {
      isClick: false
    }
  },
  computed: {
    setShabonPos: function () {
      // return {}
      // let info = this.setShabonInfo()
      return {
        top: this.shabonInfo.y + 'px',
        left: this.shabonInfo.x + 'px'
      }
    },
    setShabonScale: function () {
      // return {}
      // let info = this.setShabonInfo()
      return {
        transform: 'scale(' + this.shabonInfo.scale + ',' + this.shabonInfo.scale + ')'
      }
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
.shabon {
  position: absolute;
  width: 200px;
  height: 200px;
  -webkit-tap-highlight-color: rgba(0, 0, 0, 0);
}
.v-enter-active {
  transition: opacity .5s;
}
.v-enter {
  opacity: 0
}
</style>
