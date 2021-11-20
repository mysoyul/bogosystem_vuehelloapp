<template>
  <div class="hello">
    <h4>{{ titleMsg }}</h4>
    
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  //부모(App.vue)가 전달해준 값을 선언하는 예약어 props
  props: ['titleMsg']
}
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
