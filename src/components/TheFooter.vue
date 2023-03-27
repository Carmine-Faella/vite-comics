<script>
export default{
    data(){
        return{
            option: [
                {
                    title:'CHARACTERS',
                    href:'#CHARACTERS'
                },
                {
                    title:'COMICS',
                    href:'#COMICS'
                },
                {
                    title:'MOVIES',
                    href:'#MOVIES'
                },
                {
                    title:'TV',
                    href:'#TV'
                },
                {
                    title:'GAMES',
                    href:'#GAMES'
                },
                {
                    title:'COLLECTIBLES',
                    href:'#COLLECTIBLES'
                },
                {
                    title:'VIDEOS',
                    href:'#VIDEOS'
                },
                {
                    title:'FANS',
                    href:'#FANS'
                },
                {
                    title:'NEWS',
                    href:'#NEWS'
                },
                {
                    title:'SHOP',
                    href:'#SHOP'
                }
            ],
        DC:['Term of Use','Privacy Policy (New)','Ad Choises','Advertising','Jobs','Subscriptions','Talent Workshops','CPSC Certificates','Ratings','Shop Help','Contact Us'],
        Sites:['DC','MAD Magazine','DC Kids', 'DC Universe', 'DC Power Visa'],
        iconImage:['footer-facebook.png','footer-periscope.png','footer-pinterest.png','footer-twitter.png','footer-youtube.png']
        }
    },
    methods:{
      getImagePath: function(img){
        return new URL(`../assets/${img}`, import.meta.url).href;
      }
    }
}
</script>

<template>
    <footer>
        <div class="foot-bar d-flex">
            <div>
            <div>
                <h3>DC COMICS</h3>
                <ul>
                    <li v-for="item in option"><a :href="item.href">{{item.title.toLowerCase()}}</a></li>
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
            <div class="d-flex">
                <div>
                    <h3>DC</h3>
                    <ul>
                        <li v-for="list in DC"><a href="#">{{list}}</a></li>
                    </ul>
                </div>
                <div>
                    <h3>SITES</h3>
                    <ul>
                        <li v-for="listSites in Sites"><a href="#">{{ listSites }}</a></li>
                    </ul>
                </div>
            </div>
            <div class="logo-footer">
                <img src="../assets/dc-logo-bg.png" alt="Logo Footer">
            </div>
        </div>
    </footer>
    <div class="foot-btn">
        <div class="foot-bottom">
            <button>Sign Up Now!</button>
            <div class="d-flex">
                <span>FOLLOW US</span>
                <ul>
                    <li v-for="imageIcon in iconImage"><a href="#"><img :src="getImagePath(imageIcon)" alt="Immmagine"></a></li>
                </ul>
            </div>
        </div>
    </div>
  
</template>

<style lang="scss" scoped>
@use '../styles/partials/variables' as *;
@use '../styles/partials/mixins' as *;

.d-flex{
    display: flex;
    align-items: center;
}

footer{
    background-image: url('../assets/footer-bg.jpg');
    color: $color-font;
    height: 50vh;

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

        img{
            height: 50vh;
            padding-left: 10rem;
        }
}

.foot-btn{
    background-color: $color-primary;
    .foot-bottom{
    height: 10vh;
    padding: 1rem 0;
    display: flex;
    align-items: center;
    justify-content: space-between;
    @include container;

    span{
        color: $color-secondary;
        padding-right: 1rem;
    }

    ul{
        display: flex;
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