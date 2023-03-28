<script>
    import TheCard from './TheCard.vue';

    export default{
        name:'CardList',
        components:{
            TheCard
        },
        props:{
            card:Array
        }
    }
</script>

<template>
    <div class="box-cnt">
        <div class="box" v-for="card,index in card" :key="index">
            <TheCard :image="card.thumb" :title="card.series"></TheCard>
        </div>
    </div>
    
</template>

<style scoped lang="scss">
@use '../styles/partials/variables' as *;
@use '../styles/partials/mixins' as *;
    .box-cnt{
        @include container;
        @include d-flex-space-between;
        flex-wrap: wrap;

            .box{
                width: calc(100%/6);
            }
    }
</style>