<template>
  <q-page>
    <q-parallax :src="localData.image"  height="400">
      <p>{{ localData.title }}</p>
    </q-parallax>

    <div class="row place-main">
      <div class="col-8 q-pa-sm">
        <q-breadcrumbs
          separator=">"
          color="light"
        >
          <q-breadcrumbs-el :label="localData.country" to="/" />
          <q-breadcrumbs-el :label="localData.locate" to="/" />
          <q-breadcrumbs-el :label="localData.title" to="/" />
        </q-breadcrumbs>
        <br>
        <span class="title"> {{ localData.title }}</span>

        <div class="row q-mt-lg">
          <div class="col-8">
            <l-icon class="q-mt-sm" :text="'景點編號：  ' + localData.id" :icon="'fas fa-tag'" :color="'grey'"/>
            <br>
            <l-icon class="q-mt-sm" :text="'建議停留：  ' + localData.stay_time + ' 小時'" :icon="'far fa-clock'" :color="'grey'"/>
            <br>
            <l-icon class="q-mt-sm" :text="'營業時間：  ' + localData.open_time" :icon="'fas fa-stopwatch'" :color="'grey'"/>
            <br>
            <l-icon class="q-mt-sm" :text="'地點位置：  ' + localData.address" :icon="'fas fa-map-marker-alt'" :color="'grey'"/>
          </div>
          <div class="col-4 info-right">
            <q-rating v-model="localData.rate" :max="5" color="pink-13" size="16px" disable />
            <span class="q-ml-sm">{{ localData.comment}}則評價</span>
          </div>
        </div>

      </div>
      <div class="col-4">

      </div>
    </div>

  </q-page>
</template>


<script>
import LIcon from 'src/components/LIcon.vue'
export default {
  data(){
    return{
      localData: {
        image:'https://instagram.ftpe8-4.fna.fbcdn.net/vp/f93efc19ab7686509713585bf9187e12/5C53A410/t51.2885-15/e35/43140377_2151186321761409_76062690586049376_n.jpg',
        title : '令人讚嘆的的鬼斧神工 澎湖小門鯨魚洞',
        country: '台灣',
        locate: '澎湖縣',
        address: '881澎湖縣西嶼鄉11-12號',
        id: '12442',
        stay_time: '0.5',
        open_time: '24H',
        rate: '4.5',
        comment: '82'
        
      }
    }
  },
  components:{
    LIcon
  }
}
</script>

<style lang="stylus">
  .q-parallax
    p
      font-size 48px
      color #fff
  .place-main 
    margin-left 10%
    margin-right 10%

    .title
      font-size 28px
      margin-top 20px
  
  .q-breadcrumbs-el
    font-size 14px

  .info-right
      text-align right
      color #979797
      font-size 12px

</style>
