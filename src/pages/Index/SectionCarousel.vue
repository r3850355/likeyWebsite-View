<template>
  <q-carousel
    color="white"
    infinite
    arrows
    autoplay
    height="400px"
  >
    <q-carousel-slide img-src="statics/bg1.JPG" />
    <q-carousel-slide img-src="statics/bg2.JPG" />
    <q-carousel-control
      position="center"
      slot="control-nav" 
      slot-scope="carousel" 
      class="carouselInput"
    >
      <div class="main">
        <b class="title">孔子的中心思想是個仁</b>
        <p class="subtitle">仁的本性是</p>

        <div class="row"> 
          <div class="col-md-2 col-xs-1"></div>
          <div class="col-md-8 col-xs-10">
            <q-input
              inverted-light
              color="white"
              placeholder="輸入城市/景點 或是想去的地方"
              :after="[{
                icon:'fas fa-search-location'
              }]"
              v-model="search"
            >
                <q-autocomplete
                  :static-data="{field: 'label', list: countries}"
                  :filter="advFilter"
                />
                <q-popover
                  no-focus
                  fit
                  v-show="!search"
                >
                  <div class="row viewList">
                    <div class="col-sm-4 col-xs-12">
                      <q-list link no-border>
                        <q-list-header>熱門目的地</q-list-header>
                        <q-item>
                          <q-item-main>
                            東京 <l-icon :icon="'fab fa-gripfire'" :text="'Hot'" :color="'orange'"/>
                          </q-item-main>
                        </q-item>
                        <q-item>
                          <q-item-main>
                            大阪 <l-icon :icon="'fab fa-gripfire'" :text="'Hot'" :color="'orange'"/>
                          </q-item-main>
                        </q-item>
                        <q-item>
                          <q-item-main>
                            北海道 <l-icon :icon="'fas fa-cannabis'" :text="'秋楓限定'" :color="'#f44336'"/>
            
                          </q-item-main>
                        </q-item>
                        <q-item>
                          <q-item-main>
                            香港
                          </q-item-main>
                        </q-item>
                        <q-item>
                          <q-item-main>
                            西藏 
                          </q-item-main>
                        </q-item>
                      </q-list>
                    </div>
                    <div class="col-sm-4 col-xs-12">
                      <q-list link no-border>
                        <q-list-header>國內旅遊</q-list-header>
                        <q-item>
                          <q-item-main>
                            南投 <l-icon :icon="'fab fa-pagelines'" :text="'櫻花限定'" :color="'#f50057'"/>
                          </q-item-main>
                        </q-item>
                        <q-item>
                          <q-item-main>
                            太魯閣 <l-icon :icon="'fab fa-gripfire'" :text="'Hot'" :color="'orange'"/>
                          </q-item-main>
                        </q-item>
                        <q-item>
                          <q-item-main>
                            綠島 <l-icon :icon="'fab fa-gripfire'" :text="'Hot'" :color="'orange'"/>
                          </q-item-main>
                        </q-item>
                        <q-item>
                          <q-item-main>
                            蘭嶼 
                          </q-item-main>
                        </q-item>
                        <q-item>
                          <q-item-main>
                            小琉球 
                          </q-item-main>
                        </q-item>
                      </q-list>
                    </div>
                    <div class="col-sm-4 col-xs-12">
                      <q-list link no-border>
                        <q-list-header>海外地區</q-list-header>
                        <q-item>
                          <q-item-main>
                            加州 <l-icon :icon="'fab fa-gripfire'" :text="'Hot'" :color="'orange'"/>
                          </q-item-main>
                        </q-item>
                        <q-item>
                          <q-item-main>
                            雪梨 <l-icon :icon="'fab fa-gripfire'" :text="'Hot'" :color="'orange'"/>
                          </q-item-main>
                        </q-item>
                        <q-item>
                          <q-item-main>
                            里約
                          </q-item-main>
                        </q-item>
                        <q-item>
                          <q-item-main>
                            邁阿密 
                          </q-item-main>
                        </q-item>
                        <q-item>
                          <q-item-main>
                            巴黎 
                          </q-item-main>
                        </q-item>
                      </q-list>
                    </div>
                  </div>

               

                </q-popover>
            </q-input>
          </div>
          <div class="col-md-2 col-xs-1"></div>
        </div>

        
      </div>

    </q-carousel-control>
  </q-carousel>
</template>

<script>
import _ from 'lodash'
import LIcon from 'src/components/LIcon.vue'
export default {
  data()
  {
    return {
      search: '',
      countries: [
        { label:'台北市' , icon:'fas fa-map-marker-alt' },
        { label:'新北市' , icon:'fas fa-map-marker-alt' },
        { label:'台中市' , icon:'fas fa-map-marker-alt' },
        { label:'「網美景點」台中秋紅谷，秋季賞楓勝地', stamp:'台中市' },
        { label:'東京台場「獨角獸鋼彈」強勢來襲！精彩變身演出搶先看' , stamp:'東京, 台場', rightTextColor:'pink-13'}
      ]
    }
  },
  components:{
    LIcon
  },
  methods:{
    advFilter(terms , { field, list}) {
      return _.filter( list , context => {
        return context[field].match(terms)
      })
    }
  }
}
</script>


<style lang="stylus" scoped>
  .carouselInput 
    width 90%
  .carouselInput .main
    text-align center
    color white
  .carouselInput .main .search
    width 300px
  .imageWall
    width 100px
    height 100px
    object-fit cover


  @media (min-width 768px)
    .carouselInput .title
      font-size 48px
    .carouselInput .subtitle
      font-size 24px

  @media (max-width 768px)
    .carouselInput .title
      font-size 24px
    .carouselInput .subtitle
      font-size 16px

  @media (max-width 576px)
    .viewList
      width 280px
</style>
