<template>
  <q-card inline>
    <q-card-media>
      <img :src="image"/>
    </q-card-media>

    <q-card-title>
      <span>{{ title }}</span>
      <div slot="subtitle" class="q-mt-sm">
        <l-icon :icon="'fas fa-star'" :text="rate" :color="'orange'" class="q-mr-md"/>
        <span class="q-mr-sm">{{ comment }}則評價</span> 
        <span>{{ view }}人瀏覽</span>
      </div>
    </q-card-title>

    <q-card-main>
      <l-icon :icon="'fas fa-map-marker-alt'" :text="locate" :color="'grey'" class="q-mr-md"/>
    </q-card-main>
  </q-card>
</template>

<script>
import LIcon from 'src/components/LIcon.vue'
export default {
  props:{
    image: String,
    title: String,
    rate: String,
    comment: String,
    view: String,
    locate: String
  },
  components:{
    LIcon
  }
}
</script>

