

<template>
<h1 class="mt-5 mb-3 fw-bold text-success">Food</h1>
<p>아래에 버튼을 누르면 item이 순차적으로 하나씩 제거됩니다</p>
<button class="btn btn-outline-danger" @click="removeItem">
I'm Iron Man
</button>
<div id="wrapper">
<food-item
v-for = "x in foods"
:key="x.name"
:food-name="x.name"
:food-desc="x.desc"
:is-favorite="x.favorite"/>
<!--아까는 수량되로 아이템을 적었는데 그래서 불편하여 아이템을 컴포넌트 모듈화 시키고 필요한만큼 재사용함 -->
</div>
</template>

<script>
export default {
  data() { 
    return {
      foods: [
        { name: 'Apples', desc: 'Apples are a type of fruit that grow on trees.', favorite: true},
        { name: 'Pizza', desc: 'Pizza has a bread base with tomato sauce, cheese, and toppings on top.', favorite: false},
        { name: 'Rice', desc: 'Rice is a type of grain that people like to eat.', favorite: false},
        { name: 'Fish', desc: 'Fish is an animal that lives in water.', favorite: true},
        { name: 'Cake', desc: 'Cake is something sweet that tastes good.', favorite: false}
      ]
    };
  },
  methods: {
    removeItem() {
      this.foods.splice(1,1);
    }
  }
}
</script>

<style>
#wrapper{display:flex; flex-wrap:wrap;}

#wrapper > div{
  border:dashed black 1px;
  flex-basis:120px; margin:10px; padding:10px; 
  background-color:lightgreen;
}
</style>

<!--
20250515 v-for Component
:동일한 종류의 많은 요소를 생성하는데 재사용될수 있습니다
v-for배열의 값에 따라 props를 동적으로 할당할수 있습니다

Vue Props
- Vue의 구성옵션 입니다
- props를 사용하면 사용자정의 속성을 컴포넌트 태그에 지정하여 컴포넌트에 데이터를 전달할수 있다
- 구성 요소에 데이터 전달
- 리액트에서 클래스형 컴포넌트에서 최초에 props를 사용 그리고 함수형 컴포넌트가 나오면서
=> hook 
- 컴포넌트태그를 만들고 props를 전달하는 예시를 아래에 구현해 봅니다


-->
