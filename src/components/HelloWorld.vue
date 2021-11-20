<template>
  <div class="hello">
    <h4>{{ titleMsg }}</h4>
    TODO : <input type="text" v-model="todo" />
    <button @click="addTodo">Todo추가</button>
    <br />
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
  //부모(App.vue)가 전달해준 값을 선언하는 예약어 props
  props: ["titleMsg"],
  data() {
    return {
      todo: "",
    };
  }, //data
  methods: {
    addTodo() {
      //부모 컴포넌트에게 전달할 Event 발생시킨다. 
      //Event의 이름은 addEvent 입니다.
      this.$emit("addEvent", this.todo);
      //this.todo 는 input에서 입력한 값이 저장된 변수
      //input 필드 초기화 input필드가 todo 변수와 연결이 되어 있으므로
      this.todo = "";
    },
  }, //methods
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
