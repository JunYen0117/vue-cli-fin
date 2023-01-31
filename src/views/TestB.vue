<template>
  <div>
    testB
  </div>
  <button @click="$emit('outside', bInfo)">BtoA</button>
</template>

<script>
export default {
  data () {
    return {
      bInfo: 'BtoA'
    }
  }
}
</script>
