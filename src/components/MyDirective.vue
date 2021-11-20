<template>
  <div>
    <h2>Vue Directive 연습</h2>
    <h3>Hello {{ name }}</h3>
    <h3>v-text : <span v-if="value === 0" v-text="name"></span></h3>
    이름 : <input type="text" v-model="name" > <br/>

    TODO : <input type="text" v-model="todo">
    <button @click="addTodo">Todo추가</button>
    <br/>
    <ul>
        <li v-for="(todo,idx) in todos" :key="idx">
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
      todo: '',
      todos: [
        { text: "Vue.js 튜토리얼 작성하기" },
        { text: "Webpack2 알아보기" },
        { text: "사이드 프로젝트 진행하기" },
      ],
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
      addTodo() {
          //this.todo 는 input에서 입력한 값이 저장된 변수 
          let todoObj = {text: this.todo};
          this.todos.push(todoObj);
          //input 필드 초기화 input필드가 todo 변수와 연결이 되어 있으므로
          this.todo = '';
      }
  },//methods
};
</script>
