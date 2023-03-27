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
        }
    }
}
</script>

<template>
  <nav>
    <div class="logo"> 
        <img src="../assets/dc-logo.png" alt="logo Dc">
    </div>
    <ul class="list-nav">
        <li v-for="list in option"><a :href="list.href">{{list.title}}</a></li>
    </ul>
  </nav>
</template>

<style scoped lang="scss">
@use '../styles/partials/variables' as *;
@use '../styles/partials/mixins' as *;

nav{
    height: 10vh;
    justify-content: space-between;
    @include d-flex-space-between;
    @include container;
    

    .list-nav{
        display: flex;

        li{
            padding: 1.5rem 0.8rem;
            font-size: 0.8rem;

            &:hover{
                border-bottom: 5px solid $color-secondary;
            }

            a{
                color: $color-primary;;
            }
        }
    }
}

img{
    object-fit: contain;
    height: 3rem;    
    padding-left: 2rem;    
}

</style>