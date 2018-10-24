<template>   
  <div class="row section-card q-ma-sm">
    <div class="col-12 q-pa-sm"><b class="title">本月最精選</b></div>
    <template v-for="(data,idx) in monthBestList">
      <div class="col-lg-3 col-sm-6 col-xs-12 q-pa-sm" :key="idx">
        <l-card 
          :title="data.title"
          :rate ="data.rate"
          :comment="data.comment"
          :view="data.view"
          :locate="data.locate"
          :image="data.image"
        />
      </div>
    </template>
  </div>
</template>

<script>
import LCard from 'src/components/LCard.vue'
export default {
  components:{
    LCard
  },
  data(){
    return{
      monthBestList:[
        { title:'和明織品文化館 HMTM' , rate: '4.8', comment: '99', view: '3621', locate: '台灣, 台南市' ,image:'https://instagram.ftpe8-4.fna.fbcdn.net/vp/dc86cba53aada051ef601547e929676c/5C67AD0F/t51.2885-15/e35/27891849_1884619055118044_7666637221746704384_n.jpg'},
        { title:'澎湖鯨魚洞' , rate: '4.6', comment: '75', view: '2643', locate: '台灣, 馬公市' ,image:'https://instagram.ftpe8-4.fna.fbcdn.net/vp/f93efc19ab7686509713585bf9187e12/5C53A410/t51.2885-15/e35/43140377_2151186321761409_76062690586049376_n.jpg'},
        { title:'石門班哨角休憩區' , rate: '4.5', comment: '82', view: '2145', locate: '台灣, 馬公市' ,image:'https://instagram.ftpe8-4.fna.fbcdn.net/vp/2d264f50ef332891546137642b8b8b3c/5C802CF9/t51.2885-15/e35/37415020_1342680469168149_7997842370647293952_n.jpg'},
        { title:'宜蘭伯朗大道' , rate: '4.2', comment: '43', view: '1456', locate: '台灣, 宜蘭縣' ,image:'https://instagram.ftpe8-4.fna.fbcdn.net/vp/eb77236c054f378313665c25a5d1363b/5C509EB8/t51.2885-15/e35/35177408_443518052759652_8108135769303941120_n.jpg'},
      ]
    }
  }
}
</script>

<style lang="stylus">
.section-card
  margin-right 5%
  margin-left 5%

  .title
    font-size 24px

  .q-card-title
    font-size 16px
    line-height 24px

  .q-card-media
    max-height 200px
</style>