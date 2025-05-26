<template>
<div class="">
    <h2>
        {{ foodName }}
        <img src="../assets/img/stamp.svg" v-show="foodIsFavorite">
    </h2>
    <p>{{ foodDesc }}</p>
    <button v-on:click="toggleFavorite">Favorite</button>
</div>
</template>

<script>
export default {
    props:['foodName','foodDesc','isFavorite'],
    //부모 컴포넌트로 부터 세가지 속성을 전달받습니다
    data(){//컴포넌트 인스턴스의 반응형 상태를 리턴
        return{
            foodIsFavorite : this.isFavorite//props의 초기값
        }
    },
    methods:{
        toggleFavorite(){//즐겨찾기를 반전함 {상태가 토글이 됨 [true <-> false]}
            this.foodIsFavorite = !this.foodIsFavorite
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