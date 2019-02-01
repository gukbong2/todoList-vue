<template>
  <div class="inputBox shadow">
    <input type="text" v-model="newTodoItem" placeholder="plz type what you have to do :)" v-on:keyup.enter="addTodo">
    <span class="addContainer" v-on:click="addTodo">
        <i class="addBtn fas fa-plus" aria-hidden="true"></i>
    </span>
  </div>
</template>

<script type="text/javascript">
  export default {
      data() {
        return {
          newTodoItem : ''
        }
      },
      methods : {
        addTodo() {
          console.log(this.newTodoItem);

          if(this.newTodoItem !== "") {
            var value = this.newTodoItem && this.newTodoItem.trim();
              this.$emit('addTodo', value);
              this.clearInput();
          }
        },
        clearInput() {
          this.newTodoItem = '';
        }
      }
  }
</script>

<style scoped>
  input:focus {
    outline : none;
    /* 인풋 박스의 선 스타일 지정 */
  }
  .inputBox {
    background : white;
    height: 50px;
    line-height: 50px; /*인풋 박스에 입력되는 텍스트의 중앙 정렬을 위해 설정 */
    border-radius: 5px; /* 인풋 박스의 둥근 테두리~~ */
  }
  .inputBox input {
    border-style: none;
    font-size: 0.9em;
  }
  .addContainer {
    float: right; /* 할일 추가 아이콘의 위치 정의 ~~*/
    background : linear-gradient(to right, #6478FB, #8763FB);
    display: block;
    width : 3rem;
    border-radius : 0 5px 5px 0;
  }
  .addBtn {
    color : white;
    vertical-align : middle; /*할 일 추가 아이콘의 수직 정렬 정의~~*/
  }



</style>
