<template>
  <section class="col shadow p-3 bg-white rounded">
    <ColorBox :color="value" />
    <h4>{{title}}</h4>
    <h2><a :href="colorApiLink">{{value}}</a></h2>
  </section>
</template>

<script>
import ColorBox from '@/components/ColorBox'

export default {
  name: 'ColorWidget',
  components: { ColorBox },
  props: {
    title: String,
    value: { type: String, required: true }
  },
  computed: {
    colorApiLink () {
      const noHashColor = this.value.substr(1)
      return `https://www.thecolorapi.com/id?format=html&hex=${noHashColor}`
    }
  }
}
</script>

<style lang="stylus">
section
  text-align: center
</style>
