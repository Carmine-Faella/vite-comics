<script>
import TheHeader from './components/TheHeader.vue';
import TheFooter from './components/TheFooter.vue';
import CardList from './components/CardList.vue';

export default{
  components:{
    TheHeader,
    TheFooter,
    CardList
  },
  data(){
    return{
      choises:[
                {
                  title:'DIGITAL COMICS',
                  image:'buy-comics-digital-comics.png'
                },
                {
                  title:'DC MERCHANDISE',
                  image:'buy-comics-merchandise.png'
                },
                {
                  title:'SUBSCRIPTION',
                  image:'buy-comics-subscriptions.png'
                },
                {
                  title:'COMIC SHOP LOCATOR',
                  image:'buy-comics-shop-locator.png'
                },
                {
                  title:'DC POWER VISA',
                  image:'buy-dc-power-visa.svg'
                }
              ],
      option: [
                {
                    title:'Characters',
                    href:'#CHARACTERS'
                },
                {
                    title:'Comics',
                    href:'#COMICS'
                },
                {
                    title:'Movies',
                    href:'#MOVIES'
                },
                {
                    title:'Tv',
                    href:'#TV'
                },
                {
                    title:'Games',
                    href:'#GAMES'
                },
                {
                    title:'Collectibles',
                    href:'#COLLECTIBLES'
                },
                {
                    title:'Videos',
                    href:'#VIDEOS'
                },
                {
                    title:'Fans',
                    href:'#FANS'
                },
                {
                    title:'News',
                    href:'#NEWS'
                },
                {
                    title:'Shop',
                    href:'#SHOP'
                }
            ],
            cards:[	
                    {thumb:	"https://static.dc.com/2023-03/LEGIONOB_Cv1_00111_DIGITAL.jpg?w=640",
                    price:	"$19.99",
                    series:	"Action Comics",
                    type:	"comic book"},
                        
                    {thumb:	"https://static.dc.com/2023-03/BA_Cv9_00911_DIGITAL.jpg?w=640",
                    price:	"$3.99",
                    series:	"American Vampire 1976",
                    type:	"comic book"},
                        
                    {thumb:	"https://static.dc.com/2023-03/ST_GH_Cv3_00311_DIGITAL.jpg?w=640",
                    price:	"$16.99",
                    series:	"Aquaman",
                    type:	"graphic novel"},

                    {thumb:	"https://static.dc.com/2023-03/MS30A_Cv1_00111_DIGITAL.jpg?w=640",
                    price:	"$2.99",
                    series:	"Batgirl",
                    type:	"comic book"},
                        
                    {thumb:	"https://static.dc.com/2023-03/MS30A_Cv1_00111_DIGITAL.jpg?w=640",
                    price:	"$3.99",
                    series:	"Batman",
                    type:	"comic book"},

                    {thumb:	"https://static.dc.com/2023-03/BMSMWF_Cv13_01311_DIGITAL.jpg?w=640",
                    price:	"$2.99",
                    series:	"Batman Beyond",
                    type:	"comic book"},

                    {thumb:	"https://static.dc.com/2023-03/NTW_Cv102_10211_DIGITAL-1.jpg?w=640",
                    price:	"$3.99",
                    series:	"Batman/Superman",
                    type:	"comic book"},
                        
                    {thumb:	"https://static.dc.com/2023-03/FLS_Cv795_79511_DIGITAL.jpg?w=640",
                    price:	"$4.99",
                    series:	"Batman/Superman Annual",
                    type:	"comic book"},
                        
                    {thumb:	"https://static.dc.com/2023-03/DCConnect_35-CVR.jpg?w=640",
                    price:	"$5.99",
                    series:	"Batman: The Joker War Zone",
                    type:	"comic book"},
                        
                    {thumb:	"https://static.dc.com/2023-03/ROBIN_v3%20%28Cover%29.jpg?w=640",
                    price:	"$6.99",
                    series:	"Batman: Three Jokers",
                    type:	"comic book"},

                    {thumb:	"https://static.dc.com/2023-03/LP-ROTG_Cv1_00111_DIGITAL.jpg?w=640",
                    price:	"$4.99",
                    series:	"Batman: White Knight Presents: Harley Quinn",
                    type:	"comic book"},
                        
                    {thumb:	"https://static.dc.com/2023-03/SM_LOST_Cv1_00111_DIGITAL.jpg?w=640",
                    price:	"$16.99",
                    series:	"Catwoman",
                    type:	"graphic novel"}
                ]
    }
  },
    methods:{
      getImagePath: function(img){
        return new URL(`./assets/${img}`, import.meta.url).href;
      }
    }
}
</script>

<template>
  <header>
    <TheHeader :links="option"></TheHeader>
  </header>
  <main>
    <div class="jumbotron">
    </div>
    <div class="box-cnt">
      <span class="title-cards">CURRENT SERIES</span>
      <CardList :card="cards"></CardList>
      <button>LOAD MORE</button>
    </div>
    <section class="cnt-choises">
      <div class="item-icon">
        <div v-for="(item,index) in choises" class="image-wrap" :key="index">
          <div class="img-wrapper"><img :src="getImagePath(item.image)" alt="Immmagine"></div>
          <span><a href="#">{{item.title}}</a></span>
        </div>
      </div>
    </section>
  </main>
  <footer>
    <TheFooter :links="option"></TheFooter>
  </footer>
  
</template>

<style lang="scss">
@use "./styles/general.scss" as *;
@use './styles/partials/mixins.scss' as *;
@use './styles/partials/variables.scss' as *;

.cnt-choises{
  padding: 2rem 0;
}

.box-cnt{
  @include container;
  padding: 0.5rem 0 1rem 0;
  position: relative;
  text-align: center;
  .title-cards{
      position: absolute;
      top: -20px;
      left: 40px;
      background-color: $color-secondary;
      display: inline-block;
      padding: 0.7rem;
      font-weight: bolder;
      color: $color-font;
    }
  button{
    background-color: $color-secondary;
    border:none;
    padding: 0.5rem 2rem;
    color: $color-font;
    font-weight: bold;
    margin: 2rem 0;
  }
}

.item-icon{
  display: flex;
  justify-content: center;
  padding: 2.2rem 0;
  @include container;

  .image-wrap{
    @include d-flex-space-between;

      a{
        color: $color-font;
        font-size: 0.7rem;
        padding: 0 1.5rem;
      }

      .img-wrapper{
      width: 50px;
      height: 50px;

        img{
          width: 100%;
          height: 100%;
          object-fit: contain;

        }
    }
  }

}

.jumbotron{
  height: 300px;
  background-image: url('jumbotron.jpg');
  background-size: cover;
}
</style>

