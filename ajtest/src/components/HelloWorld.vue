<template>
  <div class="hello">

  </div>
</template>

<script>
import axios from 'axios'
export default {
  name: 'HelloWorld',
  data () {
    return {
      msg: 'Welcome to Your Vue.js App'
    }
  },
  created () {
    var that = this
    axios.post('http://dspeaklow.wangge0101.cn/ops/user/login/', {
      phone: '+8618710031682',
      password: 'Aa123456'
    })
      .then(function (response) {
        console.log(response)
      })
      .catch(function (error) {
        console.log(error)
      })
      .finally(function () {
        that.lg()
      })
  },
  methods: {
    async lg () {
      axios.post('/ops/user/login/', {
        phone: '+8618710031682',
        password: 'Aa123456'
      })
        .then(function (response) {
          console.log(response)
        })
        .catch(function (error) {
          console.log(error)
        })
        .finally(function () {
          // always executed
        })
    }
  }
}
</script>
