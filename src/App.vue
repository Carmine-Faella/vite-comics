<script>
import TheHeader from './components/TheHeader.vue';
import TheFooter from './components/TheFooter.vue';

export default{
  components:{
    TheHeader,
    TheFooter
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
    <TheHeader></TheHeader>
  </header>
  <main>
    <div>Content goes here</div>
    <section class="cnt-choises">
      <div class="item-icon">
        <div v-for="item in choises" class="image-wrap">
          <div class="img-wrapper"><img :src="getImagePath(item.image)" alt="Immmagine"></div>
          <span><a href="#">{{item.title}}</a></span>
        </div>
      </div>
    </section>
  </main>
  <footer>
    <TheFooter></TheFooter>
  </footer>
  
</template>

<style lang="scss">
@use "./styles/general.scss" as *;
@use './styles/partials/mixins.scss' as *;
@use './styles/partials/variables.scss' as *;

.item-icon{
  display: flex;
  justify-content: center;
  padding: 4rem 0;
  @include container;

  .image-wrap{
    display: flex;
    align-items: center;

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
</style>

