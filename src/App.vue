<template>
  <h1>Food</h1>
  <p>The toggle button on the component emits an event to the parent "App.vue". The favorite status is modified in "App.vue", and the updated status is sent back to the component so that the image is toggled to reflect the favorite status.</p>
  <p>The result looks exactly like before, but now the favorite staus is modified where it should be in "App.vue" instead of in the "FoodItem.vue" component.</p>
  <div id="wrapper">
  <div>
    <food-item
      v-for="x in foods"
      :key="x.name"
      :food-name="x.name"
      :food-desc="x.desc"
      :is-favorite="x.favorite"
      @toggle-favorite="receiveEmit"/>
  </div> 
  </div>
</template>

<script>
export default{
    data(){
        return{
            foods:[
        { name: 'Apples', desc: 'Apples are a type of fruit that grow on trees.', favorite: true},
        { name: 'Pizza', desc: 'Pizza has a bread base with tomato sauce, cheese, and toppings on top.', favorite: false},
        { name: 'Rice', desc: 'Rice is a type of grain that people like to eat.', favorite: false},
        { name: 'Fish', desc: 'Fish is an animal that lives in water.', favorite: true},
        { name: 'Cake', desc: 'Cake is something sweet that tastes good.', favorite: false}                
            ]
        }
    },
    methods:{
       receiveEmit(){
        alert("Hello world")
       }
    }
}
</script>

<style>
 #wrapper {
    display: flex;
    flex-wrap: wrap;
  }
  #wrapper > div {
    display:inline-block;
    border: dashed black 1px;
    width: 120px;
    margin: 10px;
    padding: 10px;
    background-color: lightgreen;
  }
</style>

<!--
Vue $emit() 메서드 => 구성요소에서 부모로 정보를 전송해야 되는 경우 Props 에 반대
- 부모요소에서 캡처할수 있는 사용자 정의 이벤트를 자식 구성요소에서 만들수 있습니다
- Props는 부모요소에서 자식 구성요소로 데이터를 전송하는데 사용되고
- 반대로 $emit()은 자식구성요소에서 부모 구성 요소로 정보를 전달하는데 사용합니다
-->