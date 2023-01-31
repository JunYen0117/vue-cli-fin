<template>
  <NavBar></NavBar>
  <div class="container-fluid">
    <router-view/>
  </div>
</template>

<script>
import NavBar from '../components/NavBar.vue'

export default {
  components: {
    NavBar
  },
  created () {
    // 讀取cookie
    const token = document.cookie.replace(/(?:(?:^|.*;\s*)hexToken\s*=\s*([^;]*).*$)|^.*$/, '$1')
    // 把cookie塞入axios的headers裡
    this.$http.defaults.headers.common['Authorization'] = token

    const api = `${process.env.VUE_APP_API}api/user/check`
    // 打API驗證，是否為登入狀態
    this.$http.post(api)
      .then((res) => {
        console.log(res)
        if (!res.data.success) {
          this.$router.push('/login')
        }
      })
  }
}
</script>
