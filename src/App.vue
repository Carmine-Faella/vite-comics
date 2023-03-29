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

