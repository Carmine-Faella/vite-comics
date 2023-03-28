<script>
    export default{
    name:'TheCard',
    props:{
        image:String,
        title:String
    }
}
</script>

<template>
    <div class="card-wrap">
        <img :src="image" :alt="title">
        <h3>{{ title }}</h3>
    </div>
</template>

<style scoped lang="scss">
@use '../styles/partials/variables' as *;
@use '../styles/partials/mixins' as *;

    .card-wrap{

        padding: 40px;
        height: 200px;
        width: 200px;

        img{
            width: 100%;
            height: 100%;
            object-fit: cover;
        }

        h3{
            color: $color-font;
            font-size: 15px;
        }
    }

</style>