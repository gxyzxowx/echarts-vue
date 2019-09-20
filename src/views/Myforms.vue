<template>
  <div>
    <h3>这是我的表格大件</h3>
    <Form1></Form1>
    <input type="number" v-model="a">
    <span>{{funAuto}}</span>
  </div>
</template>
<script>
import Form1 from '@/components/forms/Form1.vue'
export default {
  name: 'myforms',
  data () {
    return {
      a: parseInt(1),
      b: parseInt(3)
    }
  },
  computed: {
    funAuto () {
      let c = this.a + this.b
      return c
    }
  },
  components: {
    Form1
  }
}
</script>
