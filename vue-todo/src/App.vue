<template>
  <div id="app">
    <TodoHeader></TodoHeader>
    <TodoInput></TodoInput>
    <TodoList></TodoList>
    <TodoFooter></TodoFooter>
  </div>
</template>



<script>
import TodoHeader from './components/TodoHeader.vue'
import TodoInput from './components/TodoInput.vue'
import TodoList from './components/TodoList.vue'
import TodoFooter from './components/TodoFooter.vue'

export default {
  components: {
  'TodoHeader': TodoHeader,
  'TodoInput': TodoInput,
  'TodoList': TodoList,
  'TodoFooter': TodoFooter
}
}
</script>

<style>
body {
  text-align : center;
  backgorund-color : #F6F6F8;
}
input {
  border-style : groove;
  /* border-style : 인풋 박스 테두리 모양을 정의~~ */
  width : 200px;
}
button {
  border-style : groove;
}
.shadow {
  /* box-shadow 할 일을 입력하는 인풋 박스와 할 일 아이템의 아래 그림자 정의~~ */
  box-shadow : 5px 10px 10px rgba(0,0,0,0.03)
}

</style>
