<template>
  <div id="app">
    <Shabon
      v-for="n in shabonNum"
      :key="'shabon' + n"
      :color="color[n % 5]"
      :shabonInfo="shabonInfo[n - 1]"/>
  </div>
</template>

<script>
import Shabon from './components/Shabon'

export default {
  name: 'App',
  components: {
    Shabon
  },
  data () {
    return {
      shabonNum: 15,
      color: [
        '#EB5D00',
        '#B7B3B2',
        '#B0DCEE',
        '#B8B2EA',
        '#ECD070'
      ],
      shabonInfo: [],
      shabonSize: 200
    }
  },
  methods: {
    setShabonInfo: function () {
      let scale = this.calcScale()
      let pos = this.calcPos(scale)
      // なるべく重ならないようにする
      let result = this.shabonInfo.filter((val) => {
        return ((val.x - this.shabonSize * scale) < pos.x && (val.x + this.shabonSize * scale) > pos.x && (val.y - this.shabonSize * scale) < pos.y && (val.y + this.shabonSize * scale) > pos.y)
      })
      if (result.length > 0) {
        this.setShabonInfo()
      } else {
        this.shabonInfo.push({
          x: pos.x,
          y: pos.y,
          scale: scale
        })
      }
    },
    calcPos: function (scale) {
      let ranX = Math.floor(Math.random() * ((window.innerWidth - this.shabonSize) + 1))
      let ranY = Math.floor(Math.random() * ((window.innerHeight - this.shabonSize) + 1))
      return {
        x: ranX,
        y: ranY
      }
    },
    calcScale: function () {
      let ranScale = Math.floor(Math.random() * 2)
      return ranScale === 0 ? 0.8 : 1
    }
  },
  created () {
    // スマホサイズ
    if (window.innerWidth < 750) {
      this.shabonNum = 3
    }
    for (let i = 0; i < this.shabonNum; i++) {
      this.setShabonInfo()
    }
  }
}
</script>

<style>
body {
  margin: 0;
  padding: 0;
}
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  width: 100vw;
  height: 100vh;
  background-color: #FBFBF0;
}
.shabon.float:nth-child(odd) {
  animation: float_animation_odd 3s linear infinite;
  /* transform-origin: 50% 50%; */
}
@keyframes float_animation_odd {
  0% { transform: translateY(0) }
  33.33333% { transform: translateY(-6px) }
  66.66667% { transform: translateY(0) }
  100% { transform: translateY(0) }
}
.shabon.float:nth-child(even) {
  animation: float_animation_even 4s linear infinite;
  /* transform-origin: 50% 50%; */
}
@keyframes float_animation_even {
  0% { transform: translateY(-6px) }
  33.33333% { transform: translateY(0) }
  66.66667% { transform: translateY(-6px) }
  100% { transform: translateY(-6px) }
}
</style>
