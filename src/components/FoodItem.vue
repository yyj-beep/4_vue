<template>
    <div>
        <h2>
            {{ foodName }}
            <img src="../assets/img/img_quality.svg" v-show="isFavorite">
        </h2>
        <p>{{ foodDesc }}</p>
        <button v-on:click.stop="toggleFavorite">Favorite</button>
    </div>
</template>

<script>
export default {
    props: ['foodName','foodDesc','isFavorite'],
    data() {
        return {
            foodIsFavorite: this.isFavorite
        }
    },
    methods: {
        toggleFavorite() {
            this.foodIsFavorite = !this.foodIsFavorite;
        }
    }
};
</script>

<style>
    img {
        height: 1.5em;
        float: right;
    }
</style>               