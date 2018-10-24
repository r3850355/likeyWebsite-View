<template>
  <div class="layout" :style="{ color: color}">
    <q-icon :class="icon" />
    {{ text }}
  </div>
</template>

<script>
export default {
  props:{
    text: String,
    icon: String,
    color: String,
  }
}
</script>


<style lang="stylus" scoped>
  .layout
    display inline-block
    font-size 14px
    .q-icon
      font-size 14px
</style>
