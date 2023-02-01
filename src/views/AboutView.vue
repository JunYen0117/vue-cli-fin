<template>
  <div class="about">
    <h1>This is an about page</h1>
    <button @mousedown="alert">長按事件</button>
    <div v-if="visibility">長按事件成功</div>
    <button @click="playMusic">放音樂</button>
  </div>
</template>

<script>
export default {
  data () {
    return {
      visibility: false
    }
  },
  methods: {
    alert () {
      setTimeout(() => {
        this.visibility = true
      }, 2000)
    },
    playMusic () {
      const audioPlayer = new Audio('Lullaby_of_Deserted_Hell.mp3')
      audioPlayer.play()
    }
  }
}
</script>
