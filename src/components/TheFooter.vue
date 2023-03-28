<script>
export default{
    data(){
        return{
            DC:['Term of Use','Privacy Policy (New)','Ad Choises','Advertising','Jobs','Subscriptions','Talent Workshops','CPSC Certificates','Ratings','Shop Help','Contact Us'],
            Sites:['DC','MAD Magazine','DC Kids', 'DC Universe', 'DC Power Visa'],
            iconImage:['footer-facebook.png','footer-periscope.png','footer-pinterest.png','footer-twitter.png','footer-youtube.png']
        }
    },
    props:['links'],
    methods:{
      getImagePath: function(img){
        return new URL(`../assets/${img}`, import.meta.url).href;
      }
    }
}
</script>

<template>
    <footer>
        <div class="foot-bar">
            <div>
            <div>
                <h3>DC COMICS</h3>
                <ul>
                    <li v-for="item in links"><a :href="item.href">{{item.title}}</a></li>
                </ul>
            </div>
            <div>
                <h3>SHOP</h3>
                <ul>
                    <li><a href="#Shop">Shop DC</a></li>
                    <li><a href="ShopDC">Shop DC Collectibles</a></li>
                </ul>
            </div>
            </div>
            <div>
                <div>
                    <h3>DC</h3>
                    <ul>
                        <li v-for="list,index in DC" :key="index"><a href="#">{{list}}</a></li>
                    </ul>
                </div>
                <div>
                    <h3>SITES</h3>
                    <ul>
                        <li v-for="listSites,index in Sites" :key="index"><a href="#">{{ listSites }}</a></li>
                    </ul>
                </div>
            </div>
            <div class="logo-footer">
            </div>
        </div>
    </footer>
    <div class="foot-btn">
        <div class="foot-bottom">
            <button>Sign Up Now!</button>
            <div class="follow">
                <span>FOLLOW US</span>
                <ul>
                    <li v-for="imageIcon,index in iconImage" :key="index"><a href="#"><img :src="getImagePath(imageIcon)" alt="Immmagine"></a></li>
                </ul>
            </div>
        </div>
    </div>
  
</template>

<style lang="scss" scoped>
@use '../styles/partials/variables' as *;
@use '../styles/partials/mixins' as *;

.follow{
    @include d-flex-space-between;
}

footer{
    background-image: url('../assets/footer-bg.jpg');
    color: $color-font;
    padding: 2rem 0;

    h3{
        padding: 0.7rem 0;
    }

    a{
        color:$color-font;
        opacity: 0.5;
        padding-right: 0.8rem;
        display: block;
    }
}

.foot-bar{
    display: flex;
    @include container;
}

.foot-btn{
    background-color: $color-primary;
    padding: 1.5rem 0;
    .foot-bottom{
    @include d-flex-space-between;
    justify-content: space-between;
    @include container;

    span{
        color: $color-secondary;
        padding-right: 1rem;
    }

    ul{
        display: flex;
    }

    li{
        padding: 0.5rem 0;
    }

    button{
        color: $color-font;
        background: none;
        border: 1px solid $color-secondary;
        padding: 0.5rem;
    }
    }
}

</style>