<template>
  <div class="myclass">
    <label>
      mouseX
    </label>
    <input v-model="mouseX" />
    <label>
      mouseY
    </label>
    <input v-model="mouseY" />
    <Typography/>
  </div>
</template>

<script>
export default {
  name: 'IndexPage',
  data () {
    return {
      mouseX: 0,
      mouseY: 0
    }
  },
  mounted () {
    let elem = document.querySelector('.myclass')
    elem.addEventListener('mousemove', this.onMove)
    window.addEventListener('storage', this.storage)
  },
  methods: {
    onMove (event) {
      this.mouseX = event.clientX
      localStorage.setItem('mouseX', event.clientX)
      this.mouseY = event.clientY
      localStorage.setItem('mouseY', event.clientY)
    },
    storage (event) {
      if (event.key === 'mouseX') this.mouseX = event.newValue
      if (event.key === 'mouseY') this.mouseY = event.newValue
    }
  }
}
</script>

<style>
.myclass {
  width: 100%;
  height: 1000px;
  background-color: fff;
}
</style>
