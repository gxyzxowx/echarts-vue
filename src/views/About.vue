<template>
  <div class="about">
    <h1>This is an about page</h1>
    <MyDome></MyDome>
  </div>
</template>
<script>
import MyDome from '@/components/MyDome.vue'

export default {
  name: 'about',
  components: {
    MyDome
  }
}
</script>
