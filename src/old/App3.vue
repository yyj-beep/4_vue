<template><!--html-->
<h1>Food</h1>
<p>v-for가 컴포넌트를 배열로 만들어 줍니다</p>
<div class="" id="wrapper">
    <food-item
v-for="x in foods"   
v-bind:food-name="x"
    />
</div>
</template>

<script>
export default{//데이터를 컴포넌트에 담아주는 ..
    data(){
        return{
            foods:['사과','피자','쌀','물고기','cake']
        };
    }
}
</script>

<style>
#wrapper{display:flex; flex-wrap:wrap}
#wrapper > div {border:dashed black 1px; margin:10px; padding:0 20px; 
background-color:hotpink;
}
</style>