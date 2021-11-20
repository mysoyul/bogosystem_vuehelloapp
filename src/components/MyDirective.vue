<template>
  <div>
    <h2>Vue Directive 연습</h2>
    <h3>Hello {{ name }}</h3>
    <h3>v-text : <span v-if="value === 0" v-text="name"></span></h3>
    이름 : <input type="text" v-model="name" > <br/>

    <ul>
        <li v-for="(todo,idx) in todosArray" :key="idx">
            {{todo.text}}
        </li>
    </ul>
    <!--
        <input v-bind:value="name" v-on:change="함수"
    -->
    <h3>v-html : <span v-html="htmlname" v-show="isFlag"></span></h3>
    <h3>Value = {{value}}</h3>
    <button v-on:click="increment">증가</button>
    <button @click="decrement">감소</button> <br/>
    <input type="checkbox" v-model="isFlag"/>Logo 이미지
    <!--  v-bind:src 이지만 생략해서 :src -->
    <img width="100" height="100" :src="isFlag ? vuelogo : anglogo" />
    
  </div>
</template>
<script>
export default {
  //부모컴포넌트로 부터 받은 변수를 선언할 때 props
  props:['todosArray'],
  //상태값을 저장할 변수를 선언할 때 data() 함수 내부에 선언한다.
  data() {
    return {
      //상태변수
      name: "Vuejs",
      htmlname: "<i>Vuejs</i>",
      isFlag: false,
      value: 0,
      vuelogo: "https://vuejs.org/images/logo.png",
      anglogo: "https://angular.io/assets/images/logos/angular/angular.svg",
      
    
    };
  },//data
  //개발자가 선언하는 메서드(함수)는 methods 라는 속성인 객체안에 선언을 한다.
  methods: {
      increment:function() {
        this.value++;   
      },
      decrement() {
        this.value--;
      },
  },//methods
};
</script>
