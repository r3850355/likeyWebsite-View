<template>
  <q-page>
    <section-carousel/>
    <section-cards/>
  </q-page>
</template>

<style>
</style>

<script>
  import SectionCarousel from './SectionCarousel'
  import SectionCards from './SectionCards'
  export default {
    components: {
      SectionCarousel,
      SectionCards
    }
  }
</script>
