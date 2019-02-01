<template>
  <section>
    <ul>
      <li v-for="(todoItem, index) in todoItems" class="shadow" :key="todoItem">
        <i class="checkBtn fas fa-check" aria-hidden="true"></i>
        {{ todoItem }}
        <span class="removeBtn" type="button" @click="removeTodo(todoItem, index)">
            <i class="fas fa-trash-alt"></i>
        </span>
      </li>
    </ul>
  </section>

</template>


<script type="text/javascript">
  export default {
    data() {
      return {
        todoItems : []
      }
    },
    methods : {
      removeTodo(todoItem, index) {
        localStorage.removeItem(todoItem);
        this.todoItems.splice(index, 1);
        console.log(todoItem, index);
      }
    },
    created() {
      if (localStorage.length > 0) {
        for (var i = 0; i < localStorage.length; i++) {
          this.todoItems.push(localStorage.key(i));
        }
      }
    }
  }
</script>

<style scoped>
  ul {
    list-style-type: none; /* 목록 아이템의 스타일을 지정*/
    padding-left: 0px;
    margin-top: 0;
    text-align: left;
  }
  li {
    display: flex;/* 비율 기준의 레이아웃 방식인 flext로 지정*/
    min-height: 50px;
    height: 50px;
    line-height: 50px;
    margin: 0.5rem 0;
    padding : 0 0.9rem;
    background : white;
    border-radius: 5px;
  }
  .checkBtn {
    line-height: 45px;
    color: #62acde;
    margin-left: 5px;
  }
  .removeBtn {
    margin-left: auto;
    color: #de4343;
  }
</style>
