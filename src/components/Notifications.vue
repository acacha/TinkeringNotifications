<template>
  <div >
    <input type="button" value='show noti' @click="showNotification">
    {{ msg }}
  </div>
</template>

<script>
export default {
  name: 'notifications',
  data () {
    return {
      msg: 'TODO!!!'
    }
  },
  methods: {
    showNotification: function () {
      if (Notification.permission === 'granted') {
        var notification = new Notification('Hi there!')
        notification
      }
      console.log('TODO noti')
    }
  },
  created () {
    if (!('Notification' in window)) {
      alert('This browser does not support system notifications')
    }
    Notification.requestPermission().then(function (result) {
      console.log(result)
    })
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
