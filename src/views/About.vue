<template>
  <div class="about">
    <h1>This is an about page123</h1>
    <MyDome></MyDome>
  </div>
</template>
<script>
import MyDome from '@/components/MyDome.vue'

export default {
  name: 'about',
  components: {
    MyDome
  },
  created: function () {
    this.$ajax.get('http://lianke.weirong100.com/index/index/getzaooplist').then((response) => {
      console.log(response.data)
    }).catch((response) => {
      console.log(response)
    })
  }
}
</script>
