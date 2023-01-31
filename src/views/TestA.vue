<template>
  <div>
    testA
  </div>
  {{ getBInfo }}
  <router-view @outside="BtoA"></router-view>
</template>
<script>
export default {
  data () {
    return {
      getBInfo: ''
    }
  },
  methods: {
    BtoA (info) {
      this.getBInfo = info
    }
  }
}
</script>
